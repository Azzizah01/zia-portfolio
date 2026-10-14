
<script lang="ts">
  let menuOpen = $state(false);
  let activeFilter = $state('All');

  // CONTACT INFORMATION
  // Verify these details before publishing.
  const contact = {
    email: 'azizzahnur01@gmail.com',
    phone: '+6289506886278',
    linkedin: 'https://www.linkedin.com/in/nur-azzizah'
  };

  const emailLink = `mailto:${contact.email}`;
  const whatsappLink =
    `https://wa.me/${contact.phone.replace(/\D/g, '')}`;

  type Project = {
    number: string;
    title: string;
    category: string;
    description: string;
    image: string;
    year: string;
  };

  const projects: Project[] = [
    {
      number: '01',
      title: 'Fuel Intelligence',
      category: 'Dashboard',
      description:
        'An analytics dashboard for monitoring fuel distribution, forecasting demand, and prioritizing delivery operations.',
      image: '/images/fuel-intelligence.png',
      year: '2026'
    },
    {
      number: '02',
      title: 'Warehouse Picking',
      category: 'Product Design',
      description:
        'A warehouse picking strategy focused on location verification, SKU validation, quantity accuracy, and barcode scanning.',
      image: '/images/warehouse-picking.png',
      year: '2026'
    },
    {
      number: '03',
      title: 'PT Sans Athan Group',
      category: 'Website',
      description:
        'A corporate landing page for a technology company specializing in AI, IoT, smart cities, and digital solutions.',
      image: '/images/sans-athan-landing.png',
      year: '2026'
    },
    {
      number: '04',
      title: 'HR Flow',
      category: 'Dashboard',
      description:
        'An HR management dashboard for employee data, onboarding progress, document submissions, and workforce insights.',
      image: '/images/hr-flow.png',
      year: '2026'
    },
    {
      number: '05',
      title: 'LPMUKP',
      category: 'Website',
      description:
        'A website redesign concept for a financing institution supporting marine and fisheries businesses in Indonesia.',
      image: '/images/lpmukp.png',
      year: '2026'
    },
    {
      number: '06',
      title: 'Socialens',
      category: 'Website',
      description:
        'A landing page for an AI-powered social listening platform designed to monitor public opinion and digital conversations.',
      image: '/images/socialens.png',
      year: '2026'
    },
    {
      number: '07',
      title: 'CTARSA',
      category: 'Website',
      description:
        'A website design project exploring content structure, navigation, and a clearer digital user experience.',
      image: '/images/ctarsa.jpg',
      year: '2025'
    },
    {
      number: '08',
      title: 'Donation Landing Page',
      category: 'Website',
      description:
        'A donation landing page concept focused on clear messaging, accessible information, and a straightforward user journey.',
      image: '/images/donation.png',
      year: '2025'
    },
    {
      number: '09',
      title: 'SoyDream',
      category: 'Website',
      description:
        'A soy milk product website concept with a fresh visual direction and an informative content structure.',
      image: '/images/soydream.png',
      year: '2025'
    },
    {
      number: '10',
      title: 'TevoU',
      category: 'Website',
      description:
        'A tea product website concept presenting product information through a clean and approachable interface.',
      image: '/images/tevou.png',
      year: '2025'
    },
    {
      number: '11',
      title: 'SmartSchool',
      category: 'Mobile App',
      description:
        'An educational application concept designed to support learning activities and interactions within a school environment.',
      image: '/images/smartschool.png',
      year: '2025'
    }
  ];

  const filters = [
    'All',
    'Dashboard',
    'Product Design',
    'Website',
    'Mobile App'
  ];

  let filteredProjects = $derived(
    activeFilter === 'All'
      ? projects
      : projects.filter(
          (project) => project.category === activeFilter
        )
  );
</script>

<svelte:head>
  <title>Nur Azzizah — UI/UX Designer</title>
  <meta
    name="description"
    content="Nur Azzizah's portfolio featuring digital products, dashboards, websites, and user-centered design."
  />
  <meta name="theme-color" content="#f4f3ef" />
