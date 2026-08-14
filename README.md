<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Vaibhav Rahangdale — Portfolio</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Fredoka:wght@500;600;700&family=Caveat:wght@600;700&family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root{
    --dark: #1b1c20;
    --dark2: #232428;
    --paper: #f5f4ef;
    --amber: #f4a93b;
    --cyan: #4fd1c5;
    --pink: #ef6fa5;
    --muted: #a6a9b2;
    --font-display: 'Fredoka', sans-serif;
    --font-script: 'Caveat', cursive;
    --font-body: 'Inter', sans-serif;
    --font-mono: 'JetBrains Mono', monospace;
  }
  *{ margin:0; padding:0; box-sizing:border-box; }
  html{ scroll-behavior:smooth; }
  body{ background:var(--dark); color:#fff; font-family:var(--font-body); overflow-x:hidden; }
  a{ color:inherit; text-decoration:none; }
  ::selection{ background:var(--amber); color:#1b1c20; }
  .container{ max-width:1000px; margin:0 auto; padding:0 40px; }

  /* ---------- HEADER (torn paper) ---------- */
  .paper-head{
    position:relative;
    background:
      radial-gradient(circle, rgba(0,0,0,0.05) 1px, transparent 1px) 0 0/26px 26px,
      var(--paper);
    color:#1b1c20;
    padding:70px 32px 90px;
    text-align:center;
    overflow:hidden;
  }
  .year-badge{
    display:inline-block; border:2px solid #1b1c20; border-radius:50%;
    padding:8px 20px; font-family:var(--font-script); font-size:1.4rem;
    transform:rotate(-6deg); margin-bottom:6px;
    opacity:0; animation:pop .6s .1s forwards ease-out;
  }
  .portfolio-title{
    font-family:var(--font-display); font-weight:700; font-size:clamp(3rem,10vw,6.5rem);
    letter-spacing:-0.01em; line-height:1;
    opacity:0; animation:pop .7s .25s forwards ease-out;
  }
  .portfolio-title .accent{ color:var(--amber); }
  .head-tagline{
    font-family:var(--font-mono); font-size:13px; letter-spacing:.06em; text-transform:uppercase;
    margin-top:18px; color:#4a4b52;
    opacity:0; animation:pop .7s .4s forwards ease-out;
  }
  .head-tagline span{ margin:0 10px; color:var(--amber); }
  @keyframes pop{ from{opacity:0; transform:translateY(14px);} to{opacity:1; transform:translateY(0);} }

  .spark{ position:absolute; opacity:.85; }
  .spark svg{ width:100%; height:100%; }

  .torn-edge{
    position:absolute; left:0; right:0; bottom:-1px; height:60px;
    background:var(--dark);
    clip-path: polygon(
      0% 40%, 4% 20%, 8% 45%, 12% 15%, 16% 38%, 20% 10%, 24% 42%, 28% 18%,
      32% 44%, 36% 22%, 40% 40%, 44% 12%, 48% 46%, 52% 20%, 56% 38%, 60% 14%,
      64% 42%, 68% 18%, 72% 44%, 76% 24%, 80% 40%, 84% 16%, 88% 46%, 92% 20%,
      96% 38%, 100% 15%, 100% 100%, 0% 100%
    );
  }

  /* ---------- MAIN DARK SECTION ---------- */
  .main{ padding:70px 0 40px; position:relative; }
  .top-grid{ display:grid; grid-template-columns:280px 1fr; gap:56px; align-items:start; }

  /* polaroid */
  .polaroid{
    background:#fafafa; padding:14px 14px 46px; border-radius:4px; position:relative;
    transform:rotate(-3deg); box-shadow:0 18px 40px rgba(0,0,0,0.45);
    opacity:0; animation:fadeUp .7s .2s forwards ease-out;
  }
  .polaroid .photo{
    width:100%; aspect-ratio:1/1.05; border-radius:2px; overflow:hidden; position:relative;
    background:linear-gradient(160deg, #2fb6c9, #1b7d8f);
  }
  .polaroid .name-tag{
    position:absolute; left:14px; bottom:14px; font-family:var(--font-display); font-weight:600;
    font-size:1.05rem; color:#1b1c20;
  }
  .tape{
    position:absolute; top:-14px; left:50%; transform:translateX(-50%) rotate(-2deg);
    width:90px; height:28px; background:rgba(220,200,160,0.55); border:1px solid rgba(0,0,0,0.05);
  }
  .sticker{ position:absolute; }
  .sticker.chip{ top:-16px; right:-20px; width:56px; }
  .sticker.bolt{ bottom:60px; left:-22px; width:46px; }

  @keyframes fadeUp{ from{opacity:0; transform:translateY(20px) rotate(-3deg);} to{opacity:1; transform:translateY(0) rotate(-3deg);} }

  /* hello / contact */
  .hello h2{
    font-family:var(--font-display); font-weight:600; font-size:2.4rem; margin-bottom:18px;
    opacity:0; animation:fadeUp2 .6s .3s forwards ease-out;
  }
  .hello p{
    color:var(--muted); max-width:480px; line-height:1.7; font-size:1rem;
    opacity:0; animation:fadeUp2 .6s .42s forwards ease-out;
  }
  @keyframes fadeUp2{ from{opacity:0; transform:translateY(16px);} to{opacity:1; transform:translateY(0);} }

  .contact-block{ margin-top:38px; opacity:0; animation:fadeUp2 .6s .55s forwards ease-out; }
  .contact-block h2{ font-family:var(--font-display); font-weight:600; font-size:2rem; margin-bottom:18px; }
  .contact-grid{ display:grid; grid-template-columns:1fr 1fr; gap:16px 24px; }
  .contact-item{ display:flex; align-items:center; gap:12px; font-size:.95rem; color:#e7e8ec; }
  .cico{ width:32px; height:32px; border-radius:50%; display:flex; align-items:center; justify-content:center; flex-shrink:0; }
  .cico svg{ width:16px; height:16px; }
  .c-green{ background:#25d366; } .c-blue{ background:#4267ff; } .c-red{ background:#ea4335; } .c-pink{ background:linear-gradient(135deg,#f9906f,#e8388a); }

  /* education / experience */
  .lower-grid{ display:grid; grid-template-columns:1fr 1fr; gap:56px; margin-top:80px; }
  .lower-grid h2{ font-family:var(--font-display); font-weight:600; font-size:2rem; margin-bottom:26px; }

  .edu-item .yr{ font-family:var(--font-mono); font-size:12px; color:var(--muted); }
  .edu-item .deg{ font-family:var(--font-display); font-size:1.15rem; font-weight:600; margin:4px 0 2px; }
  .edu-item .sub{ color:var(--muted); font-style:italic; font-size:.9rem; }

  .software-block{ margin-top:42px; }
  .software-block h3{ font-family:var(--font-display); font-weight:600; font-size:1.5rem; margin-bottom:16px; }
  .sw-grid{ display:flex; flex-wrap:wrap; gap:14px; margin-bottom:8px; }
  .sw-icon{
    width:56px; height:56px; border-radius:12px; display:flex; align-items:center; justify-content:center;
    font-family:var(--font-display); font-weight:600; font-size:.85rem; color:#fff;
  }
  .sw-note{ font-family:var(--font-mono); font-size:11px; color:var(--muted); margin-top:6px; }

  .personal-block{ margin-top:40px; }
  .personal-block h4{ font-family:var(--font-mono); font-size:11px; text-transform:uppercase; color:var(--muted); margin-bottom:12px; letter-spacing:.05em; }
  .ptag-row{ display:flex; flex-wrap:wrap; gap:10px; }
  .ptag{ border:1.5px solid #3a3c44; color:#c9cbd2; font-family:var(--font-mono); font-size:11.5px; padding:6px 12px; border-radius:6px; }

  .t-item{ position:relative; padding-left:20px; border-left:2px solid #3a3c44; padding-bottom:30px; }
  .t-item:last-child{ padding-bottom:0; }
  .t-item::before{ content:''; position:absolute; left:-6px; top:2px; width:10px; height:10px; border-radius:50%; background:var(--amber); }
  .t-item .yr{ font-family:var(--font-mono); font-size:12px; color:var(--amber); }
  .t-item .role{ font-family:var(--font-display); font-size:1.1rem; font-weight:600; margin:4px 0 2px; }
  .t-item .org{ color:var(--muted); font-style:italic; font-size:.9rem; margin-bottom:6px; }
  .t-item .desc{ color:#c9cbd2; font-size:.88rem; line-height:1.5; }

  .reveal{ opacity:0; transform:translateY(24px); transition:opacity .7s ease-out, transform .7s ease-out; }
  .reveal.in{ opacity:1; transform:translateY(0); }

  footer.foot{ text-align:center; padding:60px 0 40px; font-family:var(--font-mono); font-size:11.5px; color:var(--muted); }

  @media (max-width: 760px){
    .top-grid{ grid-template-columns:1fr; }
    .lower-grid{ grid-template-columns:1fr; gap:50px; }
    .contact-grid{ grid-template-columns:1fr; }
    .polaroid{ max-width:260px; margin:0 auto; }
  }
  @media (prefers-reduced-motion: reduce){
    *{ animation-duration:.01ms !important; transition-duration:.01ms !important; }
  }
</style>
</head>
<body>

<div class="paper-head">
  <div class="spark" style="top:8%; left:4%; width:34px; color:#f4a93b;">
    <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 2l2 7h7l-6 4 2 8-5-5-5 5 2-8-6-4h7z"/></svg>
  </div>
  <div class="spark" style="top:20%; right:6%; width:42px; color:#4fd1c5;">
    <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 2l2.5 7.5H22l-6 4.5 2.5 7.5L12 17l-6.5 4.5L8 14 2 9.5h7.5z"/></svg>
  </div>
  <div class="spark" style="top:6%; left:22%; width:18px; color:#1b1c20;">
    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M12 2l1.5 7.5L21 12l-7.5 1.5L12 21l-1.5-7.5L3 12l7.5-1.5z"/></svg>
  </div>

  <div class="year-badge">2026</div>
  <div class="portfolio-title">P<span class="accent">o</span>rtf<span class="accent">o</span>li<span class="accent">o</span></div>
  <div class="head-tagline">Electrical Engineering <span>+</span> Embedded Systems <span>+</span> Python</div>

  <div class="torn-edge"></div>
</div>

<div class="main container">
  <div class="top-grid">
    <div class="polaroid">
      <div class="tape"></div>
      <div class="sticker chip">
        <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
          <rect x="6" y="6" width="12" height="12" rx="2" fill="#f4a93b"/>
          <g stroke="#1b1c20" stroke-width="1.4">
            <path d="M9 2v4M12 2v4M15 2v4M9 18v4M12 18v4M15 18v4M2 9h4M2 12h4M2 15h4M18 9h4M18 12h4M18 15h4"/>
          </g>
        </svg>
      </div>
      <div class="sticker bolt">
        <svg viewBox="0 0 24 24" fill="#4fd1c5"><path d="M13 2 4 14h6l-1 8 9-12h-6z"/></svg>
      </div>
      <div class="photo">
        <svg viewBox="0 0 300 320" width="100%" height="100%" preserveAspectRatio="xMidYMid slice">
          <rect width="300" height="320" fill="#1c7d8f"/>
          <circle cx="150" cy="118" r="52" fill="#0f2530"/>
          <path d="M55 320c0-90 40-140 95-140s95 50 95 140z" fill="#0f2530"/>
          <g stroke="#4fd1c5" stroke-width="2.5" fill="none" opacity="0.9">
            <path d="M150 170v34"/>
            <circle cx="150" cy="210" r="5" fill="#4fd1c5"/>
            <path d="M150 210h44v26"/>
            <circle cx="194" cy="242" r="4" fill="#f4a93b"/>
            <path d="M150 210h-44v26"/>
            <circle cx="106" cy="242" r="4" fill="#ef6fa5"/>
          </g>
        </svg>
      </div>
      <div class="name-tag">Vaibhav Rahangdale</div>
    </div>

    <div class="hello">
      <h2>Hello!</h2>
      <p>Hi, I'm Vaibhav Rahangdale, an Electrical Engineering student at G H Raisoni College of Engineering, Nagpur. I'm interested in both hardware and software — currently sharpening my skills in Python while building hands-on hardware projects, including my minor project on an intelligent street light system.</p>

      <div class="contact-block">
        <h2>Contact</h2>
        <div class="contact-grid">
          <div class="contact-item">
            <span class="cico c-green"><svg viewBox="0 0 24 24" fill="#fff"><path d="M12 2a10 10 0 00-8.5 15.3L2 22l4.9-1.4A10 10 0 1012 2z"/></svg></span>
            Your Phone Number
          </div>
          <div class="contact-item">
            <span class="cico c-blue"><svg viewBox="0 0 24 24" fill="#fff"><rect x="3" y="4" width="18" height="16" rx="2"/></svg></span>
            LinkedIn / Vaibhav Rahangdale
          </div>
          <div class="contact-item">
            <span class="cico c-red"><svg viewBox="0 0 24 24" fill="#fff"><path d="M3 5l9 7 9-7v14H3z"/></svg></span>
            your.email@example.com
          </div>
          <div class="contact-item">
            <span class="cico c-pink"><svg viewBox="0 0 24 24" fill="#fff"><rect x="3" y="3" width="18" height="18" rx="5"/></svg></span>
            GitHub / your_handle
          </div>
        </div>
      </div>
    </div>
  </div>

  <div class="lower-grid">
    <div>
      <div class="reveal">
        <h2>Education</h2>
        <div class="edu-item">
          <div class="yr">Currently Pursuing</div>
          <div class="deg">G H Raisoni College of Engineering, Nagpur</div>
          <div class="sub">Bachelor's in Electrical Engineering</div>
        </div>
      </div>

      <div class="software-block reveal">
        <h3>Software</h3>
        <div class="sw-grid">
          <div class="sw-icon" style="background:#2f6fed;">PY</div>
          <div class="sw-icon" style="background:#00878f;">CKT</div>
          <div class="sw-icon" style="background:#5c5f66;">IDE</div>
        </div>
        <div class="sw-note">// swap in the exact tools you use — Arduino IDE, Proteus, MATLAB, etc.</div>
      </div>

      <div class="personal-block reveal">
        <h4>Personal</h4>
        <div class="ptag-row">
          <span class="ptag">Fast Learner</span>
          <span class="ptag">Team Player</span>
          <span class="ptag">Hands-On Builder</span>
          <span class="ptag">Communication</span>
        </div>
      </div>
    </div>

    <div class="reveal">
      <h2>Experience</h2>
      <div class="t-item">
        <div class="yr">Ongoing</div>
        <div class="role">Intelligent Street Light System</div>
        <div class="org">Minor Project</div>
        <div class="desc">Designing a sensor-driven street lighting system that responds to real conditions instead of running on a fixed timer, combining hardware control with software logic.</div>
      </div>
      <div class="t-item">
        <div class="yr">Completed</div>
        <div class="role">Hackathon Participant</div>
        <div class="org">Team Competition</div>
        <div class="desc">Applied problem-solving and rapid prototyping skills under time pressure as part of a team.</div>
      </div>
      <div class="t-item">
        <div class="yr">In Progress</div>
        <div class="role">Skill Building</div>
        <div class="org">Self-Directed</div>
        <div class="desc">Actively improving hardware fundamentals alongside Python, software, and communication skills.</div>
      </div>
    </div>
  </div>
</div>

<footer class="foot">© 2026 Vaibhav Rahangdale — Circuit to code.</footer>

<script>
  const revealEls = document.querySelectorAll('.reveal');
  const io = new IntersectionObserver((entries)=>{
    entries.forEach(e=>{
      if(e.isIntersecting){ e.target.classList.add('in'); io.unobserve(e.target); }
    });
  }, { threshold: 0.15 });
  revealEls.forEach(el=>io.observe(el));
</script>

</body>
</html>
