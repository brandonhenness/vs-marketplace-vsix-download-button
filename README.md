# VS Marketplace: Download VSIX Button

[![Greasy Fork](https://img.shields.io/badge/Greasy%20Fork-View%20Script-blue)](https://greasyfork.org/en/scripts/548857-vs-marketplace-download-vsix)

![Download VSIX Button Screenshot](./vsix-download-button-screenshot.png)

---

## Why I Made This Script

Microsoft removed the built-in **Download VSIX** button from the Visual Studio Marketplace.  
This decision has made it more difficult for developers in **environments without direct internet access** to install extensions.  
This script restores that functionality in a seamless way.

---

## ✨ Features

- **Exact style match**: The Download button is cloned from the real Install button so it looks native.
- **No API calls or scraping**: The link is built directly from the extension’s `itemName` in the page URL.
- **Direct download**: Click to immediately download the `.vsix` file for the latest version.
- **SPA-safe**: Works even when navigating between extensions without a full page reload.

---

## 🔗 Example

For the Python extension at:  
`https://marketplace.visualstudio.com/items?itemName=ms-python.python`

The script generates a download link to:  
[https://marketplace.visualstudio.com/_apis/public/gallery/publishers/ms-python/vsextensions/python/latest/vspackage](https://marketplace.visualstudio.com/_apis/public/gallery/publishers/ms-python/vsextensions/python/latest/vspackage)

---

## 📥 Installation

1. Install a userscript manager if you don’t already have one:
   - [Tampermonkey](https://www.tampermonkey.net/) (recommended)
   - [Violentmonkey](https://violentmonkey.github.io/)
   - [Greasemonkey](https://www.greasespot.net/) (not as well tested)

2. Install this script from [Greasy Fork](https://greasyfork.org/en/scripts/548857-vs-marketplace-download-vsix).

3. Visit any Visual Studio Marketplace extension page — the **Download VSIX** button will appear right next to Install.

---

## ⚙ How It Works

- Reads the `publisher.extension` ID from the page URL.
- Constructs a `latest/vspackage` download link for that extension.
- Clones the existing Install button’s HTML/CSS, updates its text and `href`, and inserts it beside Install.
- Keeps the button injected on all SPA navigations and re-renders.

---

## 🛠 Planned Features

- **Download old versions**:  
  Add an option to select and download previous releases of an extension by parsing the Version History tab and generating VSIX links for each version.

---

## License

This project is licensed under the [GNU General Public License v3.0](LICENSE).

---

Developed with ❤️ by [Brandon Henness](https://github.com/brandonhenness)
