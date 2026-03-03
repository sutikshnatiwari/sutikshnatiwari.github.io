/* ===================================================
   SUNNY TIWARI — PORTFOLIO STYLESHEET
   =================================================== */

@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap');

*, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

:root {
  --bg:     #080c14;
  --bg2:    #0d1220;
  --bg3:    #111827;
  --neon:   #00f5c4;
  --neon2:  #00b8ff;
  --text:   #e2e8f0;
  --muted:  #64748b;
  --border: rgba(0,245,196,0.12);
  --card:   rgba(255,255,255,0.03);
}

html { scroll-behavior: smooth; }
body { font-family: 'Inter', sans-serif; background: var(--bg); color: var(--text); overflow-x: hidden; }

/* SCROLLBAR */
::-webkit-scrollbar { width: 5px; }
::-webkit-scrollbar-track { background: var(--bg); }
::-webkit-scrollbar-thumb { background: var(--neon); border-radius: 10px; }

/* ── NAV ── */
nav {
  position: fixed; top: 0; width: 100%; z-index: 100;
  padding: 18px 60px;
  display: flex; justify-content: space-between; align-items: center;
  background: rgba(8,12,20,0.88);
  backdrop-filter: blur(16px);
  border-bottom: 1px solid var(--border);
  transition: padding 0.3s;
}
nav.scrolled { padding: 12px 60px; }
.logo { font-size: 1.2rem; font-weight: 800; background: linear-gradient(135deg, var(--neon), var(--neon2)); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
.nav-links { display: flex; gap: 30px; list-style: none; }
.nav-links a { color: var(--muted); text-decoration: none; font-size: 0.8rem; font-weight: 600; letter-spacing: .5px; text-transform: uppercase; transition: color .3s; }
.nav-links a:hover, .nav-links a.active { color: var(--neon); }

/* ── HERO ── */
#hero {
  min-height: 100vh; display: flex; align-items: center; justify-content: center;
  position: relative; overflow: hidden; padding: 100px 60px 60px;
}
.hero-bg {
  position: absolute; inset: 0; z-index: 0;
  background:
    radial-gradient(ellipse 80% 60% at 70% 50%, rgba(0,245,196,0.07) 0%, transparent 60%),
    radial-gradient(ellipse 60% 50% at 20% 80%, rgba(0,184,255,0.05) 0%, transparent 60%);
}
.grid-overlay {
  position: absolute; inset: 0; z-index: 0;
  background-image:
    linear-gradient(rgba(0,245,196,0.04) 1px, transparent 1px),
    linear-gradient(90deg, rgba(0,245,196,0.04) 1px, transparent 1px);
  background-size: 50px 50px;
}
.hero-inner {
  position: relative; z-index: 1; max-width: 1100px; width: 100%;
  display: flex; align-items: center; justify-content: space-between; gap: 60px;
}
.hero-text { flex: 1; }

.hero-badge {
  display: inline-flex; align-items: center; gap: 8px;
  padding: 6px 16px; border-radius: 100px;
  border: 1px solid var(--border); background: rgba(0,245,196,0.05);
  font-size: 0.72rem; font-weight: 700; color: var(--neon);
  text-transform: uppercase; letter-spacing: 1px; margin-bottom: 24px;
}
.hero-badge .dot {
  width: 6px; height: 6px; border-radius: 50%;
  background: var(--neon); animation: pulse 2s infinite;
}

@keyframes pulse { 0%,100%{opacity:1} 50%{opacity:0.3} }
@keyframes fadeUp { from{opacity:0;transform:translateY(24px)} to{opacity:1;transform:translateY(0)} }

