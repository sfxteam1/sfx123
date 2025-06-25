document.addEventListener("DOMContentLoaded", () => {
  const questions = [
    {
      text: "Can I ask something...😁🙈",
      yes: "Tquuuuuu kurripppii thathhaa😁😻!",
      no: "That's okay, sorry for disturbing... 🙃🚶🏼"
    },
    {
      text: "Are you comfortable with me? 👀🌝",
      yes: "You just made me smile too!🙈😁",
      no: "Its okkeyy...🚶🏼🙃"
    },
    {
      text: "Are you feeling better now, Kurippe🌝👀?",
      yes: "Igannne okkey ayi irnnna mathii atha rassam😁🌝",
      no: "kuripppe ankkk nthannnn pattiyeee nnnodd parayyyy..."
    },
    {
      text: "Can I be your favorite hello and hardest goodbye? 💌",
      yes: "You'll always be mine...🤍😻",
      no: "I'll work hard every day for that 🚶🏼"
    },
    {
      text: "One More Surprise 🎁<br>Click below to see something special I've prepared just for you",
      yes: "<a href='https://forms.gle/mWaT8FaBPmGWKELP9' target='_blank'>Open Surprise 🎁</a>",
      no: "You might miss something special! 💔"
    }
  ];

  let loveScore = 0;
  const timeline = document.getElementById("timeline");
  const loveCounter = document.getElementById("loveScore");
  const popup = document.getElementById("final-popup");
  const music = document.getElementById("bgMusic");
  const confettiCanvas = document.getElementById("confettiCanvas");
  const ctx = confettiCanvas.getContext("2d");

  let current = 0;

  function renderQuestion(index) {
    if (index >= questions.length) {
      popup.classList.remove("hidden");
      music.play();
      startConfetti();
      return;
    }

    const q = questions[index];
    const block = document.createElement("div");
    block.className = "question-block typewriter";
    block.innerHTML = `
      <p><strong>${q.text}</strong></p>
      <div class="button-group">
        <button onclick="answer(${index}, true)">Yes</button>
        <button onclick="answer(${index}, false)">No</button>
      </div>
      <div class="response-message" id="response-${index}"></div>
    `;
    timeline.appendChild(block);
    block.scrollIntoView({ behavior: "smooth" });
  }

  window.answer = function(index, isYes) {
    const msg = questions[index][isYes ? 'yes' : 'no'];
    const msgDiv = document.getElementById(`response-${index}`);
    msgDiv.innerHTML = msg;

    if (isYes) loveScore++;
    loveCounter.textContent = `💖 x ${loveScore}`;
    document.querySelectorAll(".question-block")[index].classList.remove("typewriter");

    setTimeout(() => {
      renderQuestion(index + 1);
    }, 1500);
  };

  document.getElementById("themeToggle").addEventListener("change", () => {
    document.body.classList.toggle("dark");
  });

  renderQuestion(current);

  function startConfetti() {
    confettiCanvas.classList.remove("hidden");
    confettiCanvas.width = window.innerWidth;
    confettiCanvas.height = window.innerHeight;

    let confettis = Array.from({ length: 200 }, () => ({
      x: Math.random() * confettiCanvas.width,
      y: Math.random() * confettiCanvas.height,
      r: Math.random() * 6 + 4,
      d: Math.random() * 10 + 10,
      color: `hsl(${Math.random() * 360}, 100%, 70%)`
    }));

    function draw() {
      ctx.clearRect(0, 0, confettiCanvas.width, confettiCanvas.height);
      confettis.forEach(c => {
        ctx.beginPath();
        ctx.arc(c.x, c.y, c.r, 0, Math.PI * 2, false);
        ctx.fillStyle = c.color;
        ctx.fill();
      });
      update();
    }

    function update() {
      confettis.forEach(c => {
        c.y += Math.sin(c.d / 10);
        c.x += Math.sin(c.d);
        if (c.y > confettiCanvas.height) {
          c.y = 0;
          c.x = Math.random() * confettiCanvas.width;
        }
      });
    }

    function loop() {
      draw();
      requestAnimationFrame(loop);
    }
    loop();
  }
});
