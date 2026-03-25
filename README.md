## Activity Snake

<svg viewBox="0 0 520 180" width="520" height="180" xmlns="http://www.w3.org/2000/svg">
  <desc>Animated contribution snake (compact)</desc>
  <style>
    :root{
      --bg:#0d1117;
      --gridStroke:#1b1f230a;
      --snake:#8a2be2;
      --low:#01311f;
      --mid:#0f6d31;
      --high:#00c647;
      --cell:#161b22;
      --speed:14000ms;
      --cellSize:14;
      --gap:4;
      --radius:3;
    }
    .g { shape-rendering:geometricPrecision; fill:var(--cell); stroke:var(--gridStroke); stroke-width:1px; }
    .bar { transform-origin:0 0; fill:var(--high); }
    .snake { fill:var(--snake); }

    @keyframes pulseLow   { 50%{fill:var(--low)}   100%{fill:var(--cell)} }
    @keyframes pulseMid   { 50%{fill:var(--mid)}   100%{fill:var(--cell)} }
    @keyframes pulseHigh  { 50%{fill:var(--high)}  100%{fill:var(--cell)} }

    .pL { animation: pulseLow  var(--speed) linear infinite; }
    .pM { animation: pulseMid  var(--speed) linear infinite; }
    .pH { animation: pulseHigh var(--speed) linear infinite; }

    @keyframes growA { 0%{transform:scale(0,1)} 30%{transform:scale(0.33,1)} 60%{transform:scale(0.66,1)} 100%{transform:scale(1,1)} }
    @keyframes growB { 0%{transform:scale(0,1)} 40%{transform:scale(0.5,1)} 100%{transform:scale(1,1)} }
    @keyframes growC { 0%{transform:scale(0,1)} 50%{transform:scale(0.25,1)} 75%{transform:scale(0.5,1)} 90%{transform:scale(0.75,1)} 100%{transform:scale(1,1)} }

    .barA { animation: growA var(--speed) linear infinite; transform-origin:0 0; }
    .barB { animation: growB var(--speed) linear infinite; transform-origin:180px 0; }
    .barC { animation: growC var(--speed) linear infinite; transform-origin:320px 0; }

    @keyframes slither {
      0%, 99% { transform:translate(0, -16px) }
      3%      { transform:translate(0, 0px) }
      18%     { transform:translate(220px, 0px) }
      22%     { transform:translate(220px, 48px) }
      35%     { transform:translate(360px, 48px) }
      40%     { transform:translate(360px, 64px) }
      46%     { transform:translate(420px, 64px) }
      52%     { transform:translate(420px, 32px) }
      65%     { transform:translate(260px, 32px) }
      70%     { transform:translate(260px, 80px) }
      85%     { transform:translate(120px, 80px) }
      90%     { transform:translate(120px, 0px) }
      97%     { transform:translate(40px, 0px) }
    }
    .s0, .s1, .s2, .s3 { animation: slither var(--speed) linear infinite; }
  </style>

  <!-- GRID -->
  <!-- Row 0 -->
  <rect class="g pM" x="10" y="10" width="14" height="14" rx="3"/>
  <rect class="g" x="28" y="10" width="14" height="14" rx="3"/>
  <rect class="g pL" x="46" y="10" width="14" height="14" rx="3"/>
  <rect class="g" x="64" y="10" width="14" height="14" rx="3"/>
  <rect class="g pH" x="82" y="10" width="14" height="14" rx="3"/>
  <rect class="g" x="100" y="10" width="14" height="14" rx="3"/>
  <rect class="g pL" x="118" y="10" width="14" height="14" rx="3"/>
  <rect class="g" x="136" y="10" width="14" height="14" rx="3"/>
  <rect class="g pM" x="154" y="10" width="14" height="14" rx="3"/>
  <rect class="g" x="172" y="10" width="14" height="14" rx="3"/>
  <rect class="g pH" x="190" y="10" width="14" height="14" rx="3"/>
  <rect class="g" x="208" y="10" width="14" height="14" rx="3"/>

  <!-- Row 1 -->
  <rect class="g" x="10" y="28" width="14" height="14" rx="3"/>
  <rect class="g pL" x="28" y="28" width="14" height="14" rx="3"/>
  <rect class="g" x="46" y="28" width="14" height="14" rx="3"/>
  <rect class="g pM" x="64" y="28" width="14" height="14" rx="3"/>
  <rect class="g" x="82" y="28" width="14" height="14" rx="3"/>
  <rect class="g pH" x="100" y="28" width="14" height="14" rx="3"/>
  <rect class="g" x="118" y="28" width="14" height="14" rx="3"/>
  <rect class="g pL" x="136" y="28" width="14" height="14" rx="3"/>
  <rect class="g" x="154" y="28" width="14" height="14" rx="3"/>
  <rect class="g pM" x="172" y="28" width="14" height="14" rx="3"/>
  <rect class="g" x="190" y="28" width="14" height="14" rx="3"/>
  <rect class="g pH" x="208" y="28" width="14" height="14" rx="3"/>

  <!-- Row 2 -->
  <rect class="g pH" x="10" y="46" width="14" height="14" rx="3"/>
  <rect class="g" x="28" y="46" width="14" height="14" rx="3"/>
  <rect class="g pM" x="46" y="46" width="14" height="14" rx="3"/>
  <rect class="g" x="64" y="46" width="14" height="14" rx="3"/>
  <rect class="g pL" x="82" y="46" width="14" height="14" rx="3"/>
  <rect class="g" x="100" y="46" width="14" height="14" rx="3"/>
  <rect class="g pM" x="118" y="46" width="14" height="14" rx="3"/>
  <rect class="g" x="136" y="46" width="14" height="14" rx="3"/>
  <rect class="g pL" x="154" y="46" width="14" height="14" rx="3"/>
  <rect class="g" x="172" y="46" width="14" height="14" rx="3"/>
  <rect class="g pM" x="190" y="46" width="14" height="14" rx="3"/>
  <rect class="g" x="208" y="46" width="14" height="14" rx="3"/>

  <!-- Row 3 -->
  <rect class="g" x="10" y="64" width="14" height="14" rx="3"/>
  <rect class="g pM" x="28" y="64" width="14" height="14" rx="3"/>
  <rect class="g" x="46" y="64" width="14" height="14" rx="3"/>
  <rect class="g pH" x="64" y="64" width="14" height="14" rx="3"/>
  <rect class="g" x="82" y="64" width="14" height="14" rx="3"/>
  <rect class="g pL" x="100" y="64" width="14" height="14" rx="3"/>
  <rect class="g" x="118" y="64" width="14" height="14" rx="3"/>
  <rect class="g pH" x="136" y="64" width="14" height="14" rx="3"/>
  <rect class="g" x="154" y="64" width="14" height="14" rx="3"/>
  <rect class="g pM" x="172" y="64" width="14" height="14" rx="3"/>
  <rect class="g" x="190" y="64" width="14" height="14" rx="3"/>
  <rect class="g pL" x="208" y="64" width="14" height="14" rx="3"/>

  <!-- Row 4 -->
  <rect class="g pL" x="10" y="82" width="14" height="14" rx="3"/>
  <rect class="g" x="28" y="82" width="14" height="14" rx="3"/>
  <rect class="g pH" x="46" y="82" width="14" height="14" rx="3"/>
  <rect class="g" x="64" y="82" width="14" height="14" rx="3"/>
  <rect class="g pM" x="82" y="82" width="14" height="14" rx="3"/>
  <rect class="g" x="100" y="82" width="14" height="14" rx="3"/>
  <rect class="g pH" x="118" y="82" width="14" height="14" rx="3"/>
  <rect class="g" x="136" y="82" width="14" height="14" rx="3"/>
  <rect class="g pM" x="154" y="82" width="14" height="14" rx="3"/>
  <rect class="g" x="172" y="82" width="14" height="14" rx="3"/>
  <rect class="g pL" x="190" y="82" width="14" height="14" rx="3"/>
  <rect class="g" x="208" y="82" width="14" height="14" rx="3"/>

  <!-- Row 5 -->
  <rect class="g" x="10" y="100" width="14" height="14" rx="3"/>
  <rect class="g pH" x="28" y="100" width="14" height="14" rx="3"/>
  <rect class="g" x="46" y="100" width="14" height="14" rx="3"/>
  <rect class="g pM" x="64" y="100" width="14" height="14" rx="3"/>
  <rect class="g" x="82" y="100" width="14" height="14" rx="3"/>
  <rect class="g pL" x="100" y="100" width="14" height="14" rx="3"/>
  <rect class="g" x="118" y="100" width="14" height="14" rx="3"/>
  <rect class="g pM" x="136" y="100" width="14" height="14" rx="3"/>
  <rect class="g" x="154" y="100" width="14" height="14" rx="3"/>
  <rect class="g pH" x="172" y="100" width="14" height="14" rx="3"/>
  <rect class="g" x="190" y="100" width="14" height="14" rx="3"/>
  <rect class="g pL" x="208" y="100" width="14" height="14" rx="3"/>

  <!-- Progress bars -->
  <rect class="bar barA" x="10" y="140" width="180" height="12" rx="3"/>
  <rect class="bar barB" x="190" y="140" width="140" height="12" rx="3"/>
  <rect class="bar barC" x="330" y="140" width="160" height="12" rx="3"/>

  <!-- Snake -->
  <rect class="snake s0" x="11" y="-6" width="16" height="16" rx="5"/>
  <rect class="snake s1" x="12" y="-5" width="14" height="14" rx="4"/>
  <rect class="snake s2" x="13" y="-4" width="12" height="12" rx="4"/>
  <rect class="snake s3" x="13.5" y="-3.5" width="11" height="11" rx="3.5"/>
</svg>