h1 { font-size: clamp(2.6rem,5vw,4.2rem); font-weight: 900; line-height: 1.05; letter-spacing: -2px; margin-bottom: 20px; }
h1 .name { background: linear-gradient(135deg, #fff 30%, var(--neon)); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
h1 .role { color: var(--neon); }

.hero-desc { font-size: 1rem; color: var(--muted); line-height: 1.8; max-width: 520px; margin-bottom: 16px; }
.hero-desc strong { color: var(--text); }

.hero-pills { display: flex; flex-wrap: wrap; gap: 8px; margin-bottom: 36px; }
.pill { padding: 4px 13px; border-radius: 100px; font-size: 0.7rem; font-weight: 700; text-transform: uppercase; letter-spacing: .5px; background: rgba(0,245,196,0.07); color: var(--neon); border: 1px solid rgba(0,245,196,0.2); }

.hero-cta { display: flex; gap: 16px; flex-wrap: wrap; }

.btn-primary {
  padding: 13px 30px; border-radius: 8px; font-weight: 700; font-size: 0.88rem;
  cursor: pointer; text-decoration: none;
  background: linear-gradient(135deg, var(--neon), var(--neon2)); color: #000;
  border: none; transition: transform .2s, box-shadow .2s;
  box-shadow: 0 0 28px rgba(0,245,196,0.25);
}
.btn-primary:hover { transform: translateY(-2px); box-shadow: 0 0 40px rgba(0,245,196,0.4); }

.btn-outline {
  padding: 13px 30px; border-radius: 8px; font-weight: 600; font-size: 0.88rem;
  cursor: pointer; text-decoration: none;
  background: transparent; color: var(--text); border: 1px solid var(--border); transition: all .2s;
}
.btn-outline:hover { border-color: var(--neon); color: var(--neon); }

.hero-avatar {
  width: 300px; height: 340px; flex-shrink: 0;
  border-radius: 24px; overflow: hidden;
  border: 1px solid var(--border);
  box-shadow: 0 0 60px rgba(0,245,196,0.1);
  position: relative;
}
.hero-avatar::before {
  content: ''; position: absolute; inset: -1px;
  background: linear-gradient(135deg, var(--neon), transparent, var(--neon2));
  border-radius: 24px; z-index: -1; opacity: 0.3;
}
.hero-avatar img { width: 100%; height: 100%; object-fit: cover; object-position: center top; display: block; }

/* ── SECTION BASE ── */
section { padding: 96px 60px; max-width: 1200px; margin: 0 auto; }
.band { background: var(--bg2); }
.band .inner { max-width: 1100px; margin: 0 auto; padding: 96px 60px; }

.section-label {
  display: inline-flex; align-items: center; gap: 10px;
  font-size: 0.72rem; font-weight: 700; text-transform: uppercase;
  letter-spacing: 2px; color: var(--neon); margin-bottom: 14px;
}
.section-label::before { content: ''; width: 26px; height: 2px; background: var(--neon); }

h2 { font-size: clamp(1.9rem,3.5vw,2.6rem); font-weight: 800; letter-spacing: -1px; margin-bottom: 14px; }
.section-sub { color: var(--muted); font-size: 0.93rem; line-height: 1.65; max-width: 560px; margin-bottom: 52px; }

/* ── ABOUT ── */
.about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 56px; align-items: start; }
.about-bio p { color: var(--muted); line-height: 1.9; margin-bottom: 15px; font-size: 0.92rem; }
.about-bio p strong { color: var(--text); }
.stats-row { display: flex; gap: 26px; margin-top: 26px; flex-wrap: wrap; }
.stat { border-left: 2px solid var(--neon); padding-left: 14px; }
.stat-num { font-size: 1.65rem; font-weight: 800; color: var(--neon); line-height: 1; }
.stat-label { font-size: 0.68rem; color: var(--muted); text-transform: uppercase; letter-spacing: 1px; margin-top: 4px; }

.about-cards { display: flex; flex-direction: column; gap: 14px; }
.about-card { background: var(--card); border: 1px solid var(--border); border-radius: 14px; padding: 18px; display: flex; gap: 15px; align-items: flex-start; transition: border-color .3s, transform .3s; }
.about-card:hover { border-color: rgba(0,245,196,0.3); transform: translateX(4px); }
.card-icon { width: 40px; height: 40px; border-radius: 10px; flex-shrink: 0; background: rgba(0,245,196,0.08); border: 1px solid var(--border); display: flex; align-items: center; justify-content: center; font-size: 1rem; }
.card-title { font-weight: 700; margin-bottom: 4px; font-size: 0.88rem; }
.card-body { color: var(--muted); font-size: 0.8rem; line-height: 1.6; }

/* ── TIMELINE ── */
.timeline { position: relative; }
.timeline::before { content: ''; position: absolute; left: 19px; top: 4px; bottom: 4px; width: 2px; background: linear-gradient(to bottom, var(--neon), var(--neon2), transparent); }
.tl-item { display: flex; gap: 26px; padding-bottom: 40px; position: relative; }
.tl-dot { width: 40px; height: 40px; border-radius: 50%; background: var(--bg3); border: 2px solid var(--neon); display: flex; align-items: center; justify-content: center; font-size: 1rem; flex-shrink: 0; z-index: 1; margin-top: 2px; transition: background .3s; }
.tl-item:hover .tl-dot { background: rgba(0,245,196,0.1); }
.tl-content { flex: 1; }
.tl-header { display: flex; justify-content: space-between; align-items: flex-start; flex-wrap: wrap; gap: 8px; margin-bottom: 5px; }
.tl-role { font-weight: 800; font-size: 0.98rem; }
.tl-date { font-size: 0.72rem; color: var(--neon); font-weight: 700; background: rgba(0,245,196,0.08); padding: 3px 11px; border-radius: 100px; border: 1px solid rgba(0,245,196,0.2); white-space: nowrap; }
.tl-company { color: var(--neon2); font-size: 0.83rem; font-weight: 600; margin-bottom: 12px; }
.tl-bullets { list-style: none; display: flex; flex-direction: column; gap: 8px; }
.tl-bullets li { color: var(--muted); font-size: 0.83rem; line-height: 1.7; padding-left: 18px; position: relative; }
.tl-bullets li::before { content: '→'; position: absolute; left: 0; color: var(--neon); font-size: 0.72rem; top: 1px; }
.tl-bullets li strong { color: var(--text); }

/* ── SKILLS ── */
.skills-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(250px, 1fr)); gap: 20px; }
.skill-category { background: var(--card); border: 1px solid var(--border); border-radius: 18px; padding: 24px; transition: transform .3s, border-color .3s; }
.skill-category:hover { transform: translateY(-4px); border-color: rgba(0,245,196,0.25); }
.skill-cat-header { display: flex; align-items: center; gap: 11px; margin-bottom: 18px; }
.skill-cat-icon { width: 36px; height: 36px; border-radius: 10px; background: linear-gradient(135deg, rgba(0,245,196,0.12), rgba(0,184,255,0.08)); display: flex; align-items: center; justify-content: center; font-size: 0.95rem; }
.skill-cat-name { font-weight: 700; font-size: 0.9rem; }
.skill-item { margin-bottom: 12px; }
.skill-row { display: flex; justify-content: space-between; margin-bottom: 5px; }
.skill-name { font-size: 0.78rem; color: var(--muted); }
.skill-pct { font-size: 0.78rem; color: var(--neon); font-weight: 700; }
.skill-bar { height: 4px; background: rgba(255,255,255,0.06); border-radius: 10px; overflow: hidden; }
.skill-fill { height: 100%; border-radius: 10px; background: linear-gradient(90deg, var(--neon), var(--neon2)); width: 0; transition: width 1.2s cubic-bezier(.4,0,.2,1); }

