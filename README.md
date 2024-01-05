# Astroworld's Adventure Le Manga
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Compte à rebours</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

<div class="countdown">
  <h1>Compte à rebours</h1>
  <div id="timer">
    <span id="days"></span>
    <span id="hours"></span>
    <span id="minutes"></span>
    <span id="seconds"></span>
  </div>
</div>

<script src="script.js"></script>
</body>
</html>

// Date de fin du compte à rebours
const countDownDate = new Date("2024-01-06T17:00:00").getTime();

const countdown = setInterval(function() {
  const now = new Date().getTime();
  const distance = countDownDate - now;

  const days = Math.floor(distance / (1000 * 60 * 60 * 24));
  const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
  const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
  const seconds = Math.floor((distance % (1000 * 60)) / 1000);

  document.getElementById("days").innerText = days + "j ";
  document.getElementById("hours").innerText = hours + "h ";
  document.getElementById("minutes").innerText = minutes + "m ";
  document.getElementById("seconds").innerText = seconds + "s ";

  if (distance < 0) {
    clearInterval(countdown);
    document.getElementById("timer").innerHTML = "<h2>Temps écoulé !</h2>";
  }
}, 1000);
