# Quiz CLI

## Project Overview

Quiz CLI is an interactive command-line quiz game built with Node.js and ES modules. It loads quiz questions from a JSON file, lets the user choose a category and question count, and then runs a terminal-based quiz with progress feedback, scoring, explanations, and a replay loop.

This codebase is a compact example of modern Node.js development. It demonstrates file system access, modular JavaScript, asynchronous control flow, and user interaction through the built-in `readline` API.

## Features

- Interactive terminal quiz experience
- Category selection from grouped question sets
- Choice between all questions, 3 questions, or 5 questions when available
- Randomized question order using a Fisher-Yates shuffle
- Immediate correctness feedback after each answer
- Explanations shown for questions when provided
- Progress indicator for the current quiz session
- Final score summary with a performance message
- Option to replay and choose a new category
- ANSI color output without external dependencies

## Setup Instructions

### Prerequisites

- Node.js **18.0.0 or later**
- A terminal that supports standard interactive input

### Installation

```bash
# Clone the repository
git clone <repository-url>
cd test-app

# Install dependencies
npm install
```

### Run the application

```bash
npm start
```

This runs the CLI entry point defined in `package.json` and launches the quiz in your terminal.

### Run tests

```bash
npm test
```

The project currently uses Node's built-in test runner (`node --test`).

## Usage Examples

Start the quiz:

```bash
npm start
```

Typical interaction flow:

1. Choose a quiz category
2. Select how many questions to answer
3. Enter the number corresponding to your answer
4. Review the final score and explanations
5. Decide whether to play again

Example terminal session:

```text
Choose a category:

  1. JavaScript Basics
  2. Node.js Fundamentals
  3. General Programming

Your choice (enter number): 1

How many questions?

  1. All questions
  2. 3 questions
  3. 5 questions

Your choice (enter number): 2
```

## File Structure

```text
.
├── index.js              # Application entry point; loads questions and runs the main quiz loop
├── package.json           # Project metadata, scripts, module type, and Node.js engine requirement
├── data/
│   └── questions.json     # Quiz content grouped by category
└── src/
    ├── colors.js         # ANSI color helpers for terminal styling
    ├── input.js          # Readline-based prompt, selection, confirmation, and pause helpers
    └── quiz.js           # Quiz class, scoring logic, progress display, and results summary
```

## Additional Relevant Details

- The application uses **ES modules** (`"type": "module"` in `package.json`).
- The entry file is `index.js`, and it uses a shebang (`#!/usr/bin/env node`) so it can be executed as a CLI script in compatible environments.
- Quiz data is stored in `data/questions.json`, making it easy to add or modify categories and questions without changing the application logic.
- `src/quiz.js` shuffles questions before each run so the quiz order is not always the same.
- `src/input.js` uses Node's built-in `readline` module for all terminal prompts.
- `src/colors.js` provides color output without requiring third-party packages.
- The repository license is **MIT**.

## Contributing

Contributions can be made by extending the question bank, improving terminal UX, adding more quiz categories, or enhancing test coverage.

A typical workflow is:

1. Create a branch for your change
2. Make and test your updates
3. Open a pull request

## License

This project is licensed under the **MIT License**.