/* ── PROJECTS ── */
.projects-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(310px, 1fr)); gap: 24px; }
.project-card { background: var(--card); border: 1px solid var(--border); border-radius: 20px; overflow: hidden; transition: transform .3s, border-color .3s, box-shadow .3s; }
.project-card:hover { transform: translateY(-6px); border-color: rgba(0,245,196,0.3); box-shadow: 0 20px 50px rgba(0,0,0,0.4); }
.project-banner { height: 120px; display: flex; align-items: center; justify-content: center; font-size: 2.3rem; }
.project-body { padding: 20px; }
.project-tags { display: flex; flex-wrap: wrap; gap: 6px; margin-bottom: 11px; }
.tag { padding: 3px 9px; border-radius: 100px; font-size: 0.67rem; font-weight: 700; text-transform: uppercase; letter-spacing: .5px; background: rgba(0,245,196,0.07); color: var(--neon); border: 1px solid rgba(0,245,196,0.18); }
.tag.blue { background: rgba(0,184,255,0.07); color: var(--neon2); border-color: rgba(0,184,255,0.18); }
.project-title { font-size: 0.97rem; font-weight: 800; margin-bottom: 9px; }
.project-desc { color: var(--muted); font-size: 0.81rem; line-height: 1.75; }
.project-impact { display: flex; flex-wrap: wrap; gap: 7px; margin-top: 13px; }
.impact-chip { font-size: 0.7rem; font-weight: 700; padding: 3px 10px; border-radius: 6px; background: rgba(0,245,196,0.06); border: 1px solid rgba(0,245,196,0.14); color: var(--neon); }

