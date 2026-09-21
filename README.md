<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Love Alarm ♡</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@400;500;600;700&display=swap');

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    min-height: 100vh;
    background: #080604;
    color: white;
    font-family: 'Cormorant Garamond', Georgia, serif;
    overflow: hidden;
}

.page {
    position: absolute;
    inset: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 25px;
    opacity: 0;
    visibility: hidden;
    transform: scale(1.03);
    transition: opacity 1s ease, transform 1s ease, visibility 1s;
}

.page.active {
    opacity: 1;
    visibility: visible;
    transform: scale(1);
}

.background {
    position: absolute;
    inset: 0;
    background:
        radial-gradient(circle at 50% 45%, rgba(255, 190, 40, 0.12), transparent 35%),
        radial-gradient(circle at 20% 80%, rgba(255, 170, 0, 0.08), transparent 30%),
        linear-gradient(135deg, #080604, #151006, #050403);
    z-index: -2;
}

.glow {
    position: absolute;
    width: 350px;
    height: 350px;
    border-radius: 50%;
    background: rgba(255, 193, 7, 0.08);
    filter: blur(80px);
    z-index: -1;
}

.heart {
    font-size: 100px;
    animation: heartbeat 1.3s infinite;
    filter: drop-shadow(0 0 20px rgba(255, 193, 7, 0.45));
}

@keyframes heartbeat {
    0%, 100% { transform: scale(1); }
    15% { transform: scale(1.12); }
    30% { transform: scale(1); }
    45% { transform: scale(1.08); }
}

.content {
    width: min(90%, 650px);
    text-align: center;
    position: relative;
    z-index: 5;
}

.alarm-title {
    margin-top: 30px;
    font-size: clamp(25px, 6vw, 43px);
    letter-spacing: 3px;
    color: #f4c542;
    text-shadow: 0 0 15px rgba(244, 197, 66, 0.35);
    font-weight: 600;
    line-height: 1.6;
}

.flower {
    position: absolute;
    font-size: 35px;
    animation: floatFlower linear infinite;
    opacity: 0.85;
    pointer-events: none;
    z-index: 1;
}

@keyframes floatFlower {
    from {
        transform: translateY(110vh) rotate(0deg);
        opacity: 0;
    }
    15% { opacity: 0.9; }
    85% { opacity: 0.9; }
    to {
        transform: translateY(-15vh) rotate(360deg);
        opacity: 0;
    }
}

.flower:nth-of-type(1) {
    left: 8%;
    animation-duration: 9s;
    animation-delay: 0s;
}

.flower:nth-of-type(2) {
    left: 25%;
    animation-duration: 12s;
    animation-delay: 3s;
}

.flower:nth-of-type(3) {
    left: 48%;
    animation-duration: 10s;
    animation-delay: 1s;
}

.flower:nth-of-type(4) {
    left: 70%;
    animation-duration: 13s;
    animation-delay: 4s;
}

.flower:nth-of-type(5) {
    left: 88%;
    animation-duration: 11s;
    animation-delay: 2s;
}

.message-box {
    background: rgba(20, 14, 5, 0.72);
    border: 1px solid rgba(244, 197, 66, 0.35);
    border-radius: 22px;
    padding: 35px 28px;
    box-shadow:
        0 0 35px rgba(244, 197, 66, 0.08),
        inset 0 0 30px rgba(255, 190, 30, 0.025);
    backdrop-filter: blur(8px);
}

.message-box p {
    font-size: clamp(16px, 4vw, 19px);
    line-height: 1.8;
    color: #eee8dc;
    margin-bottom: 20px;
}

.message-box p:last-child {
    margin-bottom: 0;
}

.signature {
    color: #f4c542 !important;
    font-style: italic;
    margin-top: 25px;
}

.next-button {
    margin-top: 35px;
    width: 58px;
    height: 58px;
    border-radius: 50%;
    border: 1px solid rgba(244, 197, 66, 0.55);
    background: rgba(244, 197, 66, 0.08);
    color: #f4c542;
    font-size: 28px;
    cursor: pointer;
    transition: 0.35s ease;
}

.next-button:hover {
    transform: translateX(5px) scale(1.08);
    background: rgba(244, 197, 66, 0.18);
    box-shadow: 0 0 25px rgba(244, 197, 66, 0.2);
}

.yellow-page .content {
    max-width: 700px;
}

.yellow-title {
    font-size: clamp(30px, 7vw, 48px);
    color: #f4c542;
    margin-bottom: 25px;
    text-shadow: 0 0 18px rgba(244, 197, 66, 0.3);
}

.final-heart {
    font-size: 75px;
    margin-bottom: 25px;
    animation: heartbeat 1.3s infinite;
    filter: drop-shadow(0 0 20px rgba(255, 193, 7, 0.45));
}

.final-text {
    font-size: clamp(28px, 7vw, 48px);
    color: #f4c542;
    line-height: 1.3;
}

.small-text {
    margin-top: 20px;
    color: #d9d1c0;
    font-size: 16px;
}
</style>
</head>

<body>

<div class="background"></div>
<div class="glow"></div>

<section class="page active" id="page1">
    <div class="content">
        <div class="heart">💛</div>

        <div class="alarm-title">
            RACHEL'S LOVE ALARM HAS RUNG
        </div>

        <button class="next-button" onclick="nextPage(2)">→</button>
    </div>
</section>

<section class="page yellow-page" id="page2">

    <div class="flower">🌼</div>
    <div class="flower">🌼</div>
    <div class="flower">🌼</div>
    <div class="flower">🌼</div>
    <div class="flower">🌼</div>

    <div class="content">
        <div class="yellow-title">🌼</div>

        <div class="message-box">
            <p>
                Bueno, ya que hoy se regalan flores amarillas a las personas que queremos tener cerca. Supongo que era bastante obvio a quién iban estas.
            </p>

            <p>
                No necesitaba una fecha para regalarte flores, pero teniendo una excusa, tampoco iba a desperdiciarla.
            </p>

            <p>
                La verdad es que no tengo demasiado que decirte, simplemente quería aprovechar la ocasión. Así que feliz día de las flores amarillas, Rachel, te amo y así.
            </p>

            <p class="signature">
                — Con amor: Ryan
            </p>
        </div>

        <button class="next-button" onclick="nextPage(3)">→</button>
    </div>
</section>

<section class="page" id="page3">
    <div class="content">
        <div class="final-heart">💛</div>

        <div class="final-text">
            Feliz día de las<br>
            flores amarillas.
        </div>

        <div class="small-text">🌼</div>
    </div>
</section>

<script>
function nextPage(number) {
    document.querySelectorAll('.page').forEach(page => {
        page.classList.remove('active');
    });

    document.getElementById('page' + number).classList.add('active');
}
</script>

</body>
</html>
