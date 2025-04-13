# Introduction to JavaScript and DOM Manipulation

## Objectives

Write basic JavaScript functions.
Manipulate the DOM dynamically.
Respond to user interactions.

## Instructions

- Create a script.js file and link it to a HTML.
- Structure the document using DOCTYPE, html, head, and body.

>[!NOTE]
>  - Write JavaScript that:
>  - Changes text content dynamically.
>  - Modifies CSS styles via JavaScript.
>  - Adds or removes an element when a button is clicked.


# Tasks
- Create a well-structured HTML5 document.
- Use at least 5 different HTML elements.
- Ensure semantic correctness.

Happy Coding! 💻✨

DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript DOM Manipulation</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>

    <header>
        <h1>DOM Manipulation Example</h1>
    </header>

    <main>
        <p id="dynamicParagraph">This is the initial text content.</p>

        <button id="changeTextButton">Change Text</button>
        <button id="changeStyleButton">Change Style</button>
        <button id="addElementButton">Add New Item</button>
        <button id="removeElementButton">Remove Last Item</button>

        <ul id="itemList">
            <li>Item 1</li>
            <li>Item 2</li>
        </ul>
    </main>

    <footer>
        <p>&copy; 2025 My DOM Playground</p>
    </footer>

    <script src="script.js"></script>
</body>
</html>

/* styles.css (Optional - for basic styling) */
body {
    font-family: sans-serif;
    margin: 20px;
    background-color: #f4f4f4;
}

header {
    text-align: center;
    padding: 1em 0;
    background-color: #333;
    color: white;
}

main {
    background-color: white;
    padding: 20px;
    border-radius: 8px;
    margin-top: 20px;
}

button {
    padding: 0.8em 1.5em;
    margin-right: 10px;
    cursor: pointer;
    border: none;
    border-radius: 5px;
    background-color: #007bff;
    color: white;
}

button:hover {
    background-color: #0056b3;
}

#itemList {
    margin-top: 20px;
    padding-left: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
}

#itemList li {
    padding: 0.5em 0;
}

footer {
    text-align: center;
    margin-top: 20px;
    padding: 1em 0;
    background-color: #333;
    color: white;
    border-radius: 5px;
}

// script.js

document.addEventListener('DOMContentLoaded', function() {
    const dynamicParagraph = document.getElementById('dynamicParagraph');
    const changeTextButton = document.getElementById('changeTextButton');
    const changeStyleButton = document.getElementById('changeStyleButton');
    const addElementButton = document.getElementById('addElementButton');
    const removeElementButton = document.getElementById('removeElementButton');
    const itemList = document.getElementById('itemList');

    // Function to change text content
    function changeText() {
        dynamicParagraph.textContent = 'The text has been updated by JavaScript!';
    }

    // Function to modify CSS styles
    function changeStyle() {
        dynamicParagraph.style.color = 'green';
        dynamicParagraph.style.fontWeight = 'bold';
        dynamicParagraph.style.backgroundColor = '#e0ffe0';
        dynamicParagraph.style.padding = '5px';
        dynamicParagraph.style.borderRadius = '3px';
    }

    // Function to add a new element to the list
    function addElement() {
        const newItem = document.createElement('li');
        newItem.textContent = `New Item ${itemList.children.length + 1}`;
        itemList.appendChild(newItem);
    }

    // Function to remove the last element from the list
    function removeElement() {
        if (itemList.lastElementChild) {
            itemList.removeChild(itemList.lastElementChild);
        } else {
            alert('No items to remove!');
        }
    }

    // Event listeners for the buttons
    changeTextButton.addEventListener('click', changeText);
    changeStyleButton.addEventListener('click', changeStyle);
    addElementButton.addEventListener('click', addElement);
    removeElementButton.addEventListener('click', removeElement);
});
