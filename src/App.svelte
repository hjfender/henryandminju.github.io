<!-- App.svelte -->
<script>
  import { Heart, Calendar, MapPin, Gift } from 'lucide-svelte';
  let activeSection = 'home';

  const sections = ['Home', 'RSVP', 'Registry', 'Travel'];
  
  function setActiveSection(section) {
    activeSection = section.toLowerCase();
  }
</script>

<svelte:head>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Mr+De+Haviland&family=Qwitcher+Grypen:wght@400;700&display=swap" rel="stylesheet">
</svelte:head>

<div class="container">
  <!-- Navigation -->
  <nav>
    <div class="nav-links">
      {#each sections as section}
        <a
          href="#{section.toLowerCase()}"
          on:click={() => setActiveSection(section)}
          class={activeSection === section.toLowerCase() ? 'active' : ''}
        >
          {section}
        </a>
      {/each}
    </div>
  </nav>

  <!-- Hero Section -->
  <img class="header-img" src="../../public/photos/1.jpg" alt="Henry & Minju" />
  <section class="hero" id="home">
    <h1>Henry & Minju</h1>
    <div class="divider"></div>
    <p>Are getting married</p>
  </section>

  <!-- RSVP Section -->
  <section class="rsvp" id="rsvp">
    <h2>RSVP</h2>
    <div class="content-box">
      <div class="icon-container">
        <Calendar class="icon" />
      </div>
      <p>
        Please join us for our wedding celebration
        <span>Coming soon...</span>
      </p>
    </div>
  </section>

  <!-- Registry Section -->
  <section class="registry" id="registry">
    <h2>Registry</h2>
    <div class="content-box">
      <div class="icon-container">
        <Gift class="icon" />
      </div>
      <p>
        Your presence at our wedding is the greatest gift.
        <span>Registry details coming soon.</span>
      </p>
    </div>
  </section>

  <!-- Travel Section -->
  <section class="travel" id="travel">
    <h2>Travel</h2>
    <div class="content-box">
      <div class="icon-container">
        <MapPin class="icon" />
      </div>
      <p>
        Accommodation and travel information
        <span>Details coming soon.</span>
      </p>
    </div>
  </section>

  <!-- Footer -->
  <footer>
    <div class="divider"></div>
    <p>Henry & Minju</p>
  </footer>
</div>

<style>
  :global(body) {
    margin: 0;
    font-family: serif;
    background-color: #d6d2bd;
    color: #57534e;
  }

  :global(html) {
    scroll-behavior: smooth;
  }

  .container {
    min-height: 100vh;
  }

  nav {
    position: sticky;
    top: 0;
    background-color: rgba(250, 250, 249, 0.5);
    backdrop-filter: blur(8px);
    padding: 1.2rem;
    z-index: 50;
  }

  .nav-links {
    max-width: 48rem;
    margin: 0 auto;
    display: flex;
    justify-content: center;
    gap: 3rem;
  }

  a {
    background: none;
    border: none;
    font-size: 0.875rem;
    font-weight: 300;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: #57534e;
    cursor: pointer;
    transition: color 0.3s ease;
    text-decoration: none;
  }

  a:hover {
    color: #065f46;
  }

  a.active {
    color: #065f46;
  }

  section {
    padding: 6rem 1rem;
  }

  section:nth-child(even) {
    background-color: rgb(250, 250, 249, 0.8);
  }

  .hero {
    text-align: center;
    padding: 8rem 1rem;
  }

  .header-img {
    width: 100%;
    height: 100vh;
    object-fit: cover;
    object-position: center;
  }

  h1 {
    font-size: 4.25rem;
    font-weight: 300;
    /* letter-spacing: 0.2em; */
    color: #064e3b;
    margin-bottom: 1.5rem;
  }

  h2 {
    font-size: 3rem;
    font-weight: 300;
    letter-spacing: 0.2em;
    color: #064e3b;
    text-align: center;
    margin-bottom: 4rem;
  }

  h1, h2 {
  font-family: 'Qwitcher Grypen', cursive;
  /* Since it's a script font, you might want to adjust sizes */
  font-weight: 700; /* or 400 for lighter weight */
}


  .divider {
    width: 4rem;
    height: 1px;
    background-color: #064e3b;
    margin: 1.5rem auto;
  }

  .content-box {
    max-width: 42rem;
    margin: 0 auto;
    padding: 3rem;
    background-color: white;
  }

  section:nth-child(even) .content-box {
    background-color: #fafaf9;
  }

  .icon-container {
    display: flex;
    justify-content: center;
    margin-bottom: 2rem;
  }

  :global(.icon) {
    width: 1.25rem;
    height: 1.25rem;
    color: #064e3b;
  }

  p {
    text-align: center;
    letter-spacing: 0.1em;
    line-height: 1.6;
  }

  span {
    display: block;
    margin-top: 1.5rem;
  }

  footer {
    padding: 3rem 1rem;
    text-align: center;
  }

  footer p {
    font-size: 0.875rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
  }

  @media (max-width: 640px) {
    .nav-links {
      gap: 1.5rem;
    }

    a {
      font-size: 0.75rem;
    }

    h1 {
      font-size: 1.875rem;
    }

    h2 {
      font-size: 1.25rem;
    }

    .content-box {
      padding: 2rem 1rem;
    }
  }
</style>