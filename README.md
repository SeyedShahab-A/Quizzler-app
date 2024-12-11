
# Quizzler - The Interactive Quiz App
#### Video Demo:  <URL https://youtu.be/DAr3SiAG0E8>

Quizzler is a Python-based True/False quiz application designed to test your knowledge on a variety of topics in an engaging and interactive way. The app fetches trivia questions dynamically from the [Open Trivia Database (OpenTDB)](https://opentdb.com/), ensuring that every quiz session is unique. With its intuitive graphical user interface (GUI) built using `tkinter`, Quizzler offers an accessible and fun experience for users of all ages.

---

## Overview

Quizzler leverages a combination of Python modules and APIs to create an interactive quiz platform. The app’s core functionalities include fetching questions in real time, presenting them through a user-friendly interface, and providing immediate feedback on answers. Users can track their progress with a live score displayed throughout the quiz. 

This project showcases the following key concepts:
1. **Object-Oriented Programming (OOP):** The app uses classes such as `QuizBrain` and `Question` to organize logic and handle the flow of the quiz.
2. **API Integration:** Trivia questions are fetched dynamically from OpenTDB, ensuring the app offers fresh and varied content.
3. **GUI Development:** The `tkinter` library is used to create an interactive and visually appealing application.

---

## Features

1. **Dynamic Question Loading:** 
   - The app fetches 10 True/False questions from the OpenTDB API each time it is run.
   - Questions come from a wide range of topics, ensuring variety and entertainment.
   
2. **Interactive User Interface:**
   - Users interact with the app through a GUI featuring buttons for "True" and "False" responses.
   - Questions are displayed on a canvas, with real-time updates for each new question.

3. **Live Score Tracking:**
   - The user’s score is updated immediately upon answering each question.
   - A score label keeps users informed of their progress.

4. **Visual Feedback:**
   - The app changes the background color of the question canvas to indicate whether the user’s answer is correct (green) or incorrect (red).

5. **End-of-Quiz Summary:**
   - When all questions are answered, the app displays a message summarizing the user’s final score.
   - Buttons are disabled at the end of the quiz to prevent further interactions.

6. **Customizable Question Parameters:**
   - Users can modify the number of questions or the difficulty level by changing parameters in the code (see the **Customization** section).

---

## Installation

### Prerequisites
- Python 3.7 or higher.
- An active internet connection to fetch quiz data.

### Dependencies
The project relies on the following Python libraries:
- `tkinter`: For creating the graphical user interface. (Built into Python.)
- `requests`: For making HTTP requests to the OpenTDB API.

Install the `requests` library by running:

pip install requests

**How to Run**

1.	Clone the Repository:


`git clone <repository_url>
cd quiz_app`


2.	Ensure Dependencies Are Installed:
	  Install requests using the command above if it is not already installed.
3.	Run the Application:

`python main.py`


4.	Play the Quiz:
	 The app will open in a new window. Use the “True” and “False” buttons to answer questions.

Project Structure

```
quiz_app/
│
├── main.py              # Entry point of the application
├── question_model.py    # Defines the Question class
├── quiz_brain.py        # Handles quiz logic and score tracking
├── data.py              # Fetches trivia questions from OpenTDB API
├── ui.py                # Manages the graphical user interface
├── images/              # Contains True/False button images
│   ├── true.png
│   └── false.png
└── README.md            # Project documentation
```

**Customization**

Changing the Number of Questions

You can modify the number of questions fetched from the OpenTDB API by editing the data.py file:

```
parameters = {
    "type": "boolean",
    "amount": 10  # Adjust this number to increase or decrease the number of questions
}
```

Modifying Question Difficulty or Type

You can also adjust the difficulty level or question type by adding parameters:

```
parameters = {
    "type": "boolean",
    "amount": 10,
    "difficulty": "medium"  # Options: easy, medium, hard
}
```

**How It Works**

1.**Data Fetching**:
    	The data.py script sends a GET request to the OpenTDB API with the specified parameters (question type, number, difficulty, etc.).
    	The API returns a JSON response containing the questions, their correct answers, and additional metadata.

2.**Quiz Logic**:
    	The QuizBrain class manages the flow of the quiz. It tracks the current question, checks answers, and updates the score.
    	Questions are stored in a list as objects created from the Question class.

3.**User Interface**:
    	The ui.py script uses tkinter to create a graphical interface. This includes a canvas for displaying questions, buttons for user responses, and a score label.

4.**User Interaction**:
    	When a user clicks “True” or “False,” the app checks their answer and provides immediate feedback by changing the canvas background color.
    	The app automatically moves to the next question after a short delay.



**Credits**

  - Trivia Questions: Powered by the Open Trivia Database (OpenTDB).

**Future Improvements**

  - Multiple-Choice Questions: Add support for a wider range of question types.
  - Timer: Introduce a countdown timer to limit response time for each question.
  - High Scores: Save user scores locally or to a database for tracking and competition.
  - Mobile Compatibility: Create a mobile version of the app using a framework like Kivy.
