# Quizzler – True/False Quiz App

GUI quiz application built with Python, Tkinter and an online trivia API.

## Main features

- Fetches multiple-choice data from the Open Trivia DB API in `data.py` and converts it into a list of `Question` objects.
- Presents each question as a **True / False** prompt in a clean Tkinter window.
- Keeps track of score and updates it live in the top-right corner.
- Shows visual feedback:
  - Green background for correct answers.
  - Red background for incorrect answers.
- Uses a short delay before automatically loading the next question.
- Disables the True / False buttons and shows a final message when there are no questions left.

## What I learned

- Structuring a small project across multiple files and modules.
- Designing graphical user interfaces with Tkinter (windows, labels, canvas, buttons, layout).
- Using classes to separate responsibilities:
  - `Question` for question data.
  - `QuizBrain` for quiz logic, score and progression.
  - `QuizInterface` for all UI rendering and interaction.
- Making HTTP requests to an external API using `requests` and parsing JSON responses.
- Using HTML unescaping to display clean question text.
- Providing clear user feedback and handling the end-of-quiz state.

## Project structure

- `main.py` – entry point; builds the question bank from `question_data` and starts the quiz UI.
- `question_model.py` – defines the `Question` class (text + answer).
- `quiz_brain.py` – contains the `QuizBrain` class that:
  - Stores the list of questions.
  - Tracks the current question number and score.
  - Provides the next question text.
  - Checks whether the user’s answer is correct.
- `ui.py` – defines the `QuizInterface` class that:
  - Creates the Tkinter window.
  - Displays the current question.
  - Shows the score.
  - Handles the ✅ (True) and ❌ (False) buttons, feedback colours and end-of-quiz message.
- `data.py` – fetches question data from the Open Trivia DB API and exposes it as `question_data`.
- `images/` – contains the button images used in the interface (for example `true.png` and `false.png`).

## How to run

1. Make sure you have Python 3 installed.
2. Install the required package:

   `pip install requests`

3. From the project folder, run:

   `python main.py`

A window will open showing a True / False quiz. Click the buttons to answer each question. Your score will update as you progress, and when you reach the end of the question list the app will show a final message and disable the buttons.
