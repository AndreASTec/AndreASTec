<svg width="860" height="280" viewBox="0 0 860 280" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <style>
      @keyframes moveGrid {
        0%   { transform: translate(0px, 0px); }
        100% { transform: translate(40px, 40px); }
      }
      @keyframes fadeIn {
        from { opacity: 0; transform: translateY(10px); }
        to   { opacity: 1; transform: translateY(0); }
      }
      @keyframes blink {
        0%, 100% { opacity: 1; }
        50%       { opacity: 0; }
      }
      @keyframes glow {
        0%, 100% { filter: drop-shadow(0 0 4px #00ff41); }
        50%       { filter: drop-shadow(0 0 12px #00ff41); }
      }
      .grid-move  { animation: moveGrid 4s linear infinite; }
      .name-text  { animation: fadeIn 1s ease forwards, glow 3s ease-in-out infinite 1s; opacity: 0; }
      .sub-text   { animation: fadeIn 1s ease 0.4s forwards; opacity: 0; }
      .sub-text2  { animation: fadeIn 1s ease 0.7s forwards; opacity: 0; }
      .cursor     { animation: blink 1s step-end infinite; }
    </style>

    <!-- Small cell grid -->
    <pattern id="cell" width="40" height="40" patternUnits="userSpaceOnUse">
      <path d="M 40 0 L 0 0 0 40" fill="none" stroke="#00ff41" stroke-width="0.6" opacity="1"/>
    </pattern>

    <!-- Larger accent grid -->
    <pattern id="block" width="200" height="200" patternUnits="userSpaceOnUse">
      <rect width="200" height="200" fill="url(#cell)"/>
      <path d="M 200 0 L 0 0 0 200" fill="none" stroke="#00ff41" stroke-width="1.5" opacity="1"/>
    </pattern>

    <!-- Fade-to-dark vignette -->
    <radialGradient id="vignette" cx="50%" cy="50%" r="70%">
      <stop offset="0%"   stop-color="#0d1117" stop-opacity="0"/>
      <stop offset="100%" stop-color="#0d1117" stop-opacity="0.82"/>
    </radialGradient>

    <!-- Top/bottom fade -->
    <linearGradient id="topFade" x1="0" y1="0" x2="0" y2="1">
      <stop offset="0%"   stop-color="#0d1117" stop-opacity="0.6"/>
      <stop offset="25%"  stop-color="#0d1117" stop-opacity="0"/>
      <stop offset="75%"  stop-color="#0d1117" stop-opacity="0"/>
      <stop offset="100%" stop-color="#0d1117" stop-opacity="0.6"/>
    </linearGradient>

    <clipPath id="bounds">
      <rect width="860" height="280"/>
    </clipPath>
  </defs>

  <!-- Background -->
  <rect width="860" height="280" fill="#0d1117"/>

  <!-- Animated grid layer -->
  <g clip-path="url(#bounds)">
    <g class="grid-move">
      <rect x="-40" y="-40" width="940" height="360" fill="url(#block)" opacity="0.18"/>
      <rect x="-40" y="-40" width="940" height="360" fill="url(#cell)"  opacity="0.07"/>
    </g>
  </g>

  <!-- Vignette overlay -->
  <rect width="860" height="280" fill="url(#vignette)"/>
  <rect width="860" height="280" fill="url(#topFade)"/>

  <!-- Horizontal accent line -->
  <line x1="200" y1="175" x2="660" y2="175" stroke="#00ff41" stroke-width="0.6" opacity="0.4"/>

  <!-- Content -->
  <text
    class="name-text"
    x="430" y="138"
    text-anchor="middle"
    font-family="'Courier New', Courier, monospace"
    font-size="42"
    font-weight="bold"
    fill="#00ff41"
    letter-spacing="4"
  >André</text>

  <text
    class="sub-text"
    x="430" y="162"
    text-anchor="middle"
    font-family="'Courier New', Courier, monospace"
    font-size="13"
    fill="#58a6ff"
    letter-spacing="1.5"
  >Desenvolvimento de Sistemas · Etec Sales Gomes</text>

  <text
    class="sub-text2"
    x="430" y="200"
    text-anchor="middle"
    font-family="'Courier New', Courier, monospace"
    font-size="11"
    fill="#8b949e"
    letter-spacing="0.5"
  >estagiário · dev júnior · web · back-end</text>

  <!-- Blinking cursor -->
  <text
    class="cursor"
    x="438" y="228"
    text-anchor="middle"
    font-family="'Courier New', Courier, monospace"
    font-size="16"
    fill="#00ff41"
    opacity="0.7"
  >▊</text>
</svg>
