<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>I Love youuu</title>
    <style>
        body {
            background-color: skyblue;
            text-align: center;
            font-family: "Times New Roman", serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            position: relative;
        }
        .container {
            text-align: center;
        }
        .question {
            font-size: 28px;
            margin-bottom: 20px;
        }
        .option {
            display: inline-block;
            background-color: white;
            padding: 15px 25px;
            border-radius: 20px;
            margin: 10px;
            font-size: 20px;
            cursor: pointer;
            box-shadow: 2px 2px 5px gray;
        }
        .hearts {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            overflow: hidden;
            pointer-events: none;
        }
        .heart {
            position: absolute;
            color: red;
            font-size: 30px;
            animation: float 5s infinite;
        }
        @keyframes float {
            0% { transform: translateY(100vh); opacity: 1; }
            100% { transform: translateY(-10vh); opacity: 0; }
        }
        .hidden {
            display: none;
        }
        .emoji {
            font-size: 167px;
            cursor: pointer;
            margin-bottom: 15px;
        }
        .click-text {
            font-size: 24px;
            font-family: "Times New Roman", serif;
        }
        .poem-container {
            max-width: 600px;
            margin: auto;
            text-align: left;
            font-size: 24px;
            line-height: 1.5;
            overflow-y: auto; /* Allows scrolling if needed */
            max-height: 80vh; /* Prevents overflow */
            padding: 20px;
        }
        .no-hearts {
            display: none;
        }
    </style>
</head>
<body>

    <div class="hearts" id="hearts"></div>

    <!-- First screen -->
    <div id="questionScreen" class="container">
        <div class="question">Will you be my Valentine?</div>
        <div class="option" onclick="nextScreen()">haan</div>
        <div class="option" onclick="nextScreen()">HAAN</div>
    </div>

    <!-- Second screen with Smaller 💌 emoji -->
    <div id="emojiScreen" class="container hidden">
        <div class="emoji" onclick="openMessage()">💌</div>
        <div class="click-text">Click on the heart!</div>
    </div>

    <!-- Love Letter Screen with Poem -->
    <div id="loveMessage" class="container hidden">
        <div class="poem-container">
            <p>I'll forever be grateful,<br>
            To destiny's will<br>
            For I saw the guy I'd love for life,<br>
            On the ninth of April.<br><br>

            A face so pretty<br>
            With intoxicating eyes<br>
            My mind said hello,<br>
            My heart felt shy<br>
            The same old compliments<br>
            I'll repeat and revise<br>
            With paragraphs and poems<br>
            For the rest of our lives.<br><br>

            I started listening to your voice<br>
            I haven't stopped ever since,<br>
            It wakes me up, it puts me to sleep<br>
            It brings me a lot of peace.<br>
            From recorded voice notes<br>
            To singing with you,<br>
            Life feels like a comfort playlist,<br>
            Life is painted sky blue.<br><br>

            You pull me closer,<br>
            My head on your heart,<br>
            Your essence, it holds me tight enough<br>
            Even when we're apart.<br>
            In monsoon rains and sweaty summers,<br>
            My jackets smell like heaven and above<br>
            Deep embedded in my skin,<br>
            Everyday, I smell of your love.<br><br>

            When I can't hold you in my arms,<br>
            I hold a warm cup of tea.<br>
            I tell myself there indeed is,<br>
            An invisible string tying you to me.<br>
            Your sweet taste of love<br>
            Puts me under cotton candy skies,<br>
            Your constant care and adoration<br>
            Fills my heart with giggles and smiles.<br><br>

            Hugging you is like<br>
            Rushing back home,<br>
            Your hand in mine<br>
            Will always be my comfort zone.<br>
            Help me cross the road,<br>
            Wipe my tears away<br>
            Plant a soft kiss on my cheek,<br>
            See how it makes my day..<br><br>

            I see you, I hear you,<br>
            I smell you all around;<br>
            I taste you, I touch you,<br>
            With no limits bound.<br>
            With all my soul,<br>
            And the entirety of my life,<br>
            I love you from the core of my heart,<br>
            More than just senses five.</p>
        </div>
    </div>

    <script>
        function nextScreen() {
            document.getElementById("questionScreen").classList.add("hidden");
            document.getElementById("emojiScreen").classList.remove("hidden");
        }

        function openMessage() {
            document.getElementById("emojiScreen").classList.add("hidden");
            document.getElementById("loveMessage").classList.remove("hidden");
            document.getElementById("hearts").classList.add("no-hearts"); // Remove hearts on last screen
        }

        function createHearts() {
            for (let i = 0; i < 20; i++) {
                let heart = document.createElement("div");
                heart.classList.add("heart");
                heart.innerHTML = "❤";
                heart.style.left = Math.random() * 100 + "vw";
                heart.style.animationDuration = (Math.random() * 3 + 2) + "s";
                document.querySelector(".hearts").appendChild(heart);
            }
        }
        createHearts();
    </script>

</body>
</html>
