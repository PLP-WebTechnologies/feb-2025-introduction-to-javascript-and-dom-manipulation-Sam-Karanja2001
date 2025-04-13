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

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript and DOM Manipulation</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <header>
        <h1>Welcome to the DOM Playground</h1>
    </header>

    <main>
        <p id="dynamicText">This is the initial text.</p>

        <button id="changeTextBtn">Change Text</button>
        <button id="changeStyleBtn">Change Style</button>
        <button id="addElementBtn">Add Element</button>
        <div id="elementContainer">
            </div>
    </main>

    <footer>
        <p>&copy; 2025 JavaScript DOM Manipulation</p>
    </footer>

    <script src="script.js"></script>
</body>
</html>

/* style.css (Optional - for initial styling) */
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

#elementContainer {
    margin-top: 20px;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
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
    // Get references to the HTML elements we'll be manipulating
    const dynamicTextElement = document.getElementById('dynamicText');
    const changeTextButton = document.getElementById('changeTextBtn');
    const changeStyleButton = document.getElementById('changeStyleBtn');
    const addElementButton = document.getElementById('addElementBtn');
    const elementContainer = document.getElementById('elementContainer');
    let newElementCounter = 1;

    // Function to change the text content
    function changeText() {
        dynamicTextElement.textContent = 'The text has been dynamically changed by JavaScript!';
    }

    // Function to change the CSS style
    function changeStyle() {
        dynamicTextElement.style.color = 'green';
        dynamicTextElement.style.fontWeight = 'bold';
        dynamicTextElement.style.backgroundColor = '#e0ffe0';
        dynamicTextElement.style.padding = '5px';
        dynamicTextElement.style.borderRadius = '3px';
    }

    // Function to add a new element
    function addElement() {
        const newParagraph = document.createElement('p');
        newParagraph.textContent = `New Paragraph Element #${newElementCounter}`;
        newParagraph.classList.add('dynamic-paragraph'); // You can add classes for styling
        elementContainer.appendChild(newParagraph);
        newElementCounter++;
    }

    // Function to remove the last added element
    function removeElement() {
        const lastParagraph = elementContainer.lastElementChild;
        if (lastParagraph) {
            elementContainer.removeChild(lastParagraph);
            newElementCounter--;
        } else {
            alert('No elements to remove!');
        }
    }

    // Add event listeners to the buttons
    changeTextButton.addEventListener('click', changeText);
    changeStyleButton.addEventListener('click', changeStyle);
    addElementButton.addEventListener('click', addElement);

    // Add a "Remove Element" button dynamically
    const removeElementButton = document.createElement('button');
    removeElementButton.textContent = 'Remove Element';
    removeElementButton.id = 'removeElementBtn';
    main.appendChild(removeElementButton);

    // Add event listener for the dynamically created remove button
    removeElementButton.addEventListener('click', removeElement);
});
