---
title: Implementing Popup Interactivity in a Chrome Extension
nextjs:
  metadata:
    title: Adding Interactivity to the Popup of a Text-Changing Chrome Extension
    description: A step-by-step guide on how to use JavaScript in popup.js to add functionality to the popup of a Chrome extension, enabling it to interact with webpage content.
---

## Introduction

In this guide, we will explore how to implement interactivity in the popup of the "Text Changer" Chrome Extension using JavaScript. The `popup.js` file is responsible for adding functionality to the popup elements, particularly the button, and communicating with the content script.

## Creating the file

To follow along in this next section, create a new file in your project called `popup.js`. You can put this in the main folder but if you prefer to be more organized, you can put it in a scripts folder and modify the manieft if you know what you are doing. For now, the main folder works just fine.

## Adding Functionality with `popup.js`

### Understanding `popup.js`

Here's the JavaScript code in `popup.js`:

### JavaScript Code

```javascript
// Add an event listener to a button with the id 'button1'
document.getElementById('button1').addEventListener('click', function() {
    // Send a message to the content script to trigger the function
    chrome.tabs.query({ active: true, currentWindow: true }, function(tabs) {
        var activeTab = tabs[0];
        chrome.tabs.sendMessage(activeTab.id, { action: 'triggerReplaceTextNodes', word: document.getElementById("Word").value});
    });
});
```

### Breakdown of the Code

- **Event Listener**:
  - The script adds a click event listener to the button with the id `button1`.
  - When the button is clicked, the enclosed function is executed.

- **Message Sending**:
  - The `chrome.tabs.query` method is used to find the active tab in the current window.
  - Once the active tab is identified (stored in `activeTab`), a message is sent to this tab using `chrome.tabs.sendMessage`.
  - The message includes an `action` property set to `'triggerReplaceTextNodes'` and a `word` property set to the value entered in the input field with the id `Word`.

### Key Functionalities

- **Interactivity**: The script makes the popup interactive, allowing user input to influence the extension's behavior.
- **Communication with Content Script**: The message sent to the active tab triggers the content script (`content.js`), which will execute the text-changing functionality on the webpage.
- **Dynamic Input Handling**: The script dynamically retrieves the user-entered word from the input field and sends it as part of the message, ensuring that the content script acts on current user input.

### Important Considerations

- **User Experience**: This setup provides a simple and intuitive interface for the user to interact with the extension.
- **Extension Permissions**: Ensure that the Chrome Extension has the necessary permissions to use `chrome.tabs` and message passing in the manifest file.

In the next section, we will bring together all the components we've discussed—manifest, popup, and content script—to see how they interact and provide a seamless experience for modifying text on webpages. Stay tuned for a comprehensive overview of the entire extension setup.