</svelte:head>

<header class="navbar" id="home">
  <a href="#home" class="logo" aria-label="Nur Azzizah home">
    NUR<span>.</span>AZZIZAH
  </a>

  <button
    class="menu-toggle"
    onclick={() => (menuOpen = !menuOpen)}
    aria-label={menuOpen ? 'Close navigation' : 'Open navigation'}
    aria-expanded={menuOpen}
  >
    {menuOpen ? 'CLOSE −' : 'MENU +'}
  </button>

  <nav class:open={menuOpen} aria-label="Main navigation">
    <a href="#work" onclick={() => (menuOpen = false)}>Work</a>
    <a href="#about" onclick={() => (menuOpen = false)}>About</a>
    <a href="#contact" onclick={() => (menuOpen = false)}>Contact</a>
    <a href={emailLink} class="nav-cta">Let's Talk ↗</a>
  </nav>
</header>

<main>
  <!-- HERO -->
  <section class="hero">
    <div class="hero-copy">
      <p class="eyebrow">
        <span class="status-dot"></span>
        UI/UX DESIGNER · DIGITAL PRODUCT DESIGN
      </p>

      <h1>
        Designing digital experiences
        <span>with purpose.</span>
      </h1>

      <p class="hero-description">
        I design digital experiences that connect user needs
        with thoughtful, functional, and intuitive solutions.
      </p>

      <div class="hero-actions">
        <a class="button button-dark" href="#work">
          Explore My Work ↗
        </a>
        <a class="text-link" href="#about">More About Me ↓</a>
      </div>

      <div class="hero-note">
        <span>UI/UX DESIGN</span>
        <span>OPEN TO OPPORTUNITIES ↗</span>
      </div>
    </div>

    <div class="hero-visual">
      <div class="visual-label">
        <span>DESIGN PORTFOLIO</span>
        <span>SELECTED WORKS / 2025—2026</span>
      </div>

      <div class="hero-art">
        <div class="art-circle"></div>
        <div class="art-text">DESIGN<br />THINKING.</div>

        <div class="art-card">
          <span>MY APPROACH</span>
          <strong>Research.<br />Think.<br />Design.</strong>
        </div>

        <div class="art-index">01 — 11</div>
        <div class="art-cross">✳</div>
      </div>

      <div class="visual-caption">
        <span>INDEPENDENT THINKING</span>
        <span>INTENTIONAL DESIGN ↗</span>
      </div>
    </div>

    <div class="hero-index">PORTFOLIO — 2026</div>
  </section>

  <!-- PROJECTS -->
  <section class="work-section" id="work">
    <div class="section-heading">
      <div>
        <p class="eyebrow">A SELECTION OF MY WORK</p>
        <h2>Selected <span>projects.</span></h2>
      </div>

      <p class="section-side-note">
        Digital products, interfaces,<br />
        and experiences designed with intention.
      </p>
    </div>

    <div class="filter-list" aria-label="Filter projects">
      {#each filters as filter}
        <button
          class:active={activeFilter === filter}
          aria-pressed={activeFilter === filter}
          onclick={() => (activeFilter = filter)}
        >
          {filter === 'All' ? 'All Projects' : filter}
        </button>
      {/each}
    </div>

    <div class="project-grid">
      {#each filteredProjects as project (project.number)}
        <article class="project-card">
          <div class="project-heading">
            <div class="project-meta">
              <span>{project.number} / {project.category}</span>
              <span>{project.year}</span>
            </div>

            <h3>{project.title}</h3>
            <p class="project-description">
              {project.description}
            </p>
          </div>

          <div class="project-image">

            <div
            class="image-scroll"
            aria-label={`Scrollable preview of ${project.title}`}
            >
            <img
                src={project.image}
                alt={`${project.title} project preview`}
                loading="lazy"
            />
            </div>


            <span class="scroll-hint">
              SCROLL TO EXPLORE ↓
            </span>
          </div>
        </article>
      {/each}
    </div>

    <p class="work-footnote">
      DIFFERENT PROBLEMS. THOUGHTFUL SOLUTIONS. ↗
    </p>
  </section>

  <!-- ABOUT -->
  <section class="about-section" id="about">
    <div class="about-top">
      <p class="eyebrow">A LITTLE ABOUT ME</p>
      <span class="about-symbol" aria-hidden="true">✳</span>
    </div>

    <div class="about-content">
      <h2>
        Designing with curiosity.<br />
        Building with <span>purpose.</span>
      </h2>

      <div class="about-description">
        <p>
          I'm Nur Azzizah, a UI/UX Designer with an Informatics
          background who bridges design thinking and technology
          to create meaningful digital experiences.
        </p>

        <p>
          From data-driven dashboards to websites and mobile
          applications, I turn complex requirements into
          intuitive interfaces that balance usability, clarity,
          and visual quality.
        </p>

        <a class="text-link" href={emailLink}>
          Let's create something meaningful ↗
        </a>
      </div>
    </div>

    <div class="skills">
      <span>01 / UX RESEARCH</span>
      <span>02 / UI DESIGN</span>
      <span>03 / PROTOTYPING</span>
      <span>04 / DESIGN SYSTEMS</span>
      <span>05 / USER FLOWS</span>
      <span>06 / INTERACTION DESIGN</span>
    </div>

    <!-- TOOLS -->
    <div class="tools-section">
      <div class="tools-heading">
        <div>
          <p class="eyebrow">MY WORKFLOW</p>
          <h3>Tools I work with<span>.</span></h3>
        </div>

        <p>
          A combination of design tools and AI-assisted workflows
          to explore ideas, refine concepts, and build better experiences.
        </p>
      </div>

      <div class="tools-grid">
        <article class="tool-card">
          <div class="tool-top">
            <span class="tool-number">01</span>
            <span class="tool-symbol">F</span>
          </div>

          <h4>Figma</h4>
          <p>
            UI design, wireframing, interactive prototyping,
            and design systems.
          </p>

          <span class="tool-tag">DESIGN & PROTOTYPING</span>
        </article>

        <article class="tool-card">
          <div class="tool-top">
            <span class="tool-number">02</span>
            <span class="tool-symbol">S</span>
          </div>

          <h4>Google Stitch</h4>
          <p>
            AI-assisted interface exploration and rapid
            UI concept development.
          </p>

          <span class="tool-tag">AI-ASSISTED DESIGN</span>
        </article>

        <article class="tool-card">
          <div class="tool-top">
            <span class="tool-number">03</span>
            <span class="tool-symbol">C</span>
          </div>

          <h4>Claude AI</h4>
          <p>
            Design ideation, UX writing, research synthesis,
            and AI-assisted workflows.
          </p>

          <span class="tool-tag">AI ASSISTANT</span>
        </article>
      </div>
    </div>
  </section>

  <!-- CONTACT -->
  <section class="contact-section" id="contact">
    <div class="contact-background" aria-hidden="true">
      LET'S<br />MAKE<br />IT MATTER.
    </div>

    <div class="contact-content">
      <p class="eyebrow">HAVE A PROJECT IN MIND?</p>

      <h2>
        Good ideas start<br />
        with a <span>conversation.</span>
      </h2>

      <p>
        I'm open to job opportunities, freelance projects,
        and meaningful collaborations. Let's talk about
        what we can create together.
      </p>

      <div class="contact-actions">
        <a class="button button-light" href={emailLink}>
          Send an Email ↗
        </a>

        <a
          class="button button-outline"
          href={whatsappLink}
          target="_blank"
          rel="noreferrer"
        >
          WhatsApp ↗
        </a>
      </div>
    </div>

    <div class="contact-footer">
      <a href={emailLink}>
        <span>EMAIL</span>
        {contact.email}
      </a>

      <a
        href={contact.linkedin}
        target="_blank"
        rel="noreferrer"
      >
        <span>LINKEDIN</span>
        View LinkedIn Profile ↗
      </a>

      <a
        href={whatsappLink}
        target="_blank"
        rel="noreferrer"
      >
        <span>PHONE / WHATSAPP</span>
        {contact.phone}
      </a>

      <span class="copyright">NUR AZZIZAH © 2026</span>
    </div>
  </section>
</main>

<style>
  :global(*) {
    box-sizing: border-box;
  }

  :global(html) {
    scroll-behavior: smooth;
    scroll-padding-top: 85px;
  }

  :global(body) {
    margin: 0;
    background: #f4f3ef;
    color: #171715;
    font-family: Arial, Helvetica, sans-serif;
    -webkit-font-smoothing: antialiased;
  }

  :global(a) {
    color: inherit;
    text-decoration: none;
  }

  :global(button) {
    font: inherit;
  }

  /* NAVIGATION */
  .navbar {
    min-height: 76px;
    padding: 0 6%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    border-bottom: 1px solid #deddd7;
  }

  .logo {
    font-size: 18px;
    font-weight: 800;
    letter-spacing: -1px;
  }

  .logo span {
    color: #999891;
  }

  nav {
    display: flex;
    align-items: center;
    gap: 32px;
    font-size: 12px;
  }

  nav a:not(.nav-cta):hover,
  .text-link:hover {
    opacity: 0.55;
  }

  .nav-cta {
    padding: 13px 20px;
    border-radius: 30px;
    background: #171715;
    color: #fff;
  }

  .menu-toggle {
    display: none;
    border: 0;
    background: transparent;
    cursor: pointer;
  }

  /* HERO */
  .hero {
    min-height: 600px;
    padding: 80px 8% 60px;
    display: grid;
    grid-template-columns: 1.05fr 0.95fr;
    gap: 7%;
    align-items: center;
    position: relative;
    overflow: hidden;
  }

  .eyebrow {
    font-size: 10px;
    letter-spacing: 1.6px;
    line-height: 1.8;
    font-weight: 700;
  }

  .status-dot {
    display: inline-block;
    width: 7px;
    height: 7px;
    background: #77766f;
    border-radius: 50%;
    margin-right: 7px;
  }

  h1 {
    max-width: 590px;
    font-size: clamp(48px, 6vw, 86px);
    line-height: 0.99;
    letter-spacing: -0.075em;
    margin: 26px 0;
    font-weight: 800;
  }

  h1 span,
  .section-heading h2 span,
  .about-content h2 span,
  .contact-content h2 span {
    color: #999891;
  }

  .hero-description {
    max-width: 400px;
    color: #66655f;
    font-size: 14px;
    line-height: 1.8;
  }

  .hero-actions {
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    gap: 25px;
    margin-top: 30px;
  }

  .button {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 12px;
    padding: 15px 22px;
    border-radius: 40px;
    font-size: 12px;
    transition: transform 0.2s ease;
  }

  .button:hover {
    transform: translateY(-3px);
  }

  .button-dark {
    background: #171715;
    color: #fff;
  }

  .text-link {
    font-size: 12px;
  }

  .hero-note {
    border-top: 1px solid #d8d7d1;
    margin-top: 55px;
    padding-top: 18px;
    display: flex;
    justify-content: space-between;
    gap: 12px;
    font-size: 9px;
    letter-spacing: 0.8px;
    color: #77766f;
  }

  .hero-visual {
    padding: 20px 0;
    min-width: 0;
  }

  .visual-label,
  .visual-caption {
    display: flex;
    justify-content: space-between;
    gap: 12px;
    font-size: 9px;
    letter-spacing: 1px;
  }

  .visual-label {
    margin-bottom: 15px;
    color: #77766f;
  }

  .hero-art {
    min-height: 380px;
    background: #e2e1db;
    position: relative;
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .art-text {
    position: relative;
    z-index: 1;
    font-size: clamp(48px, 6vw, 88px);
    font-weight: 800;
    line-height: 0.82;
    letter-spacing: -0.09em;
    transform: rotate(-7deg);
    mix-blend-mode: multiply;
  }

  .art-circle {
    position: absolute;
    width: 260px;
    height: 260px;
    border: 1px solid #a6a59e;
    border-radius: 50%;
    right: -60px;
    top: -50px;
  }

  .art-card {
    position: absolute;
    z-index: 2;
    bottom: 24px;
    left: 22px;
    padding: 20px;
    width: 155px;
    background: #f4f3ef;
    transform: rotate(-4deg);
  }

  .art-card span {
    display: block;
    font-size: 9px;
    letter-spacing: 1px;
    margin-bottom: 12px;
  }

  .art-card strong {
    font-size: 20px;
    line-height: 1.1;
  }

  .art-index {
    position: absolute;
    top: 22px;
    right: 22px;
    font-size: 10px;
    letter-spacing: 1px;
  }

  .art-cross {
    position: absolute;
    bottom: 24px;
    right: 25px;
    font-size: 48px;
  }

  .visual-caption {
    margin-top: 15px;
  }

  .hero-index {
    position: absolute;
    right: 2%;
    top: 50%;
    writing-mode: vertical-rl;
    font-size: 9px;
    letter-spacing: 2px;
    color: #888780;
  }

  /* PROJECTS */
  .work-section {
    padding: 95px 8%;
    background: #e9e8e2;
  }

  .section-heading {
    display: flex;
    justify-content: space-between;
    align-items: end;
    gap: 24px;
    margin-bottom: 35px;
  }

  .section-heading h2,
  .about-content h2,
  .contact-content h2 {
    font-size: clamp(42px, 5.5vw, 72px);
    letter-spacing: -0.065em;
    line-height: 1.02;
    margin: 15px 0 0;
  }

  .section-side-note {
    color: #6c6b65;
    font-size: 12px;
    line-height: 1.8;
  }

  .filter-list {
    display: flex;
    flex-wrap: wrap;
    gap: 9px;
    margin-bottom: 35px;
  }

  .filter-list button {
    padding: 10px 15px;
    border: 1px solid #c9c8c1;
    border-radius: 30px;
    background: transparent;
    color: #55544e;
    font-size: 11px;
    cursor: pointer;
    transition: background 0.2s, color 0.2s;
  }

  .filter-list button:hover,
  .filter-list button.active {
    background: #171715;
    color: #fff;
    border-color: #171715;
  }

  .project-grid {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    column-gap: 28px;
    row-gap: 52px;
    align-items: start;
  }

  .project-card {
    min-width: 0;
    display: flex;
    flex-direction: column;
  }

  .project-heading {
    display: flex;
    flex-direction: column;
    margin-bottom: 20px;
  }

  .project-meta {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 12px;
    color: #77766f;
    font-size: 10px;
    line-height: 1.5;
    letter-spacing: 0.6px;
    text-transform: uppercase;
  }

  .project-heading h3 {
    margin: 13px 0 10px;
    font-size: clamp(27px, 2.7vw, 36px);
    font-weight: 700;
    line-height: 1.08;
    letter-spacing: -1.8px;
  }

  .project-description {
    margin: 0;
    max-width: 500px;
    color: #696861;
    font-size: 12px;
    line-height: 1.75;
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-line-clamp: 2;
    line-clamp: 2;
    overflow: hidden;
    min-height: 42px;
  }

  .project-image {
    position: relative;
    width: 100%;
    aspect-ratio: 4 / 3;
    overflow: hidden;
    background: #deddd7;
    border: 1px solid #d7d6cf;
  }

  .image-scroll {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    overflow-x: hidden;
    overflow-y: auto;
    overscroll-behavior: contain;
    scrollbar-width: thin;
    scrollbar-color: #aaa9a2 transparent;
    cursor: ns-resize;
  }

  .image-scroll:focus-visible {
    outline: 2px solid #171715;
    outline-offset: -3px;
  }

  .image-scroll img {
    display: block;
    width: 100%;
    height: auto;
    max-width: 100%;
    margin: 0;
    object-fit: contain;
    object-position: top;
  }

  .image-scroll::-webkit-scrollbar {
    width: 5px;
  }

  .image-scroll::-webkit-scrollbar-track {
    background: transparent;
  }

  .image-scroll::-webkit-scrollbar-thumb {
    background: #aaa9a2;
    border-radius: 10px;
  }

  .scroll-hint {
    position: absolute;
    right: 10px;
    bottom: 10px;
    z-index: 2;
    padding: 8px 10px;
    background: rgba(244, 243, 239, 0.94);
    color: #393832;
    font-size: 9px;
    letter-spacing: 0.5px;
    pointer-events: none;
  }

  .work-footnote {
    border-top: 1px solid #c9c8c1;
    margin-top: 70px;
    padding-top: 20px;
    font-size: 10px;
    letter-spacing: 1.4px;
  }

  /* ABOUT */
  .about-section {
    padding: 95px 8%;
  }

  .about-top {
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-bottom: 1px solid #d8d7d1;
    padding-bottom: 20px;
  }

  .about-symbol {
    font-size: 42px;
  }

  .about-content {
    display: grid;
    grid-template-columns: 1.2fr 0.8fr;
    gap: 10%;
    align-items: center;
    padding: 55px 0 65px;
  }

  .about-description p {
    color: #66655f;
    font-size: 13px;
    line-height: 1.9;
    margin-bottom: 22px;
  }

  .about-description .text-link {
    display: inline-block;
    border-bottom: 1px solid #171715;
    padding-bottom: 8px;
    margin-top: 10px;
  }

  .skills {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    border-top: 1px solid #d8d7d1;
    padding-top: 22px;
  }

  .skills span {
    padding: 13px 16px;
    border: 1px solid #d8d7d1;
    border-radius: 30px;
    font-size: 10px;
    letter-spacing: 0.4px;
  }

  /* TOOLS */
  .tools-section {
    border-top: 1px solid #d8d7d1;
    padding-top: 35px;
    margin-top: 55px;
  }

  .tools-heading {
    display: flex;
    justify-content: space-between;
    align-items: end;
    gap: 30px;
    margin-bottom: 25px;
  }

  .tools-heading h3 {
    margin: 10px 0 0;
    font-size: clamp(28px, 3.5vw, 42px);
    letter-spacing: -1.8px;
  }

  .tools-heading h3 span {
    color: #999891;
  }

  .tools-heading > p {
    max-width: 330px;
    margin: 0;
    color: #696861;
    font-size: 12px;
    line-height: 1.8;
  }

  .tools-grid {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 14px;
  }

  .tool-card {
    min-width: 0;
    min-height: 230px;
    padding: 22px;
    border: 1px solid #d8d7d1;
    border-radius: 4px;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    transition: background 0.2s ease;
  }

  .tool-card:hover {
    background: #efeee8;
  }

  .tool-top {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
  }

  .tool-number {
    font-size: 10px;
    color: #77766f;
    letter-spacing: 1px;
  }

  .tool-symbol {
    display: grid;
    place-items: center;
    width: 36px;
    height: 36px;
    border: 1px solid #d8d7d1;
    border-radius: 50%;
    font-size: 14px;
    font-weight: 700;
  }

  .tool-card h4 {
    margin: 28px 0 10px;
    font-size: 21px;
    letter-spacing: -0.7px;
  }

  .tool-card p {
    margin: 0 0 24px;
    color: #696861;
    font-size: 12px;
    line-height: 1.8;
  }

  .tool-tag {
    margin-top: auto;
    font-size: 9px;
    letter-spacing: 0.7px;
    color: #77766f;
  }

  /* CONTACT */
  .contact-section {
    position: relative;
    overflow: hidden;
    background: #171715;
    color: #f4f3ef;
    padding: 100px 8% 25px;
  }

  .contact-background {
    position: absolute;
    right: -15px;
    top: 25px;
    font-size: clamp(100px, 18vw, 240px);
    line-height: 0.78;
    letter-spacing: -0.09em;
    font-weight: 800;
    color: #242421;
    text-align: right;
    pointer-events: none;
  }

  .contact-content {
    position: relative;
    z-index: 1;
    max-width: 650px;
    padding: 30px 0 90px;
  }

  .contact-content h2 {
    font-size: clamp(45px, 6.5vw, 86px);
  }

  .contact-content > p:not(.eyebrow) {
    color: #b0afa8;
    font-size: 13px;
    line-height: 1.8;
    max-width: 350px;
    margin: 25px 0;
  }

  .contact-actions {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
    margin-top: 28px;
  }

  .button-light {
    background: #f4f3ef;
    color: #171715;
  }

  .button-outline {
    border: 1px solid #77766f;
    color: #f4f3ef;
  }

  .contact-footer {
    position: relative;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: flex-start;
    gap: 24px;
    border-top: 1px solid #3b3a36;
    padding-top: 24px;
    font-size: 11px;
  }

  .contact-footer a {
    display: flex;
    flex-direction: column;
    gap: 8px;
    overflow-wrap: anywhere;
  }

  .contact-footer a span {
    color: #aaa9a2;
    font-size: 9px;
    letter-spacing: 1px;
  }

  .contact-footer a:hover {
    color: #aaa9a2;
  }

  .copyright {
    color: #aaa9a2;
    font-size: 9px;
    letter-spacing: 1px;
  }

  /* RESPONSIVE */
  @media (min-width: 1500px) {
    .hero,
    .work-section,
    .about-section,
    .contact-section {
      padding-left: max(8%, calc((100vw - 1250px) / 2));
      padding-right: max(8%, calc((100vw - 1250px) / 2));
    }
  }

  @media (max-width: 800px) {
    .navbar {
      min-height: 68px;
      padding: 0 6%;
    }

    .menu-toggle {
      display: block;
      font-size: 10px;
      letter-spacing: 1px;
    }

    nav {
      display: none;
      position: absolute;
      z-index: 5;
      top: 68px;
      left: 0;
      right: 0;
      padding: 25px 6%;
      background: #f4f3ef;
      border-bottom: 1px solid #deddd7;
      align-items: stretch;
      flex-direction: column;
      gap: 24px;
    }

    nav.open {
      display: flex;
    }

    .nav-cta {
      text-align: center;
    }

    .hero {
      grid-template-columns: 1fr;
      padding: 60px 6% 50px;
      gap: 35px;
    }

    h1 {
      font-size: clamp(48px, 12vw, 76px);
    }

    .hero-note {
      margin-top: 40px;
    }

    .hero-art {
      min-height: 310px;
    }

    .hero-index {
      display: none;
    }

    .work-section,
    .about-section {
      padding: 70px 6%;
    }

    .section-heading {
      align-items: start;
      flex-direction: column;
      gap: 10px;
    }

    .project-grid {
      grid-template-columns: 1fr;
      row-gap: 38px;
    }

    .project-heading h3 {
      font-size: 30px;
    }

    .project-description {
      min-height: auto;
    }

    .about-content {
      grid-template-columns: 1fr;
      gap: 25px;
      padding: 35px 0 45px;
    }

    .tools-heading {
      align-items: flex-start;
      flex-direction: column;
      gap: 12px;
    }

    .tools-grid {
      grid-template-columns: 1fr;
    }

    .tool-card {
      min-height: 180px;
    }

    .contact-section {
      padding: 75px 6% 25px;
    }

    .contact-background {
      top: 90px;
      font-size: 27vw;
    }

    .contact-content {
      padding-bottom: 70px;
    }

    .contact-actions {
      align-items: stretch;
    }

    .contact-footer {
      display: grid;
      grid-template-columns: 1fr;
      gap: 22px;
    }
  }

  @media (prefers-reduced-motion: reduce) {
    :global(html) {
      scroll-behavior: auto;
    }

    *,
    *::before,
    *::after {
      animation-duration: 0.01ms !important;
      transition-duration: 0.01ms !important;
    }
  }
</style>
