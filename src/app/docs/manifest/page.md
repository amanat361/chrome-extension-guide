---
title: Creating a Chrome Extension Manifest for Text Modification
nextjs:
  metadata:
    title: Setting Up a Chrome Extension Manifest for Webpage Text Modification
    description: Learn how to craft a manifest file for a Chrome extension aimed at modifying text on webpages, complete with icons, popups, and content scripts.
---

## Introduction

In this guide, we're focusing on creating a manifest file for a Chrome Extension named "Text Changer," which is designed to change text on webpages.

## Understanding the Manifest File

### The Manifest File Explained

The manifest file is a crucial component of a Chrome Extension, dictating its basic properties and behaviors. Here's the manifest for the "Text Changer" extension:

```json
{
    "manifest_version": 3,
    "name": "Text Changer",
    "description": "Changes text on a webpage.",
    "version": "1.0",
    "icons": {
        "16": "Images/icon-16.png",
        "32": "Images/icon-32.png",
        "48": "Images/icon-48.png",
        "128": "Images/icon-128.png"
    },
    "action": {
        "default_popup": "popup.html"
    },
    "content_scripts": [
        {
            "js": ["content.js"],
            "matches": ["<all_urls>"]
        }
    ]
}
```

### Key Elements of the Manifest

- **`manifest_version`**: Indicates the version of the manifest file format; version 3 is used here.
- **`name`**: The name of the extension as it appears to users.
- **`description`**: A brief summary of the extension's functionality.
- **`version`**: The current version of the extension, important for updates and management.
- **`icons`**: Paths to various sizes of the extension's icon, used in the Chrome Web Store and Chrome's user interface.
- **`action`**: Specifies the extension's default behavior, in this case, linking to `popup.html` as the popup when the extension icon is clicked.
- **`content_scripts`**: Defines scripts to be injected into webpages. Here, `content.js` is set to run on all URLs (`<all_urls>`).

### Important Points

- **Icon Files**: Make sure the specified icon files are correctly placed in the indicated paths.
- **Content Scripts**: The `content.js` file should contain the logic to modify text on webpages. It's crucial to ensure that this script targets the correct elements and functions as intended.

Next, we'll discuss setting up `popup.html` and `content.js`, which are key components of this extension. These files will define the user interface and the core functionality of the "Text Changer" extension. Stay tuned for a detailed walkthrough on creating and implementing these files.