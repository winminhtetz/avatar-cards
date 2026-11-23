# Avatar Cards

A collection of avatar card images and a JSON manifest served via jsDelivr CDN.

## API Endpoints

### 1. Avatar Cards Manifest
Fetch the list of all avatar cards:

- **URL**: `https://cdn.jsdelivr.net/gh/winminhtetz/avatar-cards/api/avatar_cards.json`
- **Method**: `GET`
- **Response Format**:
  ```json
  {
    "total": 42,
    "avatars": [
      {
        "id": 1,
        "name": "San San",
        "filename": "portrait_01.png"
      },
      {
        "id": 2,
        "name": "Thida",
        "filename": "portrait_02.png"
      }
    ]
  }
  ```

### 2. Card Images CDN
Fetch individual avatar cards directly by filename:

- **Base URL**: `https://cdn.jsdelivr.net/gh/winminhtetz/avatar-cards/cards/`
- **Format**: `https://cdn.jsdelivr.net/gh/winminhtetz/avatar-cards/cards/{filename}`
- **Examples**:
  - `https://cdn.jsdelivr.net/gh/winminhtetz/avatar-cards/cards/portrait_01.png`
  - `https://cdn.jsdelivr.net/gh/winminhtetz/avatar-cards/cards/01_Charles.png`

## Usage Example

```javascript
// Fetch avatar cards manifest
fetch("https://cdn.jsdelivr.net/gh/winminhtetz/avatar-cards/api/avatar_cards.json")
  .then((res) => res.json())
  .then((data) => {
    console.log(`Loaded ${data.total} avatar cards`);
    data.avatars.forEach((avatar) => {
      const imgUrl = `https://cdn.jsdelivr.net/gh/winminhtetz/avatar-cards/cards/${avatar.filename}`;
      console.log(avatar.id, avatar.name, imgUrl);
    });
  });
```

## Preview

Open `index.html` in your browser to view the interactive Avatar Cards gallery.
