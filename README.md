<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Minta Maaf ke Kamu</title>
  <style>
    :root {
      --bg: #ffffff;
      --text: #111111;
      --accent: #111111;
      font-family: "Inter", system-ui, -apple-system, "Segoe UI", Roboto, Arial;
    }
    body {
      margin: 0;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      background: linear-gradient(180deg, #fff, #f7f7f7);
      color: var(--text);
    }
    .card {
      width: clamp(300px, 70vw, 420px);
      background: rgba(255, 255, 255, 0.9);
      border-radius: 16px;
      padding: 28px;
      box-shadow: 0 6px 20px rgba(12,12,12,0.08);
      text-align: center;
      transition: all 0.4s ease;
    }
    h1 {
      margin: 0 0 12px;
      font-size: 28px;
    }
    p {
      margin: 0 0 18px;
      color: #444;
      line-height: 1.5;
    }
    input {
      width: 100%;
      padding: 10px 12px;
      border-radius: 10px;
      border: 1px solid #ddd;
      font-size: 16px;
      box-sizing: border-box;
    }
    .btn {
      display: inline-block;
      margin-top: 12px;
      padding: 10px 18px;
      border-radius: 999px;
      border: none;
      background: var(--accent);
      color: white;
      font-weight: 600;
      cursor: pointer;
      transition: background 0.3s;
    }
    .btn:hover {
      background: #222;
    }
    .btn.secondary {
      background: #eee;
      color: #111;
      border: 1px solid #ddd;
    }
    footer {
      margin-top: 18px;
      font-size: 13px;
      color: #666;
    }
    a.credits {
      color: #0a66ff;
      text-decoration: none;
    }
  </style>
</head>
<body>
  <div class="card" id="step1">
    <h1>Hai kamu</h1>
    <p>Boleh aku tahu nama panggilan manis kamu?</p>
    <input id="nickname" placeholder="Masukkan nama (contoh: Adin)" maxlength="40" />
    <br>
    <button class="btn" id="nextBtn">Lanjut</button>
    <footer>
      Made by <a class="credits" href="https://www.tiktok.com/@alenn.engineer.stress" target="_blank">@alenn.engineer.stress</a>
    </footer>
  </div>

  <div class="card" id="step2" style="display:none;">
    <h1>Aku minta maaf 😔</h1>
    <p id="apologyText"></p>
    <button class="btn" id="yesBtn">Maafin ✔️</button>
    <button class="btn secondary" id="noBtn">Enggak ❌</button>
    <p id="result" style="margin-top:16px;font-weight:600;"></p>
    <footer>
      Made by <a class="credits" href="https://www.tiktok.com/@alenn.engineer.stress" target="_blank">@alenn.engineer.stress</a>
    </footer>
  </div>

  <script>
    const step1 = document.getElementById("step1");
    const step2 = document.getElementById("step2");
    const nextBtn = document.getElementById("nextBtn");
    const nicknameInput = document.getElementById("nickname");
    const apologyText = document.getElementById("apologyText");
    const yesBtn = document.getElementById("yesBtn");
    const noBtn = document.getElementById("noBtn");
    const result = document.getElementById("result");

    nextBtn.addEventListener("click", () => {
      const name = nicknameInput.value.trim();
      if (name === "") {
        alert("Isi dulu namanya ya 🥺");
        return;
      }
      apologyText.innerHTML = `Aku beneran gak bermaksud bikin kamu kesel, <strong>${name}</strong>.`;
      step1.style.display = "none";
      step2.style.display = "block";
    });

    yesBtn.addEventListener("click", () => {
      result.textContent = "Terima kasih 💖 Aku janji jadi lebih baik.";
      yesBtn.disabled = true;
      noBtn.disabled = true;
    });

    noBtn.addEventListener("click", () => {
      result.textContent = "Aku ngerti... Maaf ya. Aku bakal kasih kamu ruang dulu 😔";
      yesBtn.disabled = true;
      noBtn.disabled = true;
    });
  </script>
</body>
</html>
