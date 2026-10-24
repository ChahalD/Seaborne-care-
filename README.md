
/* SEABORNE CARE - RESPONSIVE LAYOUT FIX */

html, body {
  width: 100%;
  max-width: 100%;
  margin: 0;
  padding: 0;
  overflow-x: hidden;
}

*, *::before, *::after {
  box-sizing: border-box;
}

img {
  max-width: 100%;
  height: auto;
}

.container {
  width: 100%;
  max-width: 1120px;
  margin-left: auto;
  margin-right: auto;
}

.navbar {
  width: 100%;
  max-width: 1200px;
  margin: auto;
}

.hero {
  width: 100%;
  padding: 80px 20px;
}

.hero h1 {
  font-size: clamp(30px, 5vw, 58px);
  overflow-wrap: break-word;
}

.hero p {
  font-size: clamp(15px, 2vw, 18px);
}

.card, .contact-card {
  min-width: 0;
  overflow-wrap: anywhere;
}

.split > *,
.cards > *,
.contact-grid > *,
.footer-grid > * {
  min-width: 0;
}

@media (max-width: 900px) {
  .cards {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }

  .split {
    grid-template-columns: 1fr;
  }

  .navbar {
    padding: 12px 18px;
  }
}

@media (max-width: 600px) {
  .cards,
  .contact-grid,
  .footer-grid {
    grid-template-columns: 1fr;
  }

  .container {
    padding: 40px 16px;
  }

  .hero {
    padding: 65px 16px;
  }

  .hero h1 {
    font-size: 32px;
  }

  .page-banner {
    padding: 50px 16px;
  }

  .page-banner h1 {
    font-size: 32px;
  }

  .card {
    padding: 24px 18px;
  }

  .cta h2 {
    font-size: 28px;
  }
}
