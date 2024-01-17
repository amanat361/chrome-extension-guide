---
title: Crafting the Popup HTML for the Chrome Extension
nextjs:
  metadata:
    title: Designing the Popup HTML for a Text-Changing Chrome Extension
    description: Learn how to build a simple yet effective popup.html for a Chrome extension that changes text on webpages, featuring a user-friendly interface with input and button elements.
---



## Introduction

In this guide, we will create the HTML structure for the popup interface of the "Text Changer" Chrome Extension. This popup provides the user interface where users can interact with the extension.

## Creating the file

To follow along in this next section, create a new file in your project called `popup.html`. You can put this in the main folder but if you prefer to be more organized, you can put it in a scripts folder and modify the manieft if you know what you are doing. For now, the main folder works just fine.


## Building the Popup HTML (`popup.html`)

### Overview of `popup.html`

The `popup.html` file defines the HTML structure of the popup. Here's the content of the file:

### HTML Content

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="popup.css" />
</head>
<body>
    <input placeholder="Type Word" id="Word"/>
    <button id="button1">Run</button>
    <script src="popup.js"></script>
</body>
</html>
```

### Breakdown of Elements

- **DOCTYPE and Language**: The `<!DOCTYPE html>` declaration defines the document type and HTML version. `lang="en"` specifies that the document is in English.
  
- **Head Section**:
  - **Meta Tags**: The charset `UTF-8` ensures that the document can handle any text input. The viewport tag ensures the popup is responsive and scales properly on different devices.
  - **Title**: Currently set to "Document," but it can be renamed to something more descriptive, like "Text Changer Popup".
  - **CSS Link**: Links to the `popup.css` file, which styles the elements in the popup.

- **Body Section**:
  - **Input Field**: An input element with a placeholder "Type Word", allowing users to enter the word they want to change.
  - **Button**: A button labeled "Run" that, when clicked, will presumably trigger the text-changing functionality.
  - **Script Tag**: Links to `popup.js`, which will contain the JavaScript needed to interact with the input and button.

### Key Considerations

- **Functionality**: The popup contains an input field for the word and a button to execute the change. This setup should be intuitive for users.
- **Styling**: The styling from `popup.css` will be applied, ensuring a consistent and user-friendly appearance.
- **Script Interaction**: The JavaScript in `popup.js` (to be discussed in the next section) will handle the interaction logic, such as what happens when the user clicks the "Run" button.

In the following section, we will delve into creating the `popup.js` file, which will bring functionality to our popup, allowing users to interact with the extension and change text on webpages. Stay tuned for a comprehensive guide on implementing this interactivity.