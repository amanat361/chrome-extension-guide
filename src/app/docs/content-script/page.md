---
title: Implementing Text Replacement in a Webpage with JavaScript
nextjs:
  metadata:
    title: JavaScript Text Node Manipulation and Chrome Message Handling
    description: Learn how to manipulate text nodes in a webpage and handle messages in a Chrome extension using JavaScript.
---

## Introduction

In this guide, we will explore how to implement a JavaScript function that replaces text in a webpage. We'll also cover how to listen for messages in a Chrome extension and trigger this function accordingly.

## Creating the file

To follow along in this next section, create a new file in your project called `content.js`. You can put this in the main folder but if you prefer to be more organized, you can put it in a scripts folder and modify the manieft if you know what you are doing. For now, the main folder works just fine.

## Replacing Text Nodes with Custom Words

### Overview

Our main function, `replaceTextNodes`, takes two parameters: `element` and `word`. This function will scan all text nodes within the given element and append the specified word to their content.

### Function Breakdown

```javascript
function replaceTextNodes(element, word) {
    Array.from(element.childNodes).forEach(node => {
        if (node.nodeType === Node.TEXT_NODE && node.textContent.trim() !== '') {
            // Replace text node content 
            node.textContent = node.textContent + word;
        } else if (node.nodeType === Node.ELEMENT_NODE) {
            // Recursively handle child elements
            replaceTextNodes(node, word);
        }
    });
}
```

- **Parameters**: 
  - `element`: The DOM element within which text nodes will be altered.
  - `word`: The word to be appended to the text content.

- **Process**:
  - Converts `element.childNodes` into an array and iterates over each node.
  - Checks if the node is a text node and contains non-whitespace characters.
  - Appends the `word` to the content of text nodes.
  - If the node is an element node, the function calls itself recursively to handle child elements.

## Handling Chrome Extension Messages

### Listening for Messages

```javascript
chrome.runtime.onMessage.addListener(function(request, sender, sendResponse) {
    if (request.action === "triggerReplaceTextNodes") {
        // Trigger the function when a message with the specified action is received
        console.log(request.word)
        replaceTextNodes(document.body, request.word);
    }
});
```

- **Description**: 
  - This snippet sets up an event listener for messages sent to the Chrome extension.
  - It listens for a specific message action, `"triggerReplaceTextNodes"`.

- **Functionality**:
  - When a message with the action `"triggerReplaceTextNodes"` is received, it calls `replaceTextNodes` function.
  - The function is triggered on the entire `document.body` using the `word` received in the message.

### Important Points

- This code is typically used in content scripts of Chrome extensions.
- It allows dynamic manipulation of webpage content based on messages received from other parts of the extension, like popup scripts or background scripts.

In the next section, we will look at setting up the popup.js to send messages to the content script. Stay tuned for detailed steps on that process.