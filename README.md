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

index.html:
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
        <h1>Welcome to DOM Manipulation!</h1>
    </header>

    <main>
        <p id="dynamicText">This is the initial text.</p>

        <div id="styleContainer">
            <p id="styledParagraph">This paragraph will be styled.</p>
        </div>

        <button id="changeTextButton">Change Text</button>
        <button id="styleButton">Apply Style</button>
        <button id="addElementButton">Add Element</button>
        <button id="removeElementButton">Remove Element</button>

        <div id="dynamicElements">
            </div>
    </main>

    <footer>
        <p>&copy; 2025 My DOM Manipulation Example</p>
    </footer>

    <script src="script.js"></script>
</body>
</html>

style.css (optional, for initial styling):
body {
    font-family: sans-serif;
    margin: 20px;
    background-color: #f4f4f4;
}

header {
    background-color: #333;
    color: white;
    padding: 1em;
    text-align: center;
    margin-bottom: 20px;
}

main {
    background-color: white;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

button {
    padding: 10px 15px;
    margin-right: 10px;
    cursor: pointer;
    border: none;
    border-radius: 3px;
    background-color: #007bff;
    color: white;
}

button:hover {
    background-color: #0056b3;
}

#styleContainer {
    margin-bottom: 15px;
    padding: 10px;
    border: 1px solid #ccc;
}

#styledParagraph {
    padding: 8px;
    background-color: #e9ecef;
    border-radius: 3px;
}

#dynamicElements {
    margin-top: 20px;
    border: 1px dashed #ccc;
    padding: 10px;
}

script.js:
document.addEventListener('DOMContentLoaded', function() {
    // Get references to the HTML elements
    const dynamicTextElement = document.getElementById('dynamicText');
    const styleParagraphElement = document.getElementById('styledParagraph');
    const changeTextButton = document.getElementById('changeTextButton');
    const styleButton = document.getElementById('styleButton');
    const addElementButton = document.getElementById('addElementButton');
    const removeElementButton = document.getElementById('removeElementButton');
    const dynamicElementsContainer = document.getElementById('dynamicElements');

    // Counter for dynamically added elements
    let elementCounter = 1;
    let lastAddedElement = null;

    // Function to change text content dynamically
    function changeDynamicText() {
        dynamicTextElement.textContent = 'The text has been changed by JavaScript!';
    }

    // Function to modify CSS styles
    function applyStyles() {
        styleParagraphElement.style.backgroundColor = 'lightblue';
        styleParagraphElement.style.color = 'darkblue';
        styleParagraphElement.style.fontWeight = 'bold';
        styleParagraphElement.style.padding = '15px';
    }

    // Function to add a new element
    function addDynamicElement() {
        const newElement = document.createElement('p');
        newElement.textContent = `New Element ${elementCounter}`;
        newElement.id = `dynamicElement-${elementCounter}`;
        dynamicElementsContainer.appendChild(newElement);
        lastAddedElement = newElement;
        elementCounter++;
    }

    // Function to remove the last added element
    function removeDynamicElement() {
        if (lastAddedElement) {
            dynamicElementsContainer.removeChild(lastAddedElement);
            lastAddedElement = null;
            if (elementCounter > 1) {
                elementCounter--;
                // Try to find the new last element (not the most efficient but works for this example)
                const allDynamicElements = dynamicElementsContainer.querySelectorAll('p');
                if (allDynamicElements.length > 0) {
                    lastAddedElement = allDynamicElements[allDynamicElements.length - 1];
                } else {
                    elementCounter = 1; // Reset counter if no elements left
                }
            }
        } else {
            alert('No elements to remove!');
        }
    }

    // Event listeners for the buttons
    changeTextButton.addEventListener('click', changeDynamicText);
    styleButton.addEventListener('click', applyStyles);
    addElementButton.addEventListener('click', addDynamicElement);
    removeElementButton.addEventListener('click', removeDynamicElement);
});


 
