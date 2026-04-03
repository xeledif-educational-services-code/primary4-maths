<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Fractions Adventure — Primary 4 | Xeledif Educational Services</title>
<style>
  :root {
    --blue:#378ADD; --blue-light:#E6F1FB; --blue-dark:#0C447C; --blue-mid:#185FA5;
    --green:#639922; --green-light:#EAF3DE; --green-dark:#27500A; --green-mid:#3B6D11;
    --amber:#BA7517; --amber-light:#FAEEDA; --amber-dark:#633806; --amber-mid:#854F0B;
    --purple:#7F77DD; --purple-light:#EEEDFE; --purple-dark:#3C3489; --purple-mid:#534AB7;
    --teal:#1D9E75; --teal-light:#E1F5EE; --teal-dark:#085041;
    --coral:#D85A30; --coral-light:#FAECE7; --coral-dark:#712B13;
    --pink:#D4537E; --pink-light:#FBEAF0; --pink-dark:#72243E;
    --text:#1a1a1a; --text-sec:#555; --text-ter:#888;
    --border:#ddd; --border-light:#eee;
    --bg:#fff; --bg-sec:#f8f8f8; --bg-ter:#f2f2f2;
    --radius:12px; --radius-sm:8px;
  }
  * { box-sizing:border-box; margin:0; padding:0; }
  body { font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif; color:var(--text); background:#f5f5f5; }

  .page { max-width:860px; margin:0 auto; padding:1.5rem 1rem 3rem; }

  /* HERO */
  .hero { background:var(--bg); border:0.5px solid var(--border); border-radius:var(--radius); padding:1.5rem; margin-bottom:1.25rem; }
  .hero-row { display:flex; align-items:center; gap:12px; margin-bottom:10px; }
  .hero-avatar { width:46px; height:46px; background:var(--blue); border-radius:50%; display:flex; align-items:center; justify-content:center; font-size:18px; font-weight:600; color:white; flex-shrink:0; }
  .hero-title { font-size:20px; font-weight:600; color:var(--text); }
  .hero-sub { font-size:13px; color:var(--text-sec); margin-top:2px; }
  .badge { display:inline-block; font-size:11px; font-weight:600; padding:3px 10px; border-radius:12px; margin-right:5px; }

  /* WEEK GROUPS */
  .week-group { margin-bottom:1rem; border:0.5px solid var(--border); border-radius:var(--radius); overflow:hidden; }
  .week-header { display:flex; align-items:center; gap:10px; padding:11px 14px; cursor:pointer; user-select:none; transition:opacity 0.15s; }
  .week-header:hover { opacity:0.88; }
  .week-dot { width:28px; height:28px; border-radius:50%; display:flex; align-items:center; justify-content:center; font-size:11px; font-weight:700; flex-shrink:0; }
  .week-title { font-size:13px; font-weight:600; flex:1; }
  .week-meta { font-size:11px; opacity:0.7; }
  .week-arrow { font-size:10px; opacity:0.6; transition:transform 0.2s; }
  .week-arrow.open { transform:rotate(90deg); }
  .week-tabs { display:none; padding:8px 10px 10px; border-top:0.5px solid var(--border-light); gap:6px; flex-wrap:wrap; background:var(--bg); }
  .week-tabs.open { display:flex; }

  /* TABS */
  .tab { padding:6px 13px; border-radius:20px; border:0.5px solid var(--border); font-size:12px; font-weight:600; cursor:pointer; background:transparent; color:var(--text-sec); white-space:nowrap; transition:all 0.15s; }
  .tab:hover:not(.active) { background:var(--bg-sec); }
  .tab.active { color:white; border-color:transparent; }

  /* CONTENT AREA */
  .content-area { margin-top:1.25rem; background:var(--bg); border:0.5px solid var(--border); border-radius:var(--radius); padding:1.5rem; }
  .content-area.hidden { display:none; }

  /* CONTENT LABELS */
  .gap-label { display:inline-block; font-size:11px; font-weight:600; padding:3px 10px; border-radius:12px; margin-right:4px; margin-bottom:12px; }

  /* LESSON COMPONENTS */
  .day-header { display:flex; align-items:center; gap:12px; margin-bottom:1.25rem; }
  .day-icon { width:38px; height:38px; border-radius:50%; display:flex; align-items:center; justify-content:center; font-size:15px; font-weight:700; flex-shrink:0; }
  .day-label { font-size:17px; font-weight:600; }
  .day-sub { font-size:13px; color:var(--text-sec); margin-top:1px; }

  .card { background:var(--bg); border:0.5px solid var(--border); border-radius:var(--radius); padding:1.25rem; margin-bottom:1rem; }
  .card-title { font-size:15px; font-weight:600; margin-bottom:8px; }
  .card-body { font-size:14px; color:var(--text-sec); line-height:1.7; }

  .warmup { background:var(--blue-light); border-radius:var(--radius-sm); padding:12px 14px; font-size:14px; font-style:italic; color:var(--blue-dark); line-height:1.6; }

  /* STEP EXAMPLES */
  .steps-row { display:flex; gap:10px; flex-wrap:wrap; align-items:flex-start; margin-top:8px; }
  .step-box { flex:1; min-width:110px; text-align:center; }
  .step-num { font-size:11px; font-weight:600; margin-bottom:6px; }
  .step-caption { font-size:11px; margin-top:6px; line-height:1.4; }
  .step-arrow { font-size:18px; color:var(--text-ter); align-self:center; padding-top:10px; }
  .example-label { font-size:12px; font-weight:600; color:var(--text-sec); margin-bottom:8px; letter-spacing:0.04em; text-transform:uppercase; }

  /* EXERCISES */
  .exercise-list { margin-top:4px; }
  .exercise-item { display:flex; align-items:flex-start; gap:10px; padding:10px 0; border-bottom:0.5px solid var(--border-light); font-size:14px; }
  .exercise-item:last-child { border-bottom:none; }
  .ex-num { background:var(--blue-light); color:var(--blue-dark); border-radius:50%; width:24px; height:24px; display:flex; align-items:center; justify-content:center; font-size:11px; font-weight:700; flex-shrink:0; margin-top:2px; }
  .ex-text { flex:1; color:var(--text); line-height:1.6; }
  .ex-tag { font-size:11px; font-weight:600; padding:2px 8px; border-radius:10px; margin-left:6px; vertical-align:middle; }

  /* EMPTY STATE */
  .empty-state { display:flex; flex-direction:column; align-items:center; padding:2.5rem 1rem; text-align:center; gap:10px; }
  .empty-icon { width:46px; height:46px; border-radius:50%; background:var(--bg-sec); border:0.5px dashed var(--border); display:flex; align-items:center; justify-content:center; }
  .empty-title { font-size:15px; font-weight:600; color:var(--text); }
  .empty-sub { font-size:13px; color:var(--text-sec); max-width:320px; line-height:1.6; }

  /* STRATEGY GRID */
  .strategy-grid { display:grid; grid-template-columns:repeat(auto-fit, minmax(200px,1fr)); gap:10px; margin-top:10px; }
  .strategy-card { border-radius:var(--radius-sm); padding:12px; border:0.5px solid; }
  .s-title { font-size:13px; font-weight:600; margin-bottom:4px; }
  .s-body { font-size:12px; line-height:1.6; }

  svg.shape-svg { display:block; margin:0 auto; }
</style>
</head>
<body>
<div class="page">

  <div class="hero">
    <div class="hero-row">
      <div class="hero-avatar">F</div>
      <div>
        <div class="hero-title">Fractions Adventure — Primary 4</div>
        <div class="hero-sub">Xeledif Educational Services &nbsp;|&nbsp; UK Curriculum &nbsp;|&nbsp; March 2026</div>
      </div>
    </div>
    <div>
      <span class="badge" style="background:var(--blue-light);color:var(--blue-dark);border:0.5px solid #B5D4F4;">CPA Mastery Method</span>
      <span class="badge" style="background:var(--purple-light);color:var(--purple-dark);border:0.5px solid #CECBF6;">Virtual Learning</span>
      <span class="badge" style="background:var(--green-light);color:var(--green-dark);border:0.5px solid #C0DD97;">UK Year 4</span>
    </div>
  </div>

  <div id="week-groups"></div>
  <div id="content-area" class="content-area hidden"></div>

</div>

<script>

/* ============================================================
   COLOUR & TYPE CONSTANTS — do not edit
   ============================================================ */
const COLORS = [
  { dot:'#378ADD', dotTxt:'white', active:'#185FA5', light:'#E6F1FB', border:'#B5D4F4', text:'#0C447C', gap:'Foundational gap 1 — What is a fraction?' },
  { dot:'#1D9E75', dotTxt:'white', active:'#0F6E56', light:'#E1F5EE', border:'#9FE1CB', text:'#085041', gap:'Foundational gap 2 — Comparing & ordering fractions' },
  { dot:'#BA7517', dotTxt:'white', active:'#854F0B', light:'#FAEEDA', border:'#FAC775', text:'#633806', gap:'Foundational gap 3 — Fractions of amounts & money' },
  { dot:'#7F77DD', dotTxt:'white', active:'#534AB7', light:'#EEEDFE', border:'#CECBF6', text:'#3C3489', gap:'Foundational gap 4 — Equivalent fractions' },
];

const TAB_TYPE = {
  task:     { bg:'#E6F1FB', text:'#0C447C', label:'Task' },
  review:   { bg:'#EAF3DE', text:'#27500A', label:'Study review' },
  revision: { bg:'#FAEEDA', text:'#633806', label:'Revision' },
};


/* ============================================================
   >>>  LESSON CONTENT VARIABLES
   >>>  ADD NEW ONES HERE AS EACH WEEK IS READY
   >>>  Then reference them in the WEEKS array below.
   ============================================================ */


/* ----------------------------------------------------------
   TASK 1 — 3 March 2026
   Foundational gap 1: What is a fraction? Shading shapes.
   ---------------------------------------------------------- */
const TASK1_CONTENT = `

  <div class="day-header">
    <div class="day-icon" style="background:#E6F1FB;color:#0C447C;border:0.5px solid #B5D4F4;">1</div>
    <div>
      <div class="day-label" style="color:#0C447C;">Task Set 1 — 3 March 2026</div>
      <div class="day-sub">Topic: What is a fraction? Shading rectangles &amp; squares</div>
    </div>
  </div>

  <div class="card" style="border-color:#B5D4F4;">
    <div class="card-title" style="color:#0C447C;">Let's begin</div>
    <div class="warmup">"Hello! Today we are going on a Fractions Adventure. A fraction is just a way of sharing something equally — like sharing a chocolate bar with friends. Let us do it step by step, like levels in a game!"</div>
  </div>

  <div class="card">
    <div class="card-title">What is a fraction? — Key ideas</div>
    <div class="strategy-grid">
      <div class="strategy-card" style="background:#E6F1FB;border-color:#B5D4F4;">
        <div class="s-title" style="color:#0C447C;">The whole</div>
        <div class="s-body" style="color:#185FA5;">The complete shape or group before splitting. Always start here.</div>
      </div>
      <div class="strategy-card" style="background:#EAF3DE;border-color:#C0DD97;">
        <div class="s-title" style="color:#27500A;">Equal parts</div>
        <div class="s-body" style="color:#3B6D11;">Each piece must be exactly the same size. If they are not equal, it is not a fraction.</div>
      </div>
      <div class="strategy-card" style="background:#FAEEDA;border-color:#FAC775;">
        <div class="s-title" style="color:#633806;">Denominator (bottom)</div>
        <div class="s-body" style="color:#854F0B;">The total number of equal parts. This is the NAME of the fraction.</div>
      </div>
      <div class="strategy-card" style="background:#EEEDFE;border-color:#CECBF6;">
        <div class="s-title" style="color:#3C3489;">Numerator (top)</div>
        <div class="s-body" style="color:#534AB7;">How many parts we shade or use. This is HOW MANY we have.</div>
      </div>
    </div>
  </div>

  <!-- EXAMPLE 1 -->
  <div class="card">
    <div class="card-title">Example 1 — Shade <span style="color:#185FA5;">2/3</span> of a rectangle</div>
    <div class="example-label">Follow these 3 steps:</div>
    <div class="steps-row">
      <div class="step-box">
        <div class="step-num" style="color:#0C447C;">Step 1 — The whole shape</div>
        <svg class="shape-svg" width="110" height="55" viewBox="0 0 110 55">
          <rect x="5" y="10" width="100" height="35" rx="3" fill="none" stroke="#378ADD" stroke-width="1.5"/>
        </svg>
        <div class="step-caption" style="color:#0C447C;">Here is the full rectangle. Nothing shaded yet.</div>
      </div>
      <div class="step-arrow">&#8594;</div>
      <div class="step-box">
        <div class="step-num" style="color:#0C447C;">Step 2 — Divide into 3 equal parts</div>
        <svg class="shape-svg" width="110" height="55" viewBox="0 0 110 55">
          <rect x="5" y="10" width="100" height="35" rx="3" fill="none" stroke="#378ADD" stroke-width="1.5"/>
          <line x1="38" y1="10" x2="38" y2="45" stroke="#378ADD" stroke-width="1"/>
          <line x1="71" y1="10" x2="71" y2="45" stroke="#378ADD" stroke-width="1"/>
        </svg>
        <div class="step-caption" style="color:#0C447C;">Denominator = 3, so we make 3 equal parts.</div>
      </div>
      <div class="step-arrow">&#8594;</div>
      <div class="step-box">
        <div class="step-num" style="color:#0C447C;">Step 3 — Shade 2 parts</div>
        <svg class="shape-svg" width="110" height="55" viewBox="0 0 110 55">
          <rect x="5" y="10" width="33" height="35" fill="#378ADD" opacity="0.65"/>
          <rect x="38" y="10" width="33" height="35" fill="#378ADD" opacity="0.65"/>
          <rect x="5" y="10" width="100" height="35" rx="3" fill="none" stroke="#185FA5" stroke-width="1.5"/>
          <line x1="38" y1="10" x2="38" y2="45" stroke="#185FA5" stroke-width="1"/>
          <line x1="71" y1="10" x2="71" y2="45" stroke="#185FA5" stroke-width="1"/>
        </svg>
        <div class="step-caption" style="color:#0C447C;">Numerator = 2, so we shade 2 parts. Done!</div>
      </div>
    </div>
  </div>

  <!-- EXAMPLE 2 -->
  <div class="card">
    <div class="card-title">Example 2 — Shade <span style="color:#3B6D11;">1/4</span> of a rectangle</div>
    <div class="steps-row">
      <div class="step-box">
        <div class="step-num" style="color:#27500A;">Step 1</div>
        <svg class="shape-svg" width="110" height="55" viewBox="0 0 110 55">
          <rect x="5" y="10" width="100" height="35" rx="3" fill="none" stroke="#639922" stroke-width="1.5"/>
        </svg>
        <div class="step-caption" style="color:#27500A;">Empty rectangle</div>
      </div>
      <div class="step-arrow">&#8594;</div>
      <div class="step-box">
        <div class="step-num" style="color:#27500A;">Step 2 — 4 equal parts</div>
        <svg class="shape-svg" width="110" height="55" viewBox="0 0 110 55">
          <rect x="5" y="10" width="100" height="35" rx="3" fill="none" stroke="#639922" stroke-width="1.5"/>
          <line x1="30" y1="10" x2="30" y2="45" stroke="#639922" stroke-width="1"/>
          <line x1="55" y1="10" x2="55" y2="45" stroke="#639922" stroke-width="1"/>
          <line x1="80" y1="10" x2="80" y2="45" stroke="#639922" stroke-width="1"/>
        </svg>
        <div class="step-caption" style="color:#27500A;">Denominator = 4</div>
      </div>
      <div class="step-arrow">&#8594;</div>
      <div class="step-box">
        <div class="step-num" style="color:#27500A;">Step 3 — Shade 1 part</div>
        <svg class="shape-svg" width="110" height="55" viewBox="0 0 110 55">
          <rect x="5" y="10" width="25" height="35" fill="#97C459" opacity="0.8"/>
          <rect x="5" y="10" width="100" height="35" rx="3" fill="none" stroke="#3B6D11" stroke-width="1.5"/>
          <line x1="30" y1="10" x2="30" y2="45" stroke="#3B6D11" stroke-width="1"/>
          <line x1="55" y1="10" x2="55" y2="45" stroke="#3B6D11" stroke-width="1"/>
          <line x1="80" y1="10" x2="80" y2="45" stroke="#3B6D11" stroke-width="1"/>
        </svg>
        <div class="step-caption" style="color:#27500A;">Numerator = 1</div>
      </div>
    </div>
  </div>

  <!-- EXAMPLE 3 -->
  <div class="card">
    <div class="card-title">Example 3 — Shade <span style="color:#854F0B;">3/5</span> of a rectangle</div>
    <div class="steps-row">
      <div class="step-box">
        <div class="step-num" style="color:#633806;">Step 1</div>
        <svg class="shape-svg" width="110" height="55" viewBox="0 0 110 55">
          <rect x="5" y="10" width="100" height="35" rx="3" fill="none" stroke="#BA7517" stroke-width="1.5"/>
        </svg>
        <div class="step-caption" style="color:#633806;">Empty rectangle</div>
      </div>
      <div class="step-arrow">&#8594;</div>
      <div class="step-box">
        <div class="step-num" style="color:#633806;">Step 2 — 5 equal parts</div>
        <svg class="shape-svg" width="110" height="55" viewBox="0 0 110 55">
          <rect x="5" y="10" width="100" height="35" rx="3" fill="none" stroke="#BA7517" stroke-width="1.5"/>
          <line x1="25" y1="10" x2="25" y2="45" stroke="#BA7517" stroke-width="1"/>
          <line x1="45" y1="10" x2="45" y2="45" stroke="#BA7517" stroke-width="1"/>
          <line x1="65" y1="10" x2="65" y2="45" stroke="#BA7517" stroke-width="1"/>
          <line x1="85" y1="10" x2="85" y2="45" stroke="#BA7517" stroke-width="1"/>
        </svg>
        <div class="step-caption" style="color:#633806;">Denominator = 5</div>
      </div>
      <div class="step-arrow">&#8594;</div>
      <div class="step-box">
        <div class="step-num" style="color:#633806;">Step 3 — Shade 3 parts</div>
        <svg class="shape-svg" width="110" height="55" viewBox="0 0 110 55">
          <rect x="5" y="10" width="20" height="35" fill="#EF9F27" opacity="0.8"/>
          <rect x="25" y="10" width="20" height="35" fill="#EF9F27" opacity="0.8"/>
          <rect x="45" y="10" width="20" height="35" fill="#EF9F27" opacity="0.8"/>
          <rect x="5" y="10" width="100" height="35" rx="3" fill="none" stroke="#633806" stroke-width="1.5"/>
          <line x1="25" y1="10" x2="25" y2="45" stroke="#633806" stroke-width="1"/>
          <line x1="45" y1="10" x2="45" y2="45" stroke="#633806" stroke-width="1"/>
          <line x1="65" y1="10" x2="65" y2="45" stroke="#633806" stroke-width="1"/>
          <line x1="85" y1="10" x2="85" y2="45" stroke="#633806" stroke-width="1"/>
        </svg>
        <div class="step-caption" style="color:#633806;">Numerator = 3</div>
      </div>
    </div>
  </div>

  <!-- EXAMPLE 4 -->
  <div class="card">
    <div class="card-title">Example 4 — Shade <span style="color:#534AB7;">2/4</span> of a square</div>
    <div class="steps-row">
      <div class="step-box">
        <div class="step-num" style="color:#3C3489;">Step 1</div>
        <svg class="shape-svg" width="70" height="70" viewBox="0 0 70 70">
          <rect x="5" y="5" width="60" height="60" rx="3" fill="none" stroke="#7F77DD" stroke-width="1.5"/>
        </svg>
        <div class="step-caption" style="color:#3C3489;">Empty square</div>
      </div>
      <div class="step-arrow">&#8594;</div>
      <div class="step-box">
        <div class="step-num" style="color:#3C3489;">Step 2 — 4 equal parts</div>
        <svg class="shape-svg" width="70" height="70" viewBox="0 0 70 70">
          <rect x="5" y="5" width="60" height="60" rx="3" fill="none" stroke="#7F77DD" stroke-width="1.5"/>
          <line x1="35" y1="5" x2="35" y2="65" stroke="#7F77DD" stroke-width="1"/>
          <line x1="5" y1="35" x2="65" y2="35" stroke="#7F77DD" stroke-width="1"/>
        </svg>
        <div class="step-caption" style="color:#3C3489;">Denominator = 4</div>
      </div>
      <div class="step-arrow">&#8594;</div>
      <div class="step-box">
        <div class="step-num" style="color:#3C3489;">Step 3 — Shade 2 parts</div>
        <svg class="shape-svg" width="70" height="70" viewBox="0 0 70 70">
          <rect x="5" y="5" width="30" height="30" fill="#AFA9EC" opacity="0.85"/>
          <rect x="35" y="35" width="30" height="30" fill="#AFA9EC" opacity="0.85"/>
          <rect x="5" y="5" width="60" height="60" rx="3" fill="none" stroke="#534AB7" stroke-width="1.5"/>
          <line x1="35" y1="5" x2="35" y2="65" stroke="#534AB7" stroke-width="1"/>
          <line x1="5" y1="35" x2="65" y2="35" stroke="#534AB7" stroke-width="1"/>
        </svg>
        <div class="step-caption" style="color:#3C3489;">Numerator = 2</div>
      </div>
    </div>
  </div>

  <!-- EXERCISES -->
  <div class="card" style="border-color:#B5D4F4;">
    <div class="card-title" style="color:#0C447C;">Exercises — Task Set 1</div>
    <div class="card-body" style="margin-bottom:10px;">Draw or describe your answers. Show all three steps for each shape question.</div>
    <div class="exercise-list">
      <div class="exercise-item">
        <div class="ex-num">1</div>
        <div class="ex-text">Shade <strong>1/2</strong> of a rectangle. How many equal parts will you draw? How many will you shade?
          <span class="ex-tag" style="background:#E6F1FB;color:#0C447C;">Rectangle</span>
        </div>
      </div>
      <div class="exercise-item">
        <div class="ex-num">2</div>
        <div class="ex-text">Shade <strong>3/4</strong> of a rectangle. Write one sentence explaining what the 4 means.
          <span class="ex-tag" style="background:#E6F1FB;color:#0C447C;">Rectangle</span>
        </div>
      </div>
      <div class="exercise-item">
        <div class="ex-num">3</div>
        <div class="ex-text">Shade <strong>2/5</strong> of a rectangle.
          <span class="ex-tag" style="background:#E6F1FB;color:#0C447C;">Rectangle</span>
        </div>
      </div>
      <div class="exercise-item">
        <div class="exercise-item"><div class="ex-num">4</div>
        <div class="ex-text">Shade <strong>2/4</strong> of a rectangle. Are 2/4 and 1/2 the same? 
            <span class="ex-shape-tag" style="background:var(--green-light);color:var(--green-dark);">Check</span></div></div>
        </div>
      </div>
      <div class="exercise-item">
        <div class="ex-num">5</div>
        <div class="ex-text">A pizza is cut into 6 equal slices. You eat 2 slices. Write the fraction and shade a rectangle to show it.
          <span class="ex-tag" style="background:#FAEEDA;color:#633806;">Word problem</span>
        </div>
      </div>
      <div class="exercise-item">
        <div class="ex-num">6</div>
        <div class="ex-text">Shade <strong>4/6</strong> of a rectangle.
          <span class="ex-tag" style="background:#E6F1FB;color:#0C447C;">Rectangle</span>
        </div>
      </div>
      <div class="exercise-item">
        <div class="ex-num">7</div>
        <div class="ex-text">Shade <strong>1/5</strong> of a rectangle. Then write: the denominator is ___ and the numerator is ___.
          <span class="ex-tag" style="background:#E6F1FB;color:#0C447C;">Rectangle</span>
        </div>
      </div>
      <div class="exercise-item">
        <div class="ex-num">8</div>
        <div class="ex-text">A chocolate bar has 4 equal pieces. Dad eats 1 piece. What fraction is left? Shade a rectangle to show the amount Dad ate.
          <span class="ex-tag" style="background:#FAEEDA;color:#633806;">Word problem</span>
        </div>
      </div>
      <div class="exercise-item">
        <div class="ex-num">9</div>
        <div class="ex-text">Shade <strong>3/3</strong> of a rectangle. What do you notice? What does this tell you?
          <span class="ex-tag" style="background:#EAF3DE;color:#27500A;">Think deeper</span>
        </div>
      </div>
      <div class="exercise-item">
        <div class="ex-num" style="background:#FAECE7;color:#712B13;">10</div>
        <div class="ex-text">BOSS LEVEL: Tom shaded 3 parts of a rectangle. He says the fraction is 3/5 but his rectangle only has 4 parts. Is Tom right? Explain why.
          <span class="ex-tag" style="background:#FAECE7;color:#712B13;">Boss level</span>
        </div>
      </div>
    </div>
  </div>

`;
/* ---- END OF TASK 1 ---- */


/* ----------------------------------------------------------
   HOW TO ADD TASK 2 WHEN IT IS READY
   ----------------------------------------------------------
   1. Copy the block below (remove the comment markers /* and *\/)
   2. Replace the placeholder text with your actual lesson HTML
   3. In the WEEKS array further down, find week 1 tab t2
      and change:  content: null
      to:          content: { title: 'Study Review — Saturday 4 March', body: TASK2_CONTENT }
   That is the only change needed. Nothing else in the file changes.
   ---------------------------------------------------------- */

/*
const TASK2_CONTENT = `

  <div class="day-header">
    <div class="day-icon" style="background:#EAF3DE;color:#27500A;border:0.5px solid #C0DD97;">2</div>
    <div>
      <div class="day-label" style="color:#27500A;">Study Review — Saturday, 4 March 2026</div>
      <div class="day-sub">Topic: Revisit and practise fraction shading</div>
    </div>
  </div>

  <div class="card" style="border-color:#C0DD97;">
    <div class="card-title" style="color:#27500A;">Your lesson content goes here</div>
    <div class="card-body">Add your examples, diagrams and exercises for this session.</div>
  </div>

`;
*/
/* ---- END OF TASK 2 TEMPLATE ---- */


/* ============================================================
   WEEKS DATA ARRAY
   Set content: null for any tab not yet written.
   Set content: { title:'...', body: TASKX_CONTENT } when ready.
   ============================================================ */
const WEEKS = [
  {
    weekNum: 1,
    colorIdx: 0,
    open: true,
    unlocked: true,
    tabs: [
      {
        id: 't1',
        label: 'Task Set 1 — 3 Mar 2026',
        type: 'task',
        content: {
          title: 'Task Set 1 — Introduction to fractions',
          body: TASK1_CONTENT        /* <-- TASK 1 IS LIVE */
        }
      },
      {
        id: 't2',
        label: 'Study Review — Sat, 4 Mar',
        type: 'review',
        content: null                /* <-- CHANGE TO: { title:'...', body: TASK2_CONTENT } WHEN READY */
      },
      {
        id: 't3',
        label: 'Study Review — Sun, 5 Mar',
        type: 'review',
        content: null                /* <-- CHANGE TO: { title:'...', body: TASK3_CONTENT } WHEN READY */
      },
      {
        id: 't4',
        label: 'Weekly Revision — Sun, 5 Mar',
        type: 'revision',
        content: null                /* <-- CHANGE TO: { title:'...', body: TASK4_CONTENT } WHEN READY */
      },
    ]
  },
  {
    weekNum: 2,
    colorIdx: 1,
    open: false,
    unlocked: false,
    unlockedAfter: 'Sunday, 5 March 2026',
    tabs: [
      { id:'t5',  label:'Task Set 2 — 9 Mar 2026',       type:'task',     content: null },
      { id:'t6',  label:'Task Set 3 — 9 Mar 2026',       type:'task',     content: null },
      { id:'t7',  label:'Study Review — Sat, 11 Mar',    type:'review',   content: null },
      { id:'t8',  label:'Study Review — Sun, 12 Mar',    type:'review',   content: null },
      { id:'t9',  label:'Weekly Revision — Sun, 12 Mar', type:'revision', content: null },
    ]
  },
  {
    weekNum: 3,
    colorIdx: 2,
    open: false,
    unlocked: false,
    unlockedAfter: 'Sunday, 12 March 2026',
    tabs: [
      { id:'t10', label:'Task Set 4 — 16 Mar 2026',      type:'task',     content: null },
      { id:'t11', label:'Task Set 5 — 18 Mar 2026',      type:'task',     content: null },
      { id:'t12', label:'Study Review — Sat, 18 Mar',    type:'review',   content: null },
      { id:'t13', label:'Study Review — Sun, 19 Mar',    type:'review',   content: null },
      { id:'t14', label:'Weekly Revision — Sun, 19 Mar', type:'revision', content: null },
    ]
  },
  {
    weekNum: 4,
    colorIdx: 3,
    open: false,
    unlocked: false,
    unlockedAfter: 'Sunday, 19 March 2026',
    tabs: [
      { id:'t15', label:'Task Set 6 — 23 Mar 2026',      type:'task',     content: null },
      { id:'t16', label:'Task Set 7 — 25 Mar 2026',      type:'task',     content: null },
      { id:'t17', label:'Study Review — Sat, 25 Mar',    type:'review',   content: null },
      { id:'t18', label:'Study Review — Sun, 26 Mar',    type:'review',   content: null },
      { id:'t19', label:'Weekly Revision — Sun, 26 Mar', type:'revision', content: null },
    ]
  },
];


/* ============================================================
   ENGINE — do not edit anything below this line
   ============================================================ */

function renderEmpty(tab, week, col) {
  const tc = TAB_TYPE[tab.type];
  return `
    <div class="empty-state">
      <div class="empty-icon">
        <svg width="20" height="20" viewBox="0 0 20 20" fill="none">
          <circle cx="10" cy="10" r="8.5" stroke="#bbb" stroke-width="1.2"/>
          <path d="M10 6v4l2.5 2.5" stroke="#bbb" stroke-width="1.2" stroke-linecap="round"/>
        </svg>
      </div>
      <div class="empty-title">Not yet available</div>
      <div class="empty-sub">The content for <strong>${tab.label}</strong> has not been added yet. Your teacher will upload this lesson on time — check back soon.</div>
      <div style="margin-top:8px;">
        <span class="gap-label" style="background:${col.light};color:${col.text};border:0.5px solid ${col.border};">${COLORS[week.colorIdx].gap}</span>
        <span class="gap-label" style="background:${tc.bg};color:${tc.text};">${tc.label}</span>
      </div>
    </div>
  `;
}

function renderContent(tab, week, col) {
  if (!tab.content) return renderEmpty(tab, week, col);
  const tc = TAB_TYPE[tab.type];
  return `
    <div style="margin-bottom:14px;">
      <span class="gap-label" style="background:${col.light};color:${col.text};border:0.5px solid ${col.border};">${COLORS[week.colorIdx].gap}</span>
      <span class="gap-label" style="background:${tc.bg};color:${tc.text};">${tc.label}</span>
    </div>
    ${tab.content.body}
  `;
}

function selectTab(btn, tab, week, col) {
  document.querySelectorAll('.tab').forEach(t => {
    t.classList.remove('active');
    t.style.background = '';
    t.style.color = '';
    t.style.borderColor = '';
  });
  btn.classList.add('active');
  btn.style.background = col.active;
  btn.style.color = 'white';
  btn.style.borderColor = col.active;

  const area = document.getElementById('content-area');
  area.classList.remove('hidden');
  area.innerHTML = renderContent(tab, week, col);
  area.scrollIntoView({ behavior: 'smooth', block: 'start' });
}

function build() {
  const container = document.getElementById('week-groups');
  WEEKS.forEach((week, wi) => {
    const col = COLORS[week.colorIdx];

    const grp = document.createElement('div');
    grp.className = 'week-group';
    grp.style.borderColor = col.border;

    const hdr = document.createElement('div');
    hdr.className = 'week-header';
    hdr.style.background = col.light;
    hdr.innerHTML = `
      <div class="week-dot" style="background:${col.dot};color:${col.dotTxt};">W${week.weekNum}</div>
      <div class="week-title" style="color:${col.text};">${col.gap}</div>
      <div class="week-meta" style="color:${col.text};">${week.unlocked ? 'Available now' : 'Unlocks after ' + week.unlockedAfter}</div>
      <div class="week-arrow${week.open ? ' open' : ''}" id="arr-${wi}" style="color:${col.text};">&#9654;</div>
    `;

    const tabsDiv = document.createElement('div');
    tabsDiv.id = 'tabs-' + wi;
    tabsDiv.className = 'week-tabs' + (week.open ? ' open' : '');

    if (!week.unlocked) {
      tabsDiv.innerHTML = `
        <div style="display:flex;align-items:center;gap:8px;padding:8px 4px;">
          <svg width="13" height="13" viewBox="0 0 14 14" fill="none">
            <rect x="3" y="6" width="8" height="6" rx="1.5" stroke="${col.text}" stroke-width="1.2" opacity="0.5"/>
            <path d="M5 6V4.5a2 2 0 0 1 4 0V6" stroke="${col.text}" stroke-width="1.2" fill="none" stroke-linecap="round" opacity="0.5"/>
          </svg>
          <span style="font-size:12px;color:${col.text};opacity:0.65;">Available after ${week.unlockedAfter}. Lessons will appear here on time.</span>
        </div>`;
    } else {
      week.tabs.forEach(tab => {
        const hasContent = !!tab.content;
        const btn = document.createElement('button');
        btn.className = 'tab';
        btn.innerHTML = `
          <span style="display:inline-block;width:6px;height:6px;border-radius:50%;background:${hasContent ? col.active : '#ccc'};margin-right:5px;vertical-align:middle;"></span>
          <span style="opacity:${hasContent ? 1 : 0.6};">${tab.label}</span>
        `;
        btn.onclick = () => selectTab(btn, tab, week, col);
        tabsDiv.appendChild(btn);
      });
    }

    hdr.onclick = () => {
      const td = document.getElementById('tabs-' + wi);
      const ar = document.getElementById('arr-' + wi);
      const isOpen = td.classList.contains('open');
      td.classList.toggle('open', !isOpen);
      ar.classList.toggle('open', !isOpen);
    };

    grp.appendChild(hdr);
    grp.appendChild(tabsDiv);
    container.appendChild(grp);
  });
}

build();

</script>
</body>
</html>
