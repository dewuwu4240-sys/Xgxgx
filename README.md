<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta name="theme-color" content="#090d18">
  <meta name="description" content="THE CONTROL — a free game development team management dashboard.">
  <title>THE CONTROL — Game Development Management</title>
  <link rel="stylesheet" href="style.css">
  <script src="script.js" defer></script>
</head>
<body>
  <div class="app-shell">
    <aside class="sidebar" id="sidebar">
      <a class="brand" href="#" data-page="dashboard" aria-label="THE CONTROL dashboard">
        <span class="brand-mark">T<span>C</span></span>
        <span class="brand-copy"><strong>THE CONTROL</strong><small>GAME DEV OS · v1.0</small></span>
      </a>

      <div class="sidebar-label" data-i18n="workspace">WORKSPACE</div>
      <nav class="main-nav" aria-label="Main navigation">
        <button class="nav-link active" data-page="dashboard"><span>◫</span><span data-i18n="dashboard">Dashboard</span></button>
        <button class="nav-link" data-page="team-a"><span>◉</span><span data-i18n="teamA">Team A · Guest</span><span class="nav-count">24</span></button>
        <button class="nav-link" data-page="team-b"><span>◉</span><span data-i18n="teamB">Team B · Member</span><span class="nav-count">24</span></button>
        <button class="nav-link" data-page="projects"><span>▤</span><span data-i18n="projects">Projects</span></button>
      </nav>

      <div class="sidebar-label nav-section-label" data-i18n="management">MANAGEMENT</div>
      <button class="nav-link" data-page="tasks"><span>☷</span><span data-i18n="allTasks">All tasks</span></button>

      <div class="sidebar-bottom">
        <div class="plan-card">
          <span class="plan-icon">✦</span>
          <strong data-i18n="freeForever">Free forever</strong>
          <p data-i18n="freeNote">No paid packages. Choose Guest or local Member demo.</p>
          <button class="text-button" id="package-button" data-i18n="managePackage">Choose package →</button>
        </div>
        <p class="sidebar-foot">THE CONTROL <span>·</span> 1.0.0</p>
      </div>
    </aside>

    <main class="main-content">
      <header class="topbar">
        <button class="mobile-menu icon-button" id="menu-button" aria-label="Open navigation">☰</button>
        <div class="breadcrumb"><span data-i18n="workspace">WORKSPACE</span><span class="crumb-separator">/</span><strong id="page-title">Dashboard</strong></div>
        <div class="top-actions">
          <span class="package-pill" id="package-pill">FREE GUEST</span>
          <button class="language-switch" id="language-button" aria-label="Switch language">TH <span>↔</span> EN</button>
          <button class="avatar-button" id="user-button" aria-label="Membership settings">G</button>
        </div>
      </header>

      <div class="page-content">
        <section class="view active" id="view-dashboard">
          <div class="welcome-row">
            <div>
              <p class="eyebrow" data-i18n="overview">TEAM OVERVIEW</p>
              <h1><span data-i18n="welcome">Welcome to</span> <span class="gradient-text">THE CONTROL</span></h1>
              <p class="subheading" data-i18n="dashboardIntro">Your game development team, projects, and tasks in one place.</p>
            </div>
            <button class="primary-button" data-action="new-task"><span>＋</span> <span data-i18n="newTask">New task</span></button>
          </div>

          <div class="stats-grid" id="stats-grid"></div>

          <div class="dashboard-grid">
            <section class="panel project-panel">
              <div class="panel-heading">
                <div><p class="eyebrow" data-i18n="projectSpace">PROJECT SPACE</p><h2 data-i18n="yourProjects">Your projects</h2></div>
                <button class="subtle-button" data-page="projects"><span data-i18n="viewAll">View all</span> ↗</button>
              </div>
              <div id="dashboard-projects" class="project-list"></div>
            </section>

            <section class="panel task-panel">
              <div class="panel-heading">
                <div><p class="eyebrow" data-i18n="theQueue">THE QUEUE</p><h2 data-i18n="recentTasks">Recent tasks</h2></div>
                <button class="subtle-button" data-page="tasks"><span data-i18n="viewAll">View all</span> ↗</button>
              </div>
              <div id="dashboard-tasks" class="task-list compact-list"></div>
            </section>
          </div>

          <section class="panel team-preview">
            <div class="panel-heading">
              <div><p class="eyebrow" data-i18n="roster">ROSTER</p><h2 data-i18n="yourSkills">Your Skills</h2></div>
              <span class="muted" id="team-preview-count"></span>
            </div>
            <div class="skill-grid" id="dashboard-skills"></div>
          </section>
        </section>

        <section class="view" id="view-team-a">
          <div class="page-heading">
            <div><p class="eyebrow">01 — 24</p><h1 data-i18n="teamA">Team A · Guest</h1><p class="subheading" data-i18n="teamAIntro">Core game development Skills, available to everyone.</p></div>
            <button class="primary-button" data-action="new-task">＋ <span data-i18n="newTask">New task</span></button>
          </div>
          <div class="filter-bar">
            <label class="search-box"><span>⌕</span><input id="skill-search-a" type="search" data-i18n-placeholder="searchSkills" placeholder="Search Skills…"></label>
            <select id="category-filter-a" aria-label="Filter by category"></select>
            <select id="status-filter-a" aria-label="Filter by status"></select>
          </div>
          <div class="skill-grid" id="team-a-skills"></div>
          <p class="empty-state hidden" id="team-a-empty" data-i18n="noSkills">No Skills match those filters.</p>
        </section>

        <section class="view" id="view-team-b">
          <div class="page-heading">
            <div><p class="eyebrow">25 — 48</p><h1 data-i18n="teamB">Team B · Member</h1><p class="subheading" data-i18n="teamBIntro">Specialist Skills available in Free Member mode.</p></div>
            <button class="primary-button" data-action="new-task">＋ <span data-i18n="newTask">New task</span></button>
          </div>
          <div class="filter-bar">
            <label class="search-box"><span>⌕</span><input id="skill-search-b" type="search" data-i18n-placeholder="searchSkills" placeholder="Search Skills…"></label>
            <select id="category-filter-b" aria-label="Filter by category"></select>
            <select id="status-filter-b" aria-label="Filter by status"></select>
          </div>
          <div class="skill-grid" id="team-b-skills"></div>
          <p class="empty-state hidden" id="team-b-empty" data-i18n="noSkills">No Skills match those filters.</p>
          <div class="locked-banner hidden" id="team-b-locked">
            <span class="locked-icon">🔒</span><div><strong data-i18n="memberSkillsLocked">Team B is locked in Guest mode</strong><p data-i18n="memberSkillsLockedNote">Switch to the free local Member demo to view all 48 Skills.</p></div>
            <button class="primary-button" id="unlock-member-button" data-i18n="tryMember">Try Member demo</button>
          </div>
        </section>

        <section class="view" id="view-projects">
          <div class="page-heading">
            <div><p class="eyebrow" data-i18n="projectSpace">PROJECT SPACE</p><h1 data-i18n="projects">Projects</h1><p class="subheading" data-i18n="projectsIntro">Plan work, track progress, and keep your team aligned.</p></div>
            <button class="primary-button" data-action="new-project">＋ <span data-i18n="newProject">New project</span></button>
          </div>
          <div class="project-grid" id="projects-grid"></div>
          <p class="empty-state hidden" id="projects-empty" data-i18n="noProjects">No projects yet. Create one to get started.</p>
        </section>

        <section class="view" id="view-tasks">
          <div class="page-heading">
            <div><p class="eyebrow" data-i18n="theQueue">THE QUEUE</p><h1 data-i18n="allTasks">All tasks</h1><p class="subheading" data-i18n="tasksIntro">Create and manage work across your Skills and projects.</p></div>
            <button class="primary-button" data-action="new-task">＋ <span data-i18n="newTask">New task</span></button>
          </div>
          <div class="filter-bar task-filters">
            <label class="search-box"><span>⌕</span><input id="task-search" type="search" data-i18n-placeholder="searchTasks" placeholder="Search tasks…"></label>
            <select id="task-status-filter" aria-label="Filter by status"></select>
            <select id="task-project-filter" aria-label="Filter by project"></select>
          </div>
          <div id="all-tasks-list" class="task-list"></div>
          <p class="empty-state hidden" id="tasks-empty" data-i18n="noTasks">No tasks match your filters.</p>
        </section>
      </div>

      <footer class="app-footer"><span>THE CONTROL · VERSION 1.0</span><span data-i18n="footerNote">Free forever · Your data stays in this browser</span></footer>
    </main>
  </div>

  <div class="modal-backdrop hidden" id="modal-backdrop" role="presentation">
    <section class="modal" id="modal" role="dialog" aria-modal="true" aria-labelledby="modal-title">
      <button class="modal-close icon-button" id="modal-close" aria-label="Close dialog">×</button>
      <div id="modal-content"></div>
    </section>
  </div>
  <div class="toast-region" id="toast-region" aria-live="polite"></div>
