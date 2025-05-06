<!DOCTYPE html>
<html lang="mn">
<head>
    <meta charset="UTF-8">
    <title>Болзооны урилга</title>
    <style>
        body {
            background: #fff0f5;
            font-family: 'Arial Rounded MT Bold', sans-serif;
            color: #444;
            padding: 30px;
            max-width: 700px;
            margin: auto;
            text-align: center;
        }
        h1 {
            color: #d2649a;
            font-size: 2.5em;
        }
        .question {
            display: none;
            margin-bottom: 25px;
        }
        .question.active {
            display: block;
        }
        button {
            background-color: #d2649a;
            color: white;
            border: none;
            padding: 12px 24px;
            margin: 10px;
            border-radius: 20px;
            font-size: 1em;
            cursor: pointer;
        }
        button:hover {
            background-color: #b94f87;
        }
        select {
            padding: 10px;
            font-size: 1em;
            margin-top: 10px;
        }
        .final-message {
            font-size: 1.4em;
            color: #ff66a3;
            margin-top: 30px;
        }
        img {
            width: 150px;
            margin: 20px auto;
        }
    </style>
</head>
<body>
    <h1>Сайн уу, миний гүнжээ! 💖</h1>
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3f/Heart_coraz%C3%B3n.svg/1024px-Heart_coraz%C3%B3n.svg.png" alt="Love Image">

    <div class="question active" id="q1">
        <p>Болзоонд явах уу надтай? 🥺💌</p>
        <button onclick="answerQ1(true)">Тийм ээ!</button>
        <button onclick="answerQ1(false)">Үгүй ээ</button>
    </div>

    <div class="question" id="q2">
        <p>Ямар төрлийн болзоог сонгох вэ? 🌸</p>
        <select id="dateType" onchange="showOptions()">
            <option value="">-- Сонгох --</option>
            <option value="cinema">Кино театр</option>
            <option value="mountain">Ууланд гарах</option>
            <option value="park">Парк орох</option>
            <option value="jump">Jump</option>
            <option value="gamezone">Тоглоомын газар</option>
        </select>
    </div>

    <div class="question" id="cinemaOptions">
        <p>Кино театр:</p>
        <select>
            <option>Shangri-La</option>
            <option>Urgoo</option>
            <option>Gegeenten</option>
            <option>Kaidu World</option>
        </select>
        <p>Кино:</p>
        <select>
            <option>Holy Night</option>
            <option>Until Dawn</option>
            <option>Minecraft</option>
            <option>Warfare</option>
            <option>Бусад</option>
        </select>
        <button onclick="finish()">Сонголоо хийлээ</button>
    </div>

    <div class="question" id="jumpOptions">
        <p>Jump байршил:</p>
        <select>
            <option>Хан-Уул Emart</option>
            <option>Хорооллын Emart</option>
        </select>
        <button onclick="finish()">Сонголоо хийлээ</button>
    </div>

    <div class="question" id="gamezoneOptions">
        <p>Тоглоомын газар:</p>
        <select>
            <option>Adventure Zone</option>
            <option>Kaidu World</option>
            <option>PlayStation тоглоомын газар</option>
            <option>PC тоглоомын газар</option>
            <option>Бильярд</option>
            <option>Bowling</option>
            <option>Arcade</option>
            <option>Board Game</option>
        </select>
        <button onclick="finish()">Сонголоо хийлээ</button>
    </div>

    <div class="final-message question" id="finalMessage">
        <p>Сонголтоо хадгаллаа! 💌<br>Дараа уулзъя, миний хайртай гүнжээ! 💗</p>
    </div>

    <div class="final-message question" id="sadMessage">
        <p>Тэгвэл би гомдлоо... 😢🥺</p>
    </div>

    <script>
        function show(id) {
            const elements = document.querySelectorAll('.question');
            elements.forEach(el => el.classList.remove('active'));
            document.getElementById(id).classList.add('active');
        }

        function answerQ1(go) {
            if (go) {
                show('q2');
            } else {
                show('sadMessage');
            }
        }

        function showOptions() {
            const val = document.getElementById('dateType').value;
            if (val === "cinema") {
                show('cinemaOptions');
            } else if (val === "jump") {
                show('jumpOptions');
            } else if (val === "gamezone") {
                show('gamezoneOptions');
            } else {
                show('finalMessage');
            }
        }

        function finish() {
            show('finalMessage');
            :>
