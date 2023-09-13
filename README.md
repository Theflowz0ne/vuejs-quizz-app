# Vue.js Quiz Application

This is a simple quiz application built using Vue.js. It allows users to take a quiz, answer questions, and see their results.

## Features

- Display of correct and incorrect answers.
- Result summary.
- Reset option to retake the quiz.

## Getting Started

Follow these steps to set up and run the project on your local machine:

1. **Clone the repository:**

   ```bash
   git clone https://github.com/your-username/vue-quiz-app.git

2. **Navigate to the project folder:**

   ```bash
   cd vue-quiz-app

3. **Install dependencies:**

   ```bash
   npm install

4. **Start the frontend and the backend (json-server on port 5000):**

   ```bash
   npm run dev
   npm run backend

## Usage
- Answer the quiz questions by selecting the options.
- Click the "Next" button to move to the next question.
- After completing the quiz, you will see a summary of your results.
- To retake the quiz, click the "Reset Quiz" button.

## Data Format

The quiz questions are stored in a JSON format. Each question object includes the following fields:

- question: The question text.
- correct_answer: The index of the correct answer in the answers array.
- selected_answer: The index of the selected answer (initially set to null).
- answers: An array of possible answers.
