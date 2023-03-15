# BelizeTest
Test of ChatGPT4 Code
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Belize Quiz</title>
    <style>
        body {
            font-family: Arial, sans-serif;
        }
        .question {
            margin-bottom: 1rem;
        }
        .answer {
            display: inline-block;
            margin-right: 1rem;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1>Belize Quiz</h1>
    <div id="quiz">
        <div class="question" id="question1">
            <p>1. What is the capital city of Belize?</p>
            <span class="answer" onclick="checkAnswer(1, 1, 'A')">A. Belmopan</span>
            <span class="answer" onclick="checkAnswer(1, 2, 'B')">B. Belize City</span>
            <span class="answer" onclick="checkAnswer(1, 3, 'C')">C. San Ignacio</span>
            <span class="answer" onclick="checkAnswer(1, 4, 'D')">D. Orange Walk</span>
        </div>
        <div class="question" id="question2">
            <p>2. What is the national animal of Belize?</p>
            <span class="answer" onclick="checkAnswer(2, 1, 'A')">A. Jaguar</span>
            <span class="answer" onclick="checkAnswer(2, 2, 'B')">B. Toucan</span>
            <span class="answer" onclick="checkAnswer(2, 3, 'C')">C. Baird's Tapir</span>
            <span class="answer" onclick="checkAnswer(2, 4, 'D')">D. Scarlet Macaw</span>
        </div>
        <div class="question" id="question3">
            <p>3. What is the largest island in Belize?</p>
            <span class="answer" onclick="checkAnswer(3, 1, 'A')">A. Caye Caulker</span>
            <span class="answer" onclick="checkAnswer(3, 2, 'B')">B. Ambergris Caye</span>
            <span class="answer" onclick="checkAnswer(3, 3, 'C')">C. Turneffe Atoll</span>
            <span class="answer" onclick="checkAnswer(3, 4, 'D')">D. Glover's Reef Atoll</span>
        </div>
        <div class="question" id="question4">
            <p>4. What is the official language of Belize?</p>
            <span class="answer" onclick="checkAnswer(4, 1, 'A')">A. Spanish</span>
            <span class="answer" onclick="checkAnswer(4, 2, 'B')">B. English</span>
            <span class="answer" onclick="checkAnswer(4, 3, 'C')">C. Garifuna</span>
            <span class="answer" onclick="checkAnswer(4, 4, 'D')">D. Creole
</span>
        </div>
        <div class="question" id="question5">
            <p>5. What is the Belize Barrier Reef part of?</p>
            <span class="answer" onclick="checkAnswer(5, 1, 'A')">A. Great Barrier Reef</span>
            <span class="answer" onclick="checkAnswer(5, 2, 'B')">B. Mesoamerican Barrier Reef System</span>
            <span class="answer" onclick="checkAnswer(5, 3, 'C')">C. Coral Sea</span>
            <span class="answer" onclick="checkAnswer(5, 4, 'D')">D. Red Sea</span>
        </div>
    </div>
    <button onclick="showScore()">Show Score</button>
    <p id="score"></p>
<script>
    const correctAnswers = {
        question1: 1,
        question2: 3,
        question3: 2,
        question4: 2,
        question5: 2
    };
    let answeredQuestions = 0;
    let totalCorrectAnswers = 0;

    function checkAnswer(questionNumber, selectedAnswer, letter) {
        const questionId = 'question' + questionNumber;
        const question = document.getElementById(questionId);

        if (!question.classList.contains('answered')) {
            question.classList.add('answered');
            answeredQuestions++;

            const correctAnswer = correctAnswers[questionId];
            const answerElement = question.querySelector('.answer:nth-child(' + (selectedAnswer + 1) + ')');

            if (selectedAnswer === correctAnswer) {
                answerElement.style.color = 'green';
                totalCorrectAnswers++;
            } else {
                answerElement.style.color = 'red';
            }

            answerElement.innerHTML = letter + ". " + answerElement.innerHTML.slice(2);
        }
    }

    function showScore() {
        if (answeredQuestions === 5) {
            const percentageScore = (totalCorrectAnswers / 5) * 100;
            document.getElementById('score').innerHTML = 'Your score: ' + percentageScore + '%';
        } else {
            alert('Please answer all questions before checking your score.');
        }
    }
</script>
</body>
</html>