</body>
</html>@import url('https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&family=Space+Grotesk:wght@400;500;600;700&display=swap');

:root {
  color-scheme: dark;
  --bg: #090d18;
  --panel: #101625;
  --panel-2: #141c2d;
  --panel-hover: #192338;
  --line: #222c40;
  --text: #edf2ff;
  --muted: #8792a9;
  --accent: #77e7d0;
  --accent-2: #a78bfa;
  --blue: #70a5ff;
  --green: #6de0ad;
  --yellow: #f3c878;
  --red: #ff8290;
  --radius: 16px;
  font-family: "DM Sans", "Noto Sans Thai", system-ui, sans-serif;
}
* { box-sizing: border-box; }
body { margin: 0; min-width: 320px; background: var(--bg); color: var(--text); }
button, input, select, textarea { font: inherit; }
button { color: inherit; }
button:focus-visible, input:focus-visible, select:focus-visible, textarea:focus-visible {
  outline: 2px solid var(--accent); outline-offset: 2px;
}
.app-shell { min-height: 100vh; }
.sidebar {
  position: fixed; inset: 0 auto 0 0; z-index: 20; width: 252px; display: flex; flex-direction: column;
  padding: 27px 16px 18px; background: #0c111f; border-right: 1px solid #1b2537;
}
.brand { display: flex; align-items: center; gap: 12px; color: var(--text); text-decoration: none; padding: 0 7px 34px; }
.brand-mark {
  display: grid; place-items: center; width: 40px; height: 40px; border-radius: 12px;
  background: linear-gradient(135deg, #6de0cb, #9284f6); color: #0d1421; font: 700 17px "Space Grotesk", sans-serif;
}
.brand-mark span { color: #fff; }
.brand-copy { display: grid; gap: 3px; font: 700 13px "Space Grotesk", sans-serif; letter-spacing: .07em; }
.brand-copy small { color: #7d89a2; font-size: 9px; letter-spacing: .15em; }
.sidebar-label, .eyebrow { color: #78859e; font-size: 10px; font-weight: 700; letter-spacing: .15em; }
.sidebar-label { padding: 0 11px 12px; }
.main-nav { display: grid; gap: 5px; }
.nav-link {
  display: flex; align-items: center; gap: 12px; width: 100%; padding: 11px 12px; border: 0; border-radius: 10px;
  background: transparent; color: #a4aec2; text-align: left; cursor: pointer; transition: .18s ease;
}
.nav-link > span:first-child { width: 18px; text-align: center; color: #8492ac; font-size: 16px; }
.nav-link:hover, .nav-link.active { background: #192337; color: #f2f5ff; }
.nav-link.active { box-shadow: inset 2px 0 var(--accent); }
.nav-link.active > span:first-child { color: var(--accent); }
.nav-count { margin-left: auto; padding: 2px 7px; border-radius: 20px; background: #222d42; color: #aeb9ce; font-size: 10px; }
.nav-section-label { margin-top: 30px; }
.sidebar-bottom { margin-top: auto; }
.plan-card { padding: 15px; border: 1px solid #26334b; border-radius: 13px; background: linear-gradient(145deg, #151e30, #101625); }
.plan-icon { display: block; margin-bottom: 8px; color: var(--accent); }
.plan-card strong { font-size: 13px; }
.plan-card p { margin: 7px 0 12px; color: var(--muted); font-size: 11px; line-height: 1.6; }
.text-button, .subtle-button { padding: 0; border: 0; background: transparent; color: var(--accent); cursor: pointer; font-size: 11px; font-weight: 600; }
.sidebar-foot { margin: 20px 10px 0; color: #6d7890; font-size: 9px; letter-spacing: .08em; }
.sidebar-foot span { color: var(--accent); }
.main-content { min-height: 100vh; margin-left: 252px; display: flex; flex-direction: column; }
.topbar {
  position: sticky; top: 0; z-index: 10; height: 68px; display: flex; align-items: center; justify-content: space-between;
  padding: 0 34px; border-bottom: 1px solid #1b2537; background: rgb(9 13 24 / 90%); backdrop-filter: blur(15px);
}
.breadcrumb { display: flex; gap: 10px; align-items: center; color: #78859e; font-size: 10px; letter-spacing: .08em; }
.breadcrumb strong { color: #e6ebf7; font-size: 12px; letter-spacing: 0; }
.crumb-separator { color: #46516a; }
.top-actions { display: flex; align-items: center; gap: 14px; }
.package-pill { border: 1px solid #34415a; border-radius: 20px; padding: 6px 10px; color: var(--accent); font-size: 9px; font-weight: 700; letter-spacing: .09em; }
.language-switch, .icon-button, .avatar-button {
  border: 1px solid var(--line); background: #111827; cursor: pointer;
}
.language-switch { padding: 7px 10px; border-radius: 8px; color: #c4cce0; font-size: 10px; }
.language-switch span { color: var(--accent); padding: 0 4px; }
.avatar-button { width: 31px; height: 31px; border-radius: 50%; background: #272342; color: #c4b8ff; font-weight: 700; }
.mobile-menu { display: none; }
.page-content { width: 100%; max-width: 1500px; margin: 0 auto; padding: 34px; flex: 1; }
.view { display: none; animation: enter .24s ease; }
.view.active { display: block; }
@keyframes enter { from { opacity: 0; transform: translateY(5px); } to { opacity: 1; transform: translateY(0); } }
.welcome-row, .page-heading { display: flex; align-items: center; justify-content: space-between; gap: 20px; margin-bottom: 25px; }
.eyebrow { margin: 0 0 8px; }
h1, h2, h3, p { margin-top: 0; }
h1 { margin-bottom: 8px; font: 600 clamp(24px, 3vw, 32px) "Space Grotesk", sans-serif; letter-spacing: -.04em; }
h2 { margin: 0; font: 600 18px "Space Grotesk", sans-serif; letter-spacing: -.02em; }
h3 { font: 600 14px "Space Grotesk", sans-serif; }
.gradient-text { background: linear-gradient(90deg, var(--accent), #9ab5ff 75%, #c89cff); background-clip: text; -webkit-text-fill-color: transparent; }
.subheading { margin: 0; color: var(--muted); font-size: 13px; line-height: 1.6; }
.primary-button, .secondary-button, .danger-button {
  min-height: 38px; display: inline-flex; align-items: center; justify-content: center; gap: 8px; padding: 0 14px;
  border: 1px solid transparent; border-radius: 9px; cursor: pointer; font-size: 12px; font-weight: 700; transition: .18s ease;
}
.primary-button { background: var(--accent); color: #0b1920; }
.primary-button:hover { background: #a1f4e3; transform: translateY(-1px); }
.secondary-button { border-color: #303d55; background: #182237; color: #d7dff0; }
.secondary-button:hover { background: #202c43; }
.danger-button { border-color: #58313e; background: #2a1824; color: #ff9aa7; }
.stats-grid { display: grid; grid-template-columns: repeat(4, minmax(0, 1fr)); gap: 14px; margin-bottom: 22px; }
.stat-card, .panel, .skill-card, .project-card {
  border: 1px solid var(--line); border-radius: var(--radius); background: var(--panel);
}
.stat-card { min-height: 112px; padding: 17px; }
.stat-top { display: flex; align-items: center; justify-content: space-between; color: var(--muted); font-size: 11px; }
.stat-icon { display: grid; place-items: center; width: 30px; height: 30px; border-radius: 9px; background: #1b2b35; color: var(--accent); font-size: 15px; }
.stat-value { margin: 10px 0 0; font: 600 24px "Space Grotesk", sans-serif; }
.stat-note { margin: 3px 0 0; color: #74819a; font-size: 10px; }
.dashboard-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin-bottom: 18px; }
.panel { padding: 20px; }
.panel-heading { display: flex; align-items: center; justify-content: space-between; gap: 12px; margin-bottom: 18px; }
.panel-heading .eyebrow { margin-bottom: 6px; }
.project-list, .task-list { display: grid; gap: 10px; }
.project-row { padding: 12px; border: 1px solid #202b3e; border-radius: 11px; background: #121b2b; cursor: pointer; }
.project-row:hover, .task-row:hover { border-color: #3a4b67; }
.project-row-top, .task-row-top { display: flex; align-items: center; justify-content: space-between; gap: 12px; }
.project-row strong, .task-title { font-size: 12px; font-weight: 600; }
.project-row p { margin: 6px 0 10px; color: var(--muted); font-size: 10px; }
.progress-track { height: 5px; overflow: hidden; border-radius: 10px; background: #29334a; }
.progress-fill { height: 100%; border-radius: inherit; background: linear-gradient(90deg, var(--accent), #9e9aff); transition: width .3s ease; }
.progress-meta { display: flex; justify-content: space-between; margin-top: 6px; color: #8d99af; font-size: 9px; }
.task-row { padding: 12px; border: 1px solid #202b3e; border-radius: 11px; background: #121b2b; }
.task-row-top { align-items: flex-start; }
.task-title { display: block; margin-bottom: 5px; }
.task-meta { color: #8792a9; font-size: 10px; }
.task-actions { display: flex; gap: 6px; }
.tiny-button { border: 0; background: transparent; color: #9aa8c0; cursor: pointer; font-size: 11px; }
.tiny-button:hover { color: var(--accent); }
.status-badge, .category-badge { display: inline-flex; align-items: center; width: fit-content; padding: 4px 8px; border: 1px solid transparent; border-radius: 20px; font-size: 9px; font-weight: 600; white-space: nowrap; }
.status-available { border-color: #38435a; background: #1d2739; color: #aab7ce; }
.status-working { border-color: #284867; background: #14283b; color: #82c5ff; }
.status-review { border-color: #54462b; background: #302719; color: #f4cb7c; }
.status-completed { border-color: #28523f; background: #152b23; color: #7fe1ae; }
.category-badge { border-color: #35304e; background: #211e34; color: #c4aaff; }
.skill-grid { display: grid; grid-template-columns: repeat(3, minmax(0, 1fr)); gap: 12px; }
.team-preview .skill-grid { grid-template-columns: repeat(4, minmax(0, 1fr)); }
.skill-card { min-width: 0; padding: 15px; cursor: pointer; transition: .18s ease; }
.skill-card:hover { transform: translateY(-2px); border-color: #465777; background: var(--panel-hover); }
.skill-card-top { display: flex; justify-content: space-between; align-items: flex-start; gap: 8px; }
.skill-number { color: var(--accent); font: 600 10px "Space Grotesk", sans-serif; letter-spacing: .12em; }
.skill-card h3 { margin: 10px 0 4px; font-size: 13px; }
.skill-thai { min-height: 18px; margin-bottom: 8px; color: #b6c1d5; font-size: 11px; }
.skill-description { min-height: 34px; margin-bottom: 12px; color: var(--muted); font-size: 10px; line-height: 1.55; }
.skill-card-bottom { display: flex; justify-content: space-between; align-items: center; gap: 6px; }
.page-heading { margin-bottom: 24px; }
.filter-bar { display: flex; gap: 9px; margin-bottom: 17px; }
.search-box { min-width: 210px; flex: 1; display: flex; align-items: center; gap: 9px; padding: 0 12px; border: 1px solid var(--line); border-radius: 9px; background: #111827; color: #8290a9; }
.search-box input { width: 100%; padding: 10px 0; border: 0; outline: 0; background: transparent; color: var(--text); font-size: 11px; }
.filter-bar select, .form-control, .inline-status {
  min-height: 37px; padding: 0 10px; border: 1px solid var(--line); border-radius: 9px; background: #111827; color: #d6deef; font-size: 11px;
}
.filter-bar select { min-width: 135px; }
.project-grid { display: grid; grid-template-columns: repeat(2, minmax(0, 1fr)); gap: 15px; }
.project-card { padding: 20px; }
.project-card h3 { margin: 10px 0 7px; font-size: 16px; }
.project-card > p { min-height: 34px; color: var(--muted); font-size: 11px; line-height: 1.6; }
.project-card .progress-track { margin-top: 16px; }
.project-card-footer { display: flex; justify-content: space-between; align-items: center; gap: 8px; margin-top: 14px; }
.project-buttons { display: flex; gap: 7px; }
.empty-state { padding: 30px 12px; color: var(--muted); text-align: center; font-size: 12px; }
.hidden { display: none !important; }
.locked-banner { display: flex; align-items: center; gap: 14px; padding: 17px; border: 1px solid #3b365e; border-radius: 13px; background: #18172a; }
.locked-icon { font-size: 23px; }
.locked-banner div { flex: 1; }
.locked-banner strong { font-size: 12px; }
.locked-banner p { margin: 5px 0 0; color: var(--muted); font-size: 10px; line-height: 1.5; }
.app-footer { display: flex; justify-content: space-between; gap: 10px; padding: 15px 34px 22px; color: #6d7890; font-size: 9px; letter-spacing: .05em; }
.modal-backdrop { position: fixed; inset: 0; z-index: 50; display: grid; place-items: center; padding: 18px; background: rgb(3 6 13 / 75%); backdrop-filter: blur(6px); }
.modal { position: relative; width: min(590px, 100%); max-height: min(88vh, 850px); overflow: auto; padding: 25px; border: 1px solid #34415b; border-radius: 17px; background: #111827; box-shadow: 0 25px 90px #0009; animation: enter .18s ease; }
.modal-close { position: absolute; top: 14px; right: 14px; width: 30px; height: 30px; border-radius: 8px; color: #abb6ca; font-size: 20px; }
.modal h2 { margin: 0 35px 7px 0; font-size: 21px; }
.modal-subtitle { margin-bottom: 20px; color: var(--muted); font-size: 11px; line-height: 1.6; }
.modal-section { padding-top: 16px; margin-top: 15px; border-top: 1px solid var(--line); }
.modal-section h3 { margin: 0 0 9px; color: #b7c2d7; font-size: 10px; letter-spacing: .12em; text-transform: uppercase; }
.detail-list { margin: 0; padding-left: 18px; color: #c1cbdd; font-size: 11px; line-height: 1.8; }
.capability-chips { display: flex; flex-wrap: wrap; gap: 6px; }
.capability-chip { padding: 6px 9px; border: 1px solid #303d55; border-radius: 20px; color: #bcc7dc; font-size: 10px; }
.form-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 13px; }
.form-field { display: grid; gap: 6px; margin-bottom: 13px; }
.form-field.full { grid-column: 1 / -1; }
.form-field label { color: #aeb9ce; font-size: 10px; font-weight: 600; }
.form-control { width: 100%; min-height: 39px; }
textarea.form-control { min-height: 85px; padding: 10px; resize: vertical; }
.form-actions { display: flex; justify-content: flex-end; gap: 8px; margin-top: 17px; }
.package-options { display: grid; gap: 10px; }
.package-option { display: flex; align-items: flex-start; gap: 12px; padding: 14px; border: 1px solid #303d55; border-radius: 11px; background: #141d2e; cursor: pointer; }
.package-option.selected { border-color: var(--accent); }
.package-option input { margin-top: 3px; accent-color: var(--accent); }
.package-option strong { display: block; margin-bottom: 5px; font-size: 12px; }
.package-option small { display: block; color: var(--muted); font-size: 10px; line-height: 1.6; }
.warning-note { padding: 11px; border: 1px solid #56452c; border-radius: 9px; background: #2a2419; color: #e6c785; font-size: 10px; line-height: 1.6; }
.detail-status-row { display: flex; align-items: center; justify-content: space-between; gap: 12px; }
.detail-status-row label { color: var(--muted); font-size: 11px; }
.toast-region { position: fixed; right: 18px; bottom: 18px; z-index: 80; display: grid; gap: 8px; }
.toast { max-width: 340px; padding: 12px 15px; border: 1px solid #3a4a61; border-radius: 10px; background: #172235; box-shadow: 0 10px 35px #0006; color: #e8eefb; font-size: 11px; animation: enter .18s ease; }
.toast.error { border-color: #70404b; }
.inline-status { min-height: 28px; padding: 0 7px; font-size: 9px; }

@media (min-width: 1450px) {
  .skill-grid { grid-template-columns: repeat(4, minmax(0, 1fr)); }
}
@media (max-width: 1100px) {
  .sidebar { width: 220px; }
  .main-content { margin-left: 220px; }
  .page-content { padding: 27px; }
  .team-preview .skill-grid { grid-template-columns: repeat(3, minmax(0, 1fr)); }
  .skill-grid { grid-template-columns: repeat(2, minmax(0, 1fr)); }
}
@media (max-width: 760px) {
  .sidebar { width: 260px; transform: translateX(-100%); transition: transform .22s ease; box-shadow: 15px 0 40px #0006; }
  .sidebar.open { transform: translateX(0); }
  .main-content { margin-left: 0; }
  .topbar { height: 60px; padding: 0 16px; }
  .mobile-menu { display: inline-grid; place-items: center; width: 32px; height: 32px; border-radius: 8px; }
  .breadcrumb { margin-right: auto; margin-left: 10px; font-size: 9px; }
  .top-actions { gap: 8px; }
  .package-pill { display: none; }
  .page-content { padding: 24px 16px; }
  .stats-grid { grid-template-columns: repeat(2, minmax(0, 1fr)); gap: 9px; }
  .stat-card { min-height: 100px; padding: 13px; }
  .dashboard-grid { grid-template-columns: 1fr; }
  .team-preview .skill-grid { grid-template-columns: repeat(2, minmax(0, 1fr)); }
  .skill-grid { grid-template-columns: repeat(2, minmax(0, 1fr)); }
  .project-grid { grid-template-columns: 1fr; }
  .app-footer { padding: 14px 16px 20px; font-size: 8px; }
}
@media (max-width: 480px) {
  .welcome-row, .page-heading { align-items: flex-start; flex-direction: column; }
  .welcome-row .primary-button, .page-heading .primary-button { align-self: flex-start; }
  .filter-bar { flex-wrap: wrap; }
  .search-box { flex-basis: 100%; }
  .filter-bar select { flex: 1; min-width: 0; }
  .skill-grid, .team-preview .skill-grid { grid-template-columns: 1fr; }
  .skill-description { min-height: auto; }
  .form-grid { grid-template-columns: 1fr; gap: 0; }
  .form-field.full { grid-column: auto; }
  .locked-banner { align-items: flex-start; flex-wrap: wrap; }
  .locked-banner .primary-button { margin-left: 36px; }
  .app-footer { flex-direction: column; }
}"use strict";

const STORAGE_KEY = "the-control-v1";
const STATUS_KEYS = ["available", "working", "review", "completed"];
const CATEGORIES = ["Leadership", "Production", "Design", "Engineering", "Art", "Audio", "Quality", "Operations"];

// Each row: number, English name, Thai name, category, role focus (EN/TH),
// personality (EN/TH), capabilities (EN/TH).
const RAW_SKILLS = [
  [1,"Game Director","ผู้อำนวยการเกม","Leadership","Sets the creative vision and aligns the team around the intended player experience.","กำหนดวิสัยทัศน์เชิงสร้างสรรค์และประสานทีมให้มุ่งสู่ประสบการณ์ผู้เล่นที่ต้องการ","decisive, imaginative, and collaborative","เด็ดขาด มีจินตนาการ และทำงานร่วมกับผู้อื่นได้ดี","vision setting; creative reviews; team alignment","กำหนดวิสัยทัศน์; ตรวจงานสร้างสรรค์; ประสานทีม"],
  [2,"Producer","โปรดิวเซอร์","Production","Coordinates schedules, scope, risks, and communication so the team can deliver reliably.","ประสานตารางงาน ขอบเขต ความเสี่ยง และการสื่อสารเพื่อให้ทีมส่งมอบงานได้ตามแผน","organized, calm, and people-focused","เป็นระบบ ใจเย็น และใส่ใจผู้คน","roadmaps; sprint planning; risk tracking","วางแผนงาน; วางแผนสปรินต์; ติดตามความเสี่ยง"],
  [3,"Game Designer","นักออกแบบเกม","Design","Creates rules, mechanics, and player choices that make the game engaging and coherent.","ออกแบบกติกา กลไก และทางเลือกของผู้เล่นให้เกมสนุกและมีเอกภาพ","curious, analytical, and playful","ช่างสงสัย ช่างวิเคราะห์ และสนุกกับการทดลอง","mechanic design; prototyping; design documentation","ออกแบบกลไก; สร้างต้นแบบ; จัดทำเอกสารออกแบบ"],
  [4,"Creative Director","ผู้อำนวยการฝ่ายสร้างสรรค์","Leadership","Defines the artistic and tonal direction across the game's visual, audio, and narrative work.","กำหนดทิศทางด้านศิลป์และอารมณ์ให้สอดคล้องกันทั้งภาพ เสียง และเนื้อเรื่อง","inspiring, discerning, and open-minded","สร้างแรงบันดาลใจ มีวิจารณญาณ และเปิดรับความคิด","creative direction; style guides; concept reviews","กำหนดทิศทางสร้างสรรค์; จัดทำคู่มือสไตล์; ตรวจแนวคิด"],
  [5,"Gameplay Programmer","โปรแกรมเมอร์เกมเพลย์","Engineering","Builds player controls, game mechanics, and moment-to-moment interactions.","พัฒนาการควบคุม กลไกเกม และปฏิสัมพันธ์ระหว่างการเล่น","practical, iterative, and detail-oriented","ลงมือทำจริง ปรับปรุงต่อเนื่อง และใส่ใจรายละเอียด","gameplay systems; input handling; prototyping","ระบบเกมเพลย์; จัดการอินพุต; สร้างต้นแบบ"],
  [6,"AI Programmer","โปรแกรมเมอร์ AI","Engineering","Implements believable non-player behavior, decision systems, and navigation.","พัฒนาพฤติกรรมตัวละครที่ควบคุมด้วยคอมพิวเตอร์ ระบบตัดสินใจ และการนำทาง","logical, experimental, and patient","มีเหตุผล ชอบทดลอง และอดทน","behavior trees; navigation; decision logic","behavior tree; ระบบนำทาง; ตรรกะการตัดสินใจ"],
  [7,"UI Programmer","โปรแกรมเมอร์ UI","Engineering","Develops responsive menus, HUDs, and interfaces that clearly communicate game state.","พัฒนาเมนู HUD และส่วนติดต่อที่ตอบสนองดีและสื่อสารสถานะเกมชัดเจน","empathetic, systematic, and precise","เข้าใจผู้ใช้ เป็นระบบ และแม่นยำ","UI architecture; input navigation; interface implementation","โครงสร้าง UI; การนำทางด้วยอินพุต; พัฒนาส่วนติดต่อ"],
  [8,"Network Programmer","โปรแกรมเมอร์เครือข่าย","Engineering","Builds the communication and synchronization systems needed for online play.","พัฒนาระบบสื่อสารและซิงโครไนซ์สำหรับการเล่นออนไลน์","methodical, resilient, and security-aware","เป็นขั้นตอน อดทน และคำนึงถึงความปลอดภัย","network protocols; synchronization; latency analysis","โปรโตคอลเครือข่าย; การซิงโครไนซ์; วิเคราะห์ความหน่วง"],
  [9,"Physics Programmer","โปรแกรมเมอร์ฟิสิกส์","Engineering","Implements collision, movement, and physical simulation that supports the game feel.","พัฒนาการชน การเคลื่อนที่ และการจำลองฟิสิกส์ให้เหมาะกับสัมผัสการเล่น","analytical, grounded, and persistent","ช่างวิเคราะห์ รอบคอบ และมุ่งมั่น","collision systems; simulation; movement tuning","ระบบชน; การจำลอง; ปรับแต่งการเคลื่อนที่"],
  [10,"Backend Developer","นักพัฒนาแบ็กเอนด์","Engineering","Creates game services for accounts, progression, inventories, and other online features.","สร้างบริการเกมสำหรับบัญชี ความก้าวหน้า ไอเทม และฟีเจอร์ออนไลน์","reliable, pragmatic, and security-minded","ไว้ใจได้ เน้นการใช้งานจริง และใส่ใจความปลอดภัย","service APIs; data flows; account systems","API บริการ; การไหลของข้อมูล; ระบบบัญชี"],
  [11,"Concept Artist","ศิลปินคอนเซปต์","Art","Explores visual ideas and communicates the look of characters, places, and objects.","ค้นหาแนวคิดด้านภาพและถ่ายทอดรูปลักษณ์ของตัวละคร ฉาก และวัตถุ","imaginative, observant, and expressive","มีจินตนาการ ช่างสังเกต และถ่ายทอดเก่ง","visual exploration; reference boards; concept sheets","สำรวจแนวคิดภาพ; รวบรวมภาพอ้างอิง; วาดคอนเซปต์"],
  [12,"2D Artist","ศิลปิน 2 มิติ","Art","Produces polished 2D assets, illustrations, sprites, and visual elements for the game.","สร้างภาพประกอบ สไปรต์ และองค์ประกอบ 2 มิติสำหรับเกม","versatile, expressive, and detail-aware","ปรับตัวเก่ง ถ่ายทอดได้ดี และใส่ใจรายละเอียด","illustration; sprite art; 2D asset production","ภาพประกอบ; งานสไปรต์; ผลิตแอสเซ็ต 2 มิติ"],
  [13,"3D Artist","ศิลปิน 3 มิติ","Art","Models and presents 3D assets that meet the game's visual and technical needs.","สร้างและนำเสนอโมเดล 3 มิติให้ตรงตามข้อกำหนดด้านภาพและเทคนิค","craft-focused, patient, and spatially minded","พิถีพิถัน อดทน และเข้าใจมิติพื้นที่","3D modeling; topology; asset presentation","โมเดล 3 มิติ; โทโพโลยี; นำเสนอแอสเซ็ต"],
  [14,"Animator","นักแอนิเมชัน","Art","Creates clear, expressive motion for characters, objects, and gameplay moments.","สร้างการเคลื่อนไหวที่ชัดเจนและสื่ออารมณ์ให้ตัวละคร วัตถุ และเกมเพลย์","observant, rhythmic, and expressive","ช่างสังเกต มีจังหวะ และถ่ายทอดอารมณ์ได้ดี","keyframe animation; timing; motion polish","แอนิเมชันคีย์เฟรม; จังหวะ; ขัดเกลาการเคลื่อนไหว"],
  [15,"VFX Artist","ศิลปินเอฟเฟกต์ภาพ","Art","Creates visual effects that reinforce feedback, atmosphere, and important game events.","สร้างเอฟเฟกต์ภาพที่เสริมการตอบสนอง บรรยากาศ และเหตุการณ์สำคัญในเกม","inventive, energetic, and timing-sensitive","สร้างสรรค์ กระตือรือร้น และเข้าใจจังหวะ","particle effects; shaders; visual feedback","เอฟเฟกต์อนุภาค; เชดเดอร์; ภาพตอบสนอง"],
  [16,"Level Designer","นักออกแบบเลเวล","Design","Shapes spaces, encounters, and routes to guide player challenge and discovery.","ออกแบบพื้นที่ การเผชิญหน้า และเส้นทางเพื่อกำหนดความท้าทายและการค้นพบ","player-focused, iterative, and spatial","คำนึงถึงผู้เล่น ชอบปรับปรุง และเข้าใจพื้นที่","blockouts; encounter design; player flow","บล็อกเอาต์; ออกแบบการเผชิญหน้า; เส้นทางผู้เล่น"],
  [17,"Sound Designer","นักออกแบบเสียง","Audio","Designs and integrates sound effects that make actions and environments feel alive.","ออกแบบและผสานเสียงเอฟเฟกต์ให้การกระทำและสภาพแวดล้อมมีชีวิต","attentive, inventive, and technically curious","ใส่ใจ ช่างคิด และสนใจด้านเทคนิค","sound effects; audio implementation; ambience","เสียงเอฟเฟกต์; ติดตั้งระบบเสียง; เสียงบรรยากาศ"],
  [18,"Music Composer","นักแต่งเพลง","Audio","Composes and adapts music that supports the game's emotion, pacing, and identity.","แต่งและปรับดนตรีเพื่อสนับสนุนอารมณ์ จังหวะ และเอกลักษณ์ของเกม","expressive, disciplined, and emotionally perceptive","ถ่ายทอดอารมณ์ มีวินัย และเข้าใจความรู้สึก","composition; adaptive scoring; musical themes","แต่งเพลง; ดนตรีปรับตามเกม; ธีมดนตรี"],
  [19,"Narrative Designer","นักออกแบบเนื้อเรื่อง","Design","Connects story, dialogue, and player choices with the structure of gameplay.","เชื่อมโยงเรื่องราว บทสนทนา และทางเลือกของผู้เล่นเข้ากับโครงสร้างเกม","empathetic, thoughtful, and clear","เข้าอกเข้าใจ รอบคอบ และสื่อสารชัดเจน","story structure; dialogue systems; narrative flow","โครงสร้างเรื่อง; ระบบบทสนทนา; ลำดับการเล่าเรื่อง"],
  [20,"Character Designer","นักออกแบบตัวละคร","Art","Develops memorable character identities through shape, costume, expression, and reference.","สร้างเอกลักษณ์ตัวละครผ่านรูปทรง เครื่องแต่งกาย สีหน้า และข้อมูลอ้างอิง","expressive, curious, and observant","ถ่ายทอดเก่ง ช่างสงสัย และช่างสังเกต","character concepts; turnarounds; visual identity","คอนเซปต์ตัวละคร; ภาพหลายมุม; อัตลักษณ์ภาพ"],
  [21,"QA Tester","นักทดสอบ QA","Quality","Finds, documents, and helps reproduce defects so the team can improve quality.","ค้นหา บันทึก และช่วยจำลองข้อบกพร่องเพื่อให้ทีมปรับปรุงคุณภาพ","curious, thorough, and constructive","ช่างสงสัย รอบคอบ และให้คำแนะนำอย่างสร้างสรรค์","test cases; bug reports; regression checks","กรณีทดสอบ; รายงานบั๊ก; ตรวจสอบการถดถอย"],
  [22,"Game Balancer","นักปรับสมดุลเกม","Design","Tunes rules, rewards, and difficulty to create a fair and satisfying experience.","ปรับกติกา รางวัล และความยากให้เกิดประสบการณ์ที่ยุติธรรมและน่าพึงพอใจ","data-aware, fair-minded, and analytical","ใช้ข้อมูล มีความยุติธรรม และช่างวิเคราะห์","balance tuning; economy review; playtest analysis","ปรับสมดุล; ตรวจเศรษฐกิจเกม; วิเคราะห์การทดสอบเล่น"],
  [23,"Performance Engineer","วิศวกรประสิทธิภาพ","Engineering","Measures and improves frame rate, memory use, load time, and runtime stability.","วัดและปรับปรุงเฟรมเรต การใช้หน่วยความจำ เวลาโหลด และความเสถียร","precise, investigative, and optimization-driven","แม่นยำ ช่างสืบค้น และมุ่งเน้นการเพิ่มประสิทธิภาพ","profiling; bottleneck analysis; optimization","วิเคราะห์โปรไฟล์; หาคอขวด; เพิ่มประสิทธิภาพ"],
  [24,"Security Engineer","วิศวกรความปลอดภัย","Engineering","Reviews game systems for security risks and recommends defensive safeguards.","ตรวจสอบความเสี่ยงด้านความปลอดภัยและเสนอแนวทางป้องกันระบบเกม","cautious, ethical, and detail-focused","รอบคอบ มีจริยธรรม และใส่ใจรายละเอียด","threat modeling; secure design review; risk assessment","วิเคราะห์ภัยคุกคาม; ตรวจการออกแบบอย่างปลอดภัย; ประเมินความเสี่ยง"],
  [25,"Technical Director","ผู้อำนวยการฝ่ายเทคนิค","Leadership","Sets technical direction, architecture standards, and engineering priorities across the project.","กำหนดทิศทางเทคนิค มาตรฐานสถาปัตยกรรม และลำดับความสำคัญด้านวิศวกรรม","strategic, clear-minded, and supportive","มองเชิงกลยุทธ์ ชัดเจน และสนับสนุนทีม","technical roadmaps; architecture reviews; engineering leadership","แผนเทคนิค; ตรวจสถาปัตยกรรม; นำทีมวิศวกรรม"],
  [26,"World Builder","นักสร้างโลก","Design","Assembles immersive worlds by combining terrain, landmarks, routes, and environmental storytelling.","ประกอบโลกที่ชวนดื่มด่ำด้วยภูมิประเทศ จุดเด่น เส้นทาง และการเล่าเรื่องผ่านฉาก","imaginative, patient, and spatially aware","มีจินตนาการ อดทน และเข้าใจมิติพื้นที่","world layout; terrain composition; environmental storytelling","จัดวางโลก; องค์ประกอบภูมิประเทศ; เล่าเรื่องผ่านสภาพแวดล้อม"],
  [27,"Procedural Generation Engineer","วิศวกรสร้างเนื้อหาอัตโนมัติ","Engineering","Builds rule-driven tools that generate varied, controllable game content.","สร้างเครื่องมือที่ใช้กฎเพื่อสร้างเนื้อหาเกมที่หลากหลายและควบคุมได้","mathematical, experimental, and systems-minded","ถนัดคณิตศาสตร์ ชอบทดลอง และคิดเป็นระบบ","generation algorithms; rule systems; content validation","อัลกอริทึมสร้างเนื้อหา; ระบบกฎ; ตรวจสอบเนื้อหา"],
  [28,"Cinematic Director","ผู้กำกับคัตซีน","Design","Directs in-game cinematics, staging, camera language, and narrative transitions.","กำกับคัตซีน การจัดฉาก ภาษากล้อง และช่วงเชื่อมต่อของเรื่องราว","visual, deliberate, and story-driven","เข้าใจภาพ รอบคอบ และขับเคลื่อนด้วยเรื่องราว","storyboards; camera blocking; cinematic pacing","สตอรีบอร์ด; จัดวางกล้อง; จังหวะคัตซีน"],
  [29,"Advanced Animation Engineer","วิศวกรแอนิเมชันขั้นสูง","Engineering","Builds animation systems that blend, adapt, and respond to gameplay conditions.","พัฒนาระบบแอนิเมชันที่ผสม ปรับ และตอบสนองตามสถานการณ์เกมเพลย์","technical, creative, and motion-sensitive","เชี่ยวชาญเทคนิค สร้างสรรค์ และเข้าใจการเคลื่อนไหว","animation graphs; motion blending; runtime systems","กราฟแอนิเมชัน; ผสมการเคลื่อนไหว; ระบบขณะทำงาน"],
  [30,"Lighting Artist","ศิลปินแสง","Art","Shapes mood, readability, and visual focus through real-time and baked lighting.","สร้างอารมณ์ ความชัดเจน และจุดสนใจด้วยแสงแบบเรียลไทม์และแสงอบ","atmospheric, patient, and visually precise","สร้างบรรยากาศ อดทน และแม่นยำด้านภาพ","lighting composition; mood studies; readability checks","จัดองค์ประกอบแสง; ทดลองอารมณ์; ตรวจความชัดเจน"],
  [31,"Material Artist","ศิลปินวัสดุ","Art","Creates reusable materials and surface definitions that bring assets to life.","สร้างวัสดุและพื้นผิวที่นำกลับมาใช้ได้เพื่อเพิ่มชีวิตชีวาให้แอสเซ็ต","craft-oriented, systematic, and observant","พิถีพิถัน เป็นระบบ และช่างสังเกต","material authoring; shader setup; surface definition","สร้างวัสดุ; ตั้งค่าเชดเดอร์; กำหนดพื้นผิว"],
  [32,"Environment Artist","ศิลปินสภาพแวดล้อม","Art","Creates environment assets and visual compositions that establish place and atmosphere.","สร้างแอสเซ็ตและองค์ประกอบภาพที่กำหนดสถานที่และบรรยากาศ","inventive, observant, and composition-minded","สร้างสรรค์ ช่างสังเกต และเข้าใจองค์ประกอบภาพ","environment assets; set dressing; visual composition","แอสเซ็ตฉาก; จัดวางองค์ประกอบ; องค์ประกอบภาพ"],
  [33,"Character Technical Artist","เทคนิคอลอาร์ทิสต์ตัวละคร","Engineering","Bridges character art and runtime systems through rigs, deformation, and asset workflows.","เชื่อมงานศิลป์ตัวละครกับระบบเกมผ่านริก การบิดรูป และเวิร์กโฟลว์แอสเซ็ต","adaptable, collaborative, and technically artistic","ปรับตัวเก่ง ทำงานร่วมกับผู้อื่น และมีทั้งทักษะศิลป์กับเทคนิค","character rigs; deformation; asset pipelines","ริกตัวละคร; การบิดรูป; ไปป์ไลน์แอสเซ็ต"],
  [34,"Motion Capture Specialist","ผู้เชี่ยวชาญโมชั่นแคปเจอร์","Art","Plans, captures, and cleans recorded movement for believable character performance.","วางแผน บันทึก และปรับข้อมูลการเคลื่อนไหวเพื่อการแสดงตัวละครที่น่าเชื่อถือ","observant, organized, and performance-aware","ช่างสังเกต เป็นระบบ และเข้าใจการแสดง","capture sessions; data cleanup; motion retargeting","จัดเซสชันบันทึก; ทำความสะอาดข้อมูล; ย้ายการเคลื่อนไหว"],
  [35,"Multiplayer Architect","สถาปนิกระบบมัลติเพลเยอร์","Engineering","Designs scalable multiplayer architecture, session flow, and authoritative game systems.","ออกแบบสถาปัตยกรรมมัลติเพลเยอร์ที่ขยายได้ ระบบเซสชัน และระบบเกมที่มีแหล่งควบคุมชัดเจน","forward-thinking, precise, and reliability-focused","มองการณ์ไกล แม่นยำ และให้ความสำคัญกับความเชื่อถือได้","multiplayer architecture; session design; system scaling","สถาปัตยกรรมมัลติเพลเยอร์; ออกแบบเซสชัน; ขยายระบบ"],
  [36,"Database Architect","สถาปนิกฐานข้อมูล","Engineering","Designs data models and storage patterns for reliable game information and progression.","ออกแบบโมเดลข้อมูลและรูปแบบจัดเก็บสำหรับข้อมูลเกมและความก้าวหน้าที่เชื่อถือได้","structured, analytical, and consistency-minded","เป็นระบบ ช่างวิเคราะห์ และใส่ใจความสอดคล้อง","data modeling; schema design; storage planning","โมเดลข้อมูล; ออกแบบสคีมา; วางแผนการจัดเก็บ"],
  [37,"Cloud Engineer","วิศวกรคลาวด์","Engineering","Plans cloud infrastructure and services that support dependable game operations.","วางแผนโครงสร้างพื้นฐานและบริการคลาวด์เพื่อรองรับการให้บริการเกมที่น่าเชื่อถือ","practical, vigilant, and scalable-minded","เน้นการใช้งานจริง รอบคอบ และคิดเผื่อการขยาย","cloud infrastructure; service reliability; capacity planning","โครงสร้างพื้นฐานคลาวด์; ความน่าเชื่อถือบริการ; วางแผนความจุ"],
  [38,"DevOps Engineer","วิศวกร DevOps","Engineering","Improves build, test, and deployment workflows through automation and reliable tooling.","ปรับปรุงเวิร์กโฟลว์บิลด์ ทดสอบ และเผยแพร่ด้วยระบบอัตโนมัติและเครื่องมือที่เชื่อถือได้","automative, collaborative, and process-minded","ชอบระบบอัตโนมัติ ทำงานร่วมกัน และคิดเป็นกระบวนการ","CI workflows; deployment automation; observability","เวิร์กโฟลว์ CI; อัตโนมัติการเผยแพร่; การสังเกตระบบ"],
  [39,"Localization Specialist","ผู้เชี่ยวชาญการแปลเกม","Operations","Adapts text and cultural context so the game feels natural across languages and regions.","ปรับข้อความและบริบททางวัฒนธรรมให้เกมเป็นธรรมชาติในแต่ละภาษาและภูมิภาค","culturally curious, precise, and empathetic","สนใจวัฒนธรรม แม่นยำ และเข้าใจผู้อื่น","string management; linguistic QA; cultural adaptation","จัดการข้อความ; ตรวจคุณภาพภาษา; ปรับตามวัฒนธรรม"],
  [40,"Accessibility Designer","นักออกแบบการเข้าถึง","Design","Makes game interactions more inclusive through accessible options and thoughtful design.","ทำให้การเล่นเข้าถึงได้มากขึ้นด้วยตัวเลือกและการออกแบบที่คำนึงถึงผู้เล่นทุกกลุ่ม","empathetic, proactive, and user-centered","เข้าอกเข้าใจ คิดล่วงหน้า และยึดผู้ใช้เป็นศูนย์กลาง","accessibility reviews; inclusive options; usability guidance","ตรวจการเข้าถึง; ตัวเลือกที่ครอบคลุม; แนะแนวการใช้งาน"],
  [41,"UX Researcher","นักวิจัย UX","Design","Studies player needs and behaviors to guide evidence-based experience improvements.","ศึกษาความต้องการและพฤติกรรมผู้เล่นเพื่อแนะนำการปรับปรุงประสบการณ์ที่มีหลักฐานรองรับ","curious, unbiased, and attentive","ช่างสงสัย ไม่ลำเอียง และใส่ใจ","player interviews; usability studies; insight synthesis","สัมภาษณ์ผู้เล่น; ศึกษาการใช้งาน; สังเคราะห์ข้อมูลเชิงลึก"],
  [42,"Economy Designer","นักออกแบบเศรษฐกิจเกม","Design","Shapes currencies, rewards, and resource flows to support engaging progression.","ออกแบบสกุลเงิน รางวัล และการไหลของทรัพยากรเพื่อสนับสนุนความก้าวหน้าที่น่าสนใจ","analytical, balanced, and player-aware","ช่างวิเคราะห์ รักษาสมดุล และคำนึงถึงผู้เล่น","economy models; reward tuning; progression analysis","โมเดลเศรษฐกิจ; ปรับรางวัล; วิเคราะห์ความก้าวหน้า"],
  [43,"Quest Designer","นักออกแบบเควสต์","Design","Creates objectives, steps, and rewards that guide players through meaningful adventures.","สร้างเป้าหมาย ขั้นตอน และรางวัลที่นำผู้เล่นผ่านการผจญภัยที่มีความหมาย","story-minded, organized, and inventive","เข้าใจการเล่าเรื่อง เป็นระบบ และสร้างสรรค์","quest flow; objective writing; reward placement","ลำดับเควสต์; เขียนเป้าหมาย; วางรางวัล"],
  [44,"Gameplay Analyst","นักวิเคราะห์เกมเพลย์","Quality","Turns gameplay data and observations into insights that inform design decisions.","เปลี่ยนข้อมูลและข้อสังเกตจากเกมเพลย์ให้เป็นข้อมูลเชิงลึกสำหรับการตัดสินใจออกแบบ","evidence-led, curious, and clear","ใช้หลักฐาน ช่างสงสัย และสื่อสารชัดเจน","metric design; data analysis; insight reporting","ออกแบบตัวชี้วัด; วิเคราะห์ข้อมูล; รายงานข้อค้นพบ"],
  [45,"Automation Tester","นักทดสอบระบบอัตโนมัติ","Quality","Builds repeatable automated checks that catch regressions and protect key flows.","สร้างการตรวจสอบอัตโนมัติที่ทำซ้ำได้เพื่อจับปัญหาการถดถอยและปกป้องขั้นตอนสำคัญ","systematic, persistent, and quality-focused","เป็นระบบ มุ่งมั่น และให้ความสำคัญกับคุณภาพ","test automation; regression suites; test reporting","ระบบทดสอบอัตโนมัติ; ชุดทดสอบถดถอย; รายงานการทดสอบ"],
  [46,"Compatibility Engineer","วิศวกรความเข้ากันได้","Engineering","Checks game behavior across supported devices, operating systems, and configurations.","ตรวจสอบการทำงานของเกมบนอุปกรณ์ ระบบปฏิบัติการ และการตั้งค่าที่รองรับ","thorough, adaptable, and methodical","รอบคอบ ปรับตัวเก่ง และทำงานเป็นขั้นตอน","device matrix testing; platform checks; issue triage","ทดสอบเมทริกซ์อุปกรณ์; ตรวจแพลตฟอร์ม; จัดลำดับปัญหา"],
  [47,"Build & Release Manager","ผู้จัดการบิลด์และเผยแพร่","Operations","Coordinates stable builds, release readiness, versioning, and delivery communication.","ประสานบิลด์ที่เสถียร ความพร้อมเผยแพร่ การจัดเวอร์ชัน และการสื่อสารส่งมอบ","dependable, detail-focused, and composed","ไว้ใจได้ ใส่ใจรายละเอียด และสุขุม","release checklists; version coordination; delivery planning","รายการตรวจเผยแพร่; ประสานเวอร์ชัน; วางแผนส่งมอบ"],
  [48,"Technical Support Specialist","ผู้เชี่ยวชาญฝ่ายสนับสนุนเทคนิค","Operations","Helps players and teammates resolve technical issues with clear, helpful guidance.","ช่วยผู้เล่นและทีมแก้ปัญหาทางเทคนิคด้วยคำแนะนำที่ชัดเจนและเป็นประโยชน์","patient, empathetic, and resourceful","อดทน เข้าใจผู้อื่น และรู้จักแก้ปัญหา","issue triage; troubleshooting; support documentation","จัดลำดับปัญหา; แก้ไขปัญหา; เอกสารสนับสนุน"]
];

const I18N = {
  en: {
    workspace:"WORKSPACE", dashboard:"Dashboard", teamA:"Team A · Guest", teamB:"Team B · Member",
    projects:"Projects", management:"MANAGEMENT", allTasks:"All tasks", freeForever:"Free forever",
    freeNote:"No paid packages. Choose Guest or local Member demo.", managePackage:"Choose package →",
    overview:"TEAM OVERVI# THE CONTROL — Version 1.0

A free, bilingual game development team management dashboard built with HTML, CSS, and vanilla JavaScript. Designed for GitHub Pages and responsive layouts from mobile to desktop.

## Features

- 48 distinct game development Skill profiles with English and Thai names, role descriptions, responsibilities, personality, capabilities, status, and assigned tasks.
- Free Guest mode: no registration; access to Skills 01–24.
- Free Member demo mode: access to Skills 01–48.
- Search, category filters, and status filters for Skills.
- Create, edit, assign, filter, update, and delete tasks.
- Create, edit, view, and delete projects; project progress is calculated from completed tasks.
- English/Thai interface switch.
- Browser `localStorage` persistence for language, package demo settings, Skill status, tasks, and projects.
- Responsive dark dashboard layout.

## Important: local Member demo is not secure authentication

Version 1.0 does not provide an online account system. The Member option is a local demonstration setting, stored in the browser's `localStorage`. It does not verify a user's identity, protect data, synchronize data across devices, or securely restrict access. Do not store sensitive information in this demo.

## Run locally

Keep `index.html`, `style.css`, and `script.js` in the same directory, then open `index.html` in a modern browser. No build step or paid service is required. Google Fonts are an optional external font enhancement; system font fallbacks are included.

## Publish with GitHub Pages

1. Add the four project files to the repository's root directory.
2. In the repository, open **Settings → Pages**.
3. Choose **Deploy from a branch**, select the branch and `/ (root)` folder, then save.
4. Open the published Pages URL after deployment completes.

The app is static and does not require a server, API key, or package installation.

## Data and privacy

App data is saved only in the current browser's `localStorage`. It remains after refresh in that browser, but is not shared across browsers or devices. Clearing browser site data removes it. Avoid using a shared device for private project information.

## Verification notes

This delivery has not been run through browser automation or tested on physical Android, tablet, or desktop devices. Before relying on it, manually verify both package modes, all 48 Skill profiles, filters, language switching, task and project CRUD, refresh persistence, and responsive layouts in your target browsers.# Xgxgx
Ctvtvv
