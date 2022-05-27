# yourTextHere

## Description

An Installable Web Text Editor
This application allows you to edit text on the fly. Don't have internet connection? It doesn't matter, the app will function as normal,
and save your notes for you to look at in the future!

## Link to Deployed Application

[Click to view the deployed application](https://your-text-here.herokuapp.com/)

## Table of contents

- [Technologies Employed](#technologies-employed)
- [Key Functions](#key-functions)
- [License](#license)
- [Contact/Questions](#questions)
- [Summary](#summary-and-learning-points)

## Technologies Employed

| Techlogy             | Implementation/Use   |
| -------------------- | -------------------- |
| Node.js              | JavaScript runtime   |
| Node Package Manager | Manage node packages |
| Express.js           | Web framework        |
| Workbox              | Easy service workers |
| concurrently         | run multiple scripts |
| Heroku               | Deployment           |
| idb                  | indexed db wrapper   |

## Key Functionality

### Write to database

This was the function within the database.js that made it possible to save the note in the editor to indexedDB,
using idb as a wrapper for ease of use.

```javascript
export const putDb = async (content) => {
  const todosDb = await openDB("jate", 1);
  const tx = todosDb.transaction("jate", "readwrite");
  const store = tx.objectStore("jate");
  const res = await store.put({ id: 1, content: content });
  console.log("Saved to database!");
};
```

### update Post

These lines of code, made it such that there would be an install button on the page that would allow you
to click it to install the PWA.

```javascript
butInstall.addEventListener("click", () => {
  butInstall.setAttribute("disabled", true);
  butInstall.textContent = "Installed!";
});

window.addEventListener("appinstalled", (e) => {
  console.log("app installed", e);
});
```

## License

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

## Questions?

Please contact me at:

sgquin@gmail.com

Alternatively, visit my github:

https://www.github.com/sharkby7e

## Summary and Learning Points

This was a good introduction to webpack, and PWA. I leared a lot about how to create and prepare users
to install PWA's, and how to use webpack to build my application and prepare it for deployment
