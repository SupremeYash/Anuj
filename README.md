<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Payment Successful</title>
  <style>
    :root{
      --bg:#cfefff;            /* light blue background */
      --circle:#16a34a;        /* green circle */
      --check:#10b981;         /* check color (slightly lighter) */
      --text:#0f172a;          /* dark text */
      --max-width:780px;
    }

    html,body{
      height:100%;
      margin:0;
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      background:var(--bg);
      color:var(--text);
    }

    /* Centering container for mobile-first layout */
    .wrap{
      min-height:100vh;
      display:flex;
      align-items:center;
      justify-content:center;
      padding:6vw 5vw;
      box-sizing:border-box;
    }

    .card{
      width:100%;
      max-width:var(--max-width);
      text-align:center;
      background:transparent; /* keep it minimalist */
      border-radius:16px;
      padding:4vw 4vw 6vw;
      box-sizing:border-box;
      -webkit-tap-highlight-color: transparent;
    }

    /* SVG sizing - use viewport width to make it responsive on small screens */
    .icon{
      width:56vw;               /* large on phones */
      max-width:320px;         /* cap on bigger phones */
      height:auto;
      margin:0 auto;
      display:block;
      filter: drop-shadow(0 6px 18px rgba(16, 185, 129, 0.12));
    }

    .title{
      margin-top:6vw;
      font-size:6.6vw;         /* fluid text size for mobile */
      line-height:1;
      font-weight:700;
      letter-spacing:0.01em;
    }

    /* Cap sizes for larger screens */
    @media (min-width:420px){
      .title{ font-size:28px; margin-top:22px; }
      .icon{ width:220px; max-width:320px; }
      .card{ padding:28px; }
    }

    .subtitle{
      margin-top:10px;
      font-size:3.8vw;
      color:rgba(15,23,42,0.75);
      font-weight:600;
    }
    @media (min-width:420px){
      .subtitle{ font-size:14px; }
    }

    /* BUTTON (optional) */
    .btn{
      margin-top:20px;
      display:inline-block;
      padding:12px 20px;
      border-radius:10px;
      background:#0f172a;
      color:white;
      text-decoration:none;
      font-weight:600;
      font-size:14px;
      box-shadow: 0 6px 14px rgba(2,6,23,0.12);
    }

    /* checkmark animation (stroke drawing) */
    .check-stroke{
      stroke-dasharray: 1200;
      stroke-dashoffset: 1200;
      animation: draw 0.9s cubic-bezier(.2,.9,.2,1) 0.25s forwards;
    }

    @keyframes draw {
      to { stroke-dashoffset: 0; }
    }
  </style>
</head>
<body>
  <main class="wrap" role="main">
    <div class="card" aria-live="polite">
      <!-- Inline SVG: circle + check. Accessible label added -->
      <svg class="icon" viewBox="0 0 200 200" role="img" aria-label="Payment successful. A green check inside a circle on a light blue background.">
        <!-- Outer ring -->
        <circle cx="100" cy="100" r="72" fill="none" stroke="#16a34a" stroke-width="12" stroke-linecap="round"/>
        <!-- Filled slightly-lighter inner circle for clean look (optional subtle) -->
        <circle cx="100" cy="100" r="66" fill="rgba(16,185,129,0.03)" stroke="none" />
        <!-- Check mark path - stroke animation applies -->
        <path class="check-stroke" d="M62 102 L88 128 L138 80"
              fill="none"
              stroke="#10b981"
              stroke-width="14"
              stroke-linecap="round"
              stroke-linejoin="round"/>
      </svg>

      <!-- Title and subtitle text -->
      <h1 class="title">PAYMENT SUCCESSFUL</h1>
      <p class="subtitle">Thank you — your payment has been processed.</p>

      <!-- Optional CTA (you can remove or change) -->
      <div>
        <a class="btn" href="#" onclick="event.preventDefault();">Back to Home</a>
      </div>
    </div>
  </main>

  <!-- Small JS to improve accessibility: focus title for screen readers when page loads -->
  <script>
    // Move focus to the title for screen readers
    document.addEventListener('DOMContentLoaded', function(){
      const title = document.querySelector('.title');
      if(title) {
        title.setAttribute('tabindex','-1');
        title.focus({preventScroll:true});
      }
    });
  </script>
</body>
</html>
