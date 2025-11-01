<html lang="nl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Het Woord Gedeeld — Bijb 2.0</title>
  <style>
    body { margin:0; font-family:sans-serif; background:#f6fafc; color:#374151; }
    header, footer { background:#2e3a8c; color:white; padding:1rem; text-align:center; }
    .container { max-width:1000px; margin:auto; padding:1rem; display:flex; gap:2rem; flex-wrap:wrap; }
    .sidebar { flex:1 1 250px; background:white; padding:1rem; border-radius:8px; border:1px solid #e6eef8; }
    .content { flex:3 1 600px; background:white; padding:1rem; border-radius:8px; border:1px solid #e6eef8; }
    nav a { display:block; margin:.5rem 0; text-decoration:none; color:#374151; font-weight:600; }
    nav a:hover { color:#2e3a8c; }
    .section { margin-top:1rem; padding:1rem; background:#fbfdff; border-radius:6px; border:1px solid #e6eef8; }
    button { background:#2e3a8c; color:white; border:none; padding:.5rem 1rem; border-radius:6px; cursor:pointer; }
    button:disabled { opacity:0.6; cursor:not-allowed; }
    .muted { color:#6b7280; font-size:.9rem; }
    textarea { width:100%; padding:.5rem; margin-top:.5rem; border:1px solid #ccc; border-radius:6px; font-size:.9rem; }
  </style>
</head>
<body>
  <header><h1>Het Woord Gedeeld — Bijb 2.0</h1></header>
  <div class="container">
    <aside class="sidebar">
      <h2>Geloofsrichtingen</h2>
      <nav id="faith-nav"></nav>
    </aside>
    <main class="content" id="main-content">
      <h2>Welkom</h2>
      <p>Kies links een geloofsrichting om uitleg en een AI-verhaal te ontvangen van Bijb.</p>
    </main>
  </div>
  <footer>&copy; 2025 Het Woord Gedeeld — AI door Bijb</footer>

  <script>
    const API_KEY = "AIzaSyDYCpPo7jRa8vJDbH3P5R1eopFo5koGPAo";
    const API_URL = "https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-09-2025:generateContent?key=";

    const faiths = {
      katholiek: "Rooms-Katholieke traditie",
      protestants: "Protestantse traditie",
      islam: "Islamitische traditie",
      jodendom: "Joodse traditie",
      oosters: "Oosters-Orthodoxe traditie"
    };

    let bijbMemory = [];

    const faithNav = document.getElementById("faith-nav");
    const mainContent = document.getElementById("main-content");

    Object.entries(faiths).forEach(([id, name]) => {
      const link = document.createElement("a");
      link.href = "#";
      link.textContent = name;
      link.addEventListener("click", e => {
        e.preventDefault();
        renderFaith(id, name);
      });
      faithNav.appendChild(link);
    });

    function renderFaith(id, name) {
      mainContent.innerHTML = `
        <h2>${name}</h2>
        <p class="muted">Hieronder vind je uitleg over de ${name.toLowerCase()} en kun je een historisch bijbelverhaal genereren via Bijb.</p>
        <div class="section">
          <h3>Vertel Bijb wat je belangrijk vindt</h3>
          <textarea id="user-input" rows="3" placeholder="Bijv: Ik wil verhalen over vergeving, in poëtische stijl..."></textarea>
          <button id="remember-btn">Onthoud dit</button>
        </div>
        <div class="section">
          <h3>Vraag Bijb om een historisch verhaal</h3>
          <button id="generate-btn">Genereer verhaal</button>
          <div id="ai-output" class="muted" style="margin-top:1rem;"></div>
        </div>
      `;

      document.getElementById("remember-btn").addEventListener("click", () => {
        const input = document.getElementById("user-input").value.trim();
        if (input) {
          bijbMemory.push(input);
          alert("Bijb heeft het onthouden.");
        }
      });

      const btn = document.getElementById("generate-btn");
      const output = document.getElementById("ai-output");

      btn.addEventListener("click", async () => {
        btn.disabled = true;
        btn.textContent = "Bijb denkt na...";
        output.textContent = "";

        const context = bijbMemory.length > 0 ? `Gebruiker heeft eerder gezegd: ${bijbMemory.join(" | ")}` : "Geen extra voorkeuren opgegeven.";
        const prompt = `
Je bent Bijb, een AI-verhalenverteller. ${context}
Vertel nu een historisch bijbelverhaal dat past bij de ${name}. Gebruik ongeveer 300 woorden, in hedendaags Nederlands, met nadruk op de spirituele betekenis en historische context.
        `;

        try {
          const response = await fetch(API_URL + API_KEY, {
            method: "POST",
            headers: { "Content-Type": "application/json" },
            body: JSON.stringify({
              contents: [{ role: "user", parts: [{ text: prompt }] }]
            })
          });
          const result = await response.json();
          const story = result.candidates?.[0]?.content?.parts?.[0]?.text || "Geen verhaal ontvangen.";
          output.textContent = story;
        } catch (e) {
          output.textContent = "Er ging iets mis bij het ophalen van het verhaal.";
        } finally {
          btn.disabled = false;
          btn.textContent = "Genereer verhaal";
        }
      });
    }
  </script>
</body>
</html>
