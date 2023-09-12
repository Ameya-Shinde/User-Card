# User Information Storage Web App

This web application allows users to input and store their personal information locally using the `localStorage` API.

## Features

- Allows users to input and store personal information.
- Information is stored locally using `localStorage`.
- Supports storing first name, last name, country, phone number, state, city, and village.
- Creates a card for the information given.

## How it Works

1. The application attempts to retrieve stored user information from `localStorage`.
2. If user information is found, it populates the corresponding HTML elements with the retrieved data.
3. If no stored information is found, the user is prompted to enter their personal details.
4. Entered information is stored in `localStorage` as a JSON string.

## Hosted Link
https://ameya-shinde.github.io/User-Card/

## JavaScript Features

This web application leverages several key JavaScript features and concepts:

### 1. Local Storage API

The application utilizes the `localStorage` API to store and retrieve user information. This API allows for persistent data storage within the user's browser. User details are stored as a JSON string, providing a simple and efficient means of data persistence.

``javascript
const storedUserInfo = localStorage.getItem("userInformation");``

### 2. JSON Parsing
Stored user information is retrieved as a JSON string from localStorage. To make this data usable in the application, it undergoes JSON parsing using JSON.parse(). This converts the string into a JavaScript object for easy access to individual data points.

``javascript
const userInfo = JSON.parse(storedUserInfo);``

### 3. Event Handling
The application employs event listeners to respond to user interactions. Notably, the "Clear" button triggers an event listener that removes stored user information and reloads the page.
``javascript
  clrBtn.addEventListener("click", () => {
    localStorage.removeItem("userInformation");
    window.location.reload();
});``

### 4. Dynamic DOM Manipulation
The DOM (Document Object Model) is dynamically updated to reflect user input. Elements in the HTML document are accessed and modified using JavaScript to display or update user information.

``javascript
document.getElementById("first-name").textContent = userInfo.firstName;
document.getElementById("last-name").textContent = userInfo.lastName;
// ...``

### 5. Function Declarations
The application is organized into functions for better code structure and reusability. The storeUserInfo function handles the process of gathering user input and storing it in localStorage.

``javascript
function storeUserInfo() {
    // ...
}``
These technical features collectively contribute to the functionality and interactivity of the web application, providing users with a seamless experience for inputting, storing, and managing their personal information.


