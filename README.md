# AI Perception Study Model

This project implements a chat bot that responds to user inputs with pre-recorded responses loaded from a CSV file. The bot provides functionality to select responses based on different criteria, including random, good, bad, and mixed responses. The bot also supports regenerating responses and displays them with a typing animation.

## Table of Contents

1. [Features](#features)
2. [Installation](#installation)
3. [Usage](#usage)
4. [Code Structure](#code-structure)
    - [HTML](#html)
    - [CSS](#css)
    - [JavaScript](#javascript)
5. [Customization](#customization)
6. [License](#license)

## Features

- Load pre-recorded responses from a CSV file.
- Display responses based on different criteria:
  - Random responses
  - Good responses (rating >= 4)
  - Bad responses (rating <= 2)
  - Mixed responses (a mix of good and bad)
- Regenerate responses with a button click.
- Typing animation for displaying responses.
- Track the count of highlighted and underlined words.

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/chung-isaac/ai-perception-study.git
    cd ai-perception-study
    ```

2. Open `index.html` in your web browser to view and interact with the bot.

## Usage

1. Load a CSV file containing pre-recorded responses:
    - The CSV file should have the following format:
      ```csv
      id,response,rating
      1,Using visual aid is helpful for teaching students,5
      2,Would you like me to generate a lesson plan template?,4
      3,I'm sorry, I didn't understand that.,2
      ```

2. Interact with the bot:
    - Enter a message in the input field and click "Send" to see a response from the bot.
    - Click on the different buttons to switch between response criteria (Random, Good, Bad, Mixed).
    - Click "Regenerate" to generate a new set of responses based on the current criteria.

## Code Structure

### HTML

- **index.html**: Contains the structure of the chat interface and includes buttons for interaction.

### CSS

- **styles.css**: Contains styles for the chat interface and typing animation.

### JavaScript

- **script.js**: Contains the logic for loading responses, handling user input, and displaying responses with animations.

#### Code Documentation

##### parseCSV
```javascript
/**
 * Parses CSV text into an array of response objects.
 * @param {string} text - The CSV text to parse.
 * @returns {Array<Object>} - Array of response objects with id, response, and rating properties.
 */
function parseCSV(text) {
    const lines = text.split('\n').slice(1); // Assuming the first line is headers
    return lines.map(line => {
        const [id, response, rating] = line.split(',');
        return { id, response, rating: parseInt(rating, 10) };
    });
}