/* ── ACADEMIC ── */
.academic-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 22px; }
.academic-card { background: var(--card); border: 1px solid var(--border); border-radius: 18px; padding: 24px; transition: transform .3s, border-color .3s; }
.academic-card:hover { transform: translateY(-4px); border-color: rgba(0,184,255,0.3); }
.academic-type { display: inline-block; padding: 3px 11px; border-radius: 100px; font-size: 0.67rem; font-weight: 700; text-transform: uppercase; letter-spacing: 1px; background: rgba(0,184,255,0.08); color: var(--neon2); border: 1px solid rgba(0,184,255,0.2); margin-bottom: 12px; }
.academic-title { font-size: 0.95rem; font-weight: 700; margin-bottom: 7px; }
.academic-meta { color: var(--neon); font-size: 0.78rem; font-weight: 600; margin-bottom: 9px; }
.academic-desc { color: var(--muted); font-size: 0.81rem; line-height: 1.7; }
.grade-badge { display: inline-flex; align-items: center; gap: 5px; margin-top: 13px; padding: 4px 13px; border-radius: 8px; background: rgba(0,245,196,0.05); border: 1px solid var(--border); font-size: 0.76rem; font-weight: 700; color: var(--neon); }

/* ── CONTACT ── */
.contact-wrapper { display: grid; grid-template-columns: 1fr 1fr; gap: 50px; align-items: start; }
.contact-info { display: flex; flex-direction: column; gap: 14px; }
.contact-item { display: flex; align-items: center; gap: 15px; background: var(--card); border: 1px solid var(--border); border-radius: 13px; padding: 16px 18px; transition: border-color .3s; text-decoration: none; }
.contact-item:hover { border-color: rgba(0,245,196,0.3); }
.contact-ico { width: 38px; height: 38px; border-radius: 10px; background: rgba(0,245,196,0.07); display: flex; align-items: center; justify-content: center; font-size: 1rem; flex-shrink: 0; }
.contact-label { font-size: 0.7rem; color: var(--muted); margin-bottom: 2px; }
.contact-value { font-size: 0.86rem; font-weight: 600; color: var(--text); }
.contact-form { display: flex; flex-direction: column; gap: 13px; }
.form-group { display: flex; flex-direction: column; gap: 6px; }
label { font-size: 0.72rem; font-weight: 700; color: var(--muted); text-transform: uppercase; letter-spacing: .5px; }
input, textarea { background: var(--card); border: 1px solid var(--border); border-radius: 9px; padding: 12px 14px; color: var(--text); font-family: inherit; font-size: 0.86rem; outline: none; transition: border-color .3s; }
input:focus, textarea:focus { border-color: var(--neon); }
textarea { resize: vertical; min-height: 105px; }
.form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 13px; }
.submit-btn { width: 100%; text-align: center; cursor: pointer; font-family: inherit; }

/* ── TOAST ── */
.toast {
  position: fixed; bottom: 30px; right: 30px; z-index: 999;
  background: var(--neon); color: #000; font-weight: 700; font-size: 0.85rem;
  padding: 14px 24px; border-radius: 10px;
  box-shadow: 0 8px 30px rgba(0,245,196,0.3);
  transform: translateY(80px); opacity: 0;
  transition: all 0.4s cubic-bezier(.4,0,.2,1);
}
.toast.show { transform: translateY(0); opacity: 1; }

/* ── FOOTER ── */
footer { text-align: center; padding: 34px 60px; border-top: 1px solid var(--border); color: var(--muted); font-size: 0.78rem; }
footer span { color: var(--neon); }

/* ── FADE-IN ANIMATION ── */
.fade-in { opacity: 0; transform: translateY(20px); transition: opacity 0.6s ease, transform 0.6s ease; }
.fade-in.visible { opacity: 1; transform: translateY(0); }

/* ── RESPONSIVE ── */
@media (max-width: 900px) {
  nav { padding: 15px 20px; }
  nav.scrolled { padding: 10px 20px; }
  .nav-links { gap: 16px; }
  section { padding: 64px 20px; }
  #hero { padding: 88px 20px 48px; }
  .hero-inner { flex-direction: column-reverse; text-align: center; }
  .hero-cta { justify-content: center; }
  .hero-pills { justify-content: center; }
  .hero-avatar { width: 200px; height: 230px; }
  .about-grid, .contact-wrapper, .academic-grid { grid-template-columns: 1fr; }
  .band .inner { padding: 64px 20px; }
  .stats-row { justify-content: center; }
  footer { padding: 24px 20px; }
}

@media (max-width: 500px) {
  .nav-links { display: none; }
  h1 { letter-spacing: -1px; }
}
