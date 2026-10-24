
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="Seaborne Care is a community initiative dedicated to spreading kindness and supporting underprivileged communities.">
<title>Seaborne Care | Spreading Kindness</title>
<style>
:root {
  --navy:#102b46;
  --blue:#1676a8;
  --light:#eaf5fa;
  --gold:#e9a944;
  --white:#fff;
  --text:#34475a;
}
* {box-sizing:border-box}
html {scroll-behavior:smooth}
body {margin:0;font-family:Arial,Helvetica,sans-serif;color:var(--text);background:#f7fafc;line-height:1.7}
a {color:inherit;text-decoration:none}
button {font:inherit;cursor:pointer}
header {background:white;box-shadow:0 3px 18px #102b4614;position:sticky;top:0;z-index:20}
.navbar {max-width:1200px;margin:auto;padding:15px 24px;display:flex;align-items:center;justify-content:space-between;gap:20px}
.logo {display:flex;align-items:center;gap:10px;font-size:22px;font-weight:800;color:var(--navy);cursor:pointer}
.logo-icon {background:var(--blue);color:white;width:42px;height:42px;border-radius:13px;display:grid;place-items:center;font-size:23px}
nav {display:flex;gap:20px;align-items:center;flex-wrap:wrap}
nav a {font-size:14px;font-weight:600;color:var(--navy);transition:.2s}
nav a:hover,nav a.active {color:var(--blue)}
.menu-btn {display:none;border:0;background:var(--light);padding:9px 13px;border-radius:8px;font-size:23px}
.page {display:none;min-height:65vh}
.page.active {display:block;animation:fade .4s ease}
@keyframes fade {from{opacity:0;transform:translateY(8px)}to{opacity:1;transform:translateY(0)}}
.hero {background:linear-gradient(115deg,#102b46e8,#1676a8df),url('https://images.unsplash.com/photo-1531206715517-5c0ba140b2b8?auto=format&fit=crop&w=1600&q=85') center/cover;color:white;padding:125px 24px;text-align:center}
.hero-inner {max-width:850px;margin:auto}
.eyebrow {text-transform:uppercase;letter-spacing:3px;font-size:13px;font-weight:700;color:#f8c46c}
.hero h1 {font-size:clamp(38px,6vw,72px);line-height:1.12;margin:18px 0}
.hero p {font-size:19px;color:#e3eff6;max-width:650px;margin:0 auto 30px}
.btn {display:inline-block;border:0;border-radius:9px;background:var(--gold);color:#172c40;padding:13px 26px;font-weight:700;margin:5px;transition:.25s}
.btn:hover {transform:translateY(-3px);filter:brightness(.96)}
.btn-outline {background:transparent;border:2px solid white;color:white}
.container {max-width:1120px;margin:auto;padding:70px 24px}
.section-heading {text-align:center;margin-bottom:38px}
.section-heading h2 {font-size:clamp(28px,4vw,40px);color:var(--navy);margin:5px 0 12px}
.section-heading p {max-width:650px;margin:auto}
.tag {color:var(--blue);font-weight:700;letter-spacing:2px;font-size:12px;text-transform:uppercase}
.cards {display:grid;grid-template-columns:repeat(3,1fr);gap:22px}
.card {background:white;padding:32px 25px;border-radius:16px;box-shadow:0 6px 25px #12314c0d;transition:.3s}
.card:hover {transform:translateY(-5px)}
.card-icon {font-size:36px;margin-bottom:15px}
.card h3 {color:var(--navy);font-size:21px;margin:8px 0}
.card p {margin:0}
.soft {background:var(--light)}
.page-banner {background:linear-gradient(115deg,var(--navy),var(--blue));color:white;padding:75px 24px;text-align:center}
.page-banner h1 {font-size:clamp(34px,5vw,52px);margin:0 0 12px}
.page-banner p {max-width:680px;margin:auto;color:#e0eff8}
.prose {max-width:850px;margin:auto}
.prose h2 {color:var(--navy);margin-top:32px}
.prose p {margin-bottom:20px}
.highlight {background:var(--light);border-left:4px solid var(--blue);padding:25px;border-radius:10px;margin:30px 0}
.split {display:grid;grid-template-columns:1fr 1fr;gap:40px;align-items:center}
.split img {width:100%;height:340px;object-fit:cover;border-radius:18px}
.contact-grid {display:grid;grid-template-columns:repeat(2,1fr);gap:24px;max-width:850px;margin:auto}
.contact-card {background:white;text-align:center;padding:45px 20px;border-radius:16px;box-shadow:0 5px 25px #12314c12;overflow-wrap:anywhere}
.contact-card .symbol {font-size:40px}
.contact-card h3 {color:var(--navy)}
.contact-card a {color:var(--blue);font-size:clamp(16px,2vw,22px);font-weight:bold}
.faq {max-width:850px;margin:auto}
details {background:white;margin:13px 0;border-radius:12px;padding:20px 23px;box-shadow:0 3px 15px #12314c0a}
summary {font-weight:700;color:var(--navy);cursor:pointer}
details p {margin-bottom:0}
.cta {background:var(--navy);color:white;text-align:center;padding:70px 24px}
.cta h2 {font-size:36px;margin:0 0 15px}
.cta p {max-width:650px;margin:0 auto 25px;color:#dce9f2}
footer {background:#081c2f;color:#c8d6e1;padding:45px 24px 20px}
.footer-grid {max-width:1120px;margin:auto;display:grid;grid-template-columns:2fr 1fr 1fr;gap:35px}
footer h3 {color:white;margin-top:0}
footer a {display:block;margin:8px 0}
footer a:hover {color:#f6c777}
.copyright {text-align:center;border-top:1px solid #ffffff22;margin:35px auto 0;max-width:1120px;padding-top:20px;font-size:13px}
@media(max-width:800px){
  .menu-btn {display:block}
  nav {display:none;position:absolute;top:70px;left:0;right:0;background:white;padding:20px 24px;flex-direction:column;align-items:stretch;box-shadow:0 10px 20px #0001}
  nav.open {display:flex}
  nav a {padding:8px}
  .cards,.contact-grid,.split,.footer-grid {grid-template-columns:1fr}
  .hero {padding:95px 22px}
  .container {padding:50px 20px}
  .split img {height:250px}
}
</style>
</head>
<body>

<header>
  <div class="navbar">
    <a class="logo" href="#home">
      <span class="logo-icon">♥</span>
      <span>Seaborne Care</span>
    </a>
    <button class="menu-btn" id="menuBtn" aria-label="Toggle menu" aria-expanded="false">☰</button>
    <nav id="nav">
      <a href="#home">Home</a>
      <a href="#about">About Us</a>
      <a href="#mission">Our Mission</a>
      <a href="#vision">Our Vision</a>
      <a href="#faq">FAQ</a>
      <a href="#contact">Contact Us</a>
    </nav>
  </div>
</header>

<main>

<section id="home" class="page active">
  <div class="hero">
    <div class="hero-inner">
      <div class="eyebrow">Together for a better tomorrow</div>
      <h1>Small Acts of Kindness.<br>Big Waves of Hope.</h1>
      <p>At Seaborne Care, we believe every person deserves compassion, dignity, and the joy of being remembered.</p>
      <a class="btn" href="#about">Discover Our Story</a>
      <a class="btn btn-outline" href="#contact">Get in Touch</a>
    </div>
  </div>

  <div class="container">
    <div class="section-heading">
      <span class="tag">What We Do</span>
      <h2>Care That Reaches Every Heart</h2>
      <p>We aim to bring meaningful support and moments of happiness to underprivileged individuals and communities.</p>
    </div>
    <div class="cards">
      <div class="card">
        <div class="card-icon">🍲</div>
        <h3>Food Distribution</h3>
        <p>Sharing food with people in need and helping spread the warmth of a caring community.</p>
      </div>
      <div class="card">
        <div class="card-icon">🎁</div>
        <h3>Occasion-Based Giving</h3>
        <p>Celebrating Diwali, Holi, New Year, birthdays, and other special occasions through thoughtful distribution drives.</p>
      </div>
      <div class="card">
        <div class="card-icon">🤝</div>
        <h3>Community Support</h3>
        <p>Encouraging generosity, compassion, and practical assistance for people facing difficult circumstances.</p>
      </div>
    </div>
  </div>

  <div class="container soft" style="max-width:none">
    <div class="split" style="max-width:1120px;margin:auto">
      <div>
        <span class="tag">Our Purpose</span>
        <h2 style="color:var(--navy);font-size:36px">Making Every Celebration Meaningful</h2>
        <p>For us, celebrations are not only about personal happiness. They are also an opportunity to share happiness with those who may need it most.</p>
        <p>Whether it is a festival, birthday, or an ordinary day, Seaborne Care seeks to turn compassion into action.</p>
        <a href="#mission" class="btn">Explore Our Mission</a>
      </div>
      <img src="https://images.unsplash.com/photo-1531206715517-5c0ba140b2b8?auto=format&fit=crop&w=1000&q=85" alt="People coming together in a community">
    </div>
  </div>
</section>

<section id="about" class="page">
  <div class="page-banner">
    <h1>About Us</h1>
    <p>Driven by kindness. Inspired by humanity.</p>
  </div>
  <div class="container prose">
    <span class="tag">Who We Are</span>
    <h2>Welcome to Seaborne Care</h2>
    <p>Seaborne Care is a compassion-driven initiative focused on supporting underprivileged people through acts of kindness, food distribution, and occasion-based giving.</p>
    <p>We believe that happiness grows when it is shared. From distributing food to spreading joy during festivals such as Diwali, Holi, Dussehra, and New Year, our purpose is to make people feel valued and cared for.</p>
    <p>Our efforts are guided by empathy, respect, and a genuine desire to contribute positively to society.</p>
    <div class="highlight">
      <strong>Our Belief:</strong> No act of kindness is too small to make a meaningful difference in someone's life.
    </div>
    <h2>Why Seaborne Care?</h2>
    <p>Because care should extend beyond boundaries, backgrounds, and occasions. We want to create opportunities for people to share their blessings and celebrate humanity together.</p>
  </div>
</section>

<section id="mission" class="page">
  <div class="page-banner">
    <h1>Our Mission</h1>
    <p>Turning compassion into meaningful action.</p>
  </div>
  <div class="container prose">
    <h2>Our Mission</h2>
    <p>Our mission is to support underprivileged individuals and families by providing essential assistance, sharing food, and bringing joy through thoughtful distribution activities.</p>
    <p>We strive to make celebrations more inclusive by extending kindness to those who might otherwise be left out.</p>
    <div class="cards" style="grid-template-columns:1fr">
      <div class="card"><h3>♥ Spread Compassion</h3><p>Promote empathy, dignity, and human connection.</p></div>
      <div class="card"><h3>♥ Share Essentials</h3><p>Offer food and useful items based on the needs of people and communities.</p></div>
      <div class="card"><h3>♥ Celebrate Together</h3><p>Use festivals and special occasions as opportunities to share happiness.</p></div>
    </div>
  </div>
</section>

<section id="vision" class="page">
  <div class="page-banner">
    <h1>Our Vision</h1>
    <p>A future where kindness connects communities.</p>
  </div>
  <div class="container prose">
    <h2>Building a More Caring World</h2>
    <p>Our vision is to create a society where no individual feels forgotten, where compassion is a shared responsibility, and where every celebration offers an opportunity to uplift others.</p>
    <p>We aspire to inspire more people to embrace generosity as part of everyday life and contribute to a world built on dignity, inclusion, and mutual care.</p>
    <div class="highlight">
      <strong>Our Vision Statement:</strong> A world where every act of giving creates hope, every celebration includes compassion, and every person is treated with dignity.
    </div>
  </div>
</section>

<section id="faq" class="page">
  <div class="page-banner">
    <h1>Frequently Asked Questions</h1>
    <p>Learn more about Seaborne Care and our purpose.</p>
  </div>
  <div class="container faq">
    <details>
      <summary>What is Seaborne Care?</summary>
      <p>Seaborne Care is a community-focused initiative dedicated to helping underprivileged people through food distribution, essential support, and occasion-based giving.</p>
    </details>
    <details>
      <summary>What activities does Seaborne Care organize?</summary>
      <p>Our activities include sharing food and distributing useful items during festivals, birthdays, and other special occasions, depending on needs and available resources.</p>
    </details>
    <details>
      <summary>Which occasions does Seaborne Care celebrate?</summary>
      <p>These may include Diwali, Holi, Dussehra, New Year, birthdays, and other meaningful occasions.</p>
    </details>
    <details>
      <summary>Who can benefit from Seaborne Care?</summary>
      <p>Our efforts are intended to support underprivileged individuals and communities. Assistance depends on the nature and availability of each activity.</p>
    </details>
    <details>
      <summary>How can I contact Seaborne Care?</summary>
      <p>You can call +91 9650285586 or email Care@seabornemcs.in.</p>
    </details>
    <details>
      <summary>Can I participate in your activities?</summary>
      <p>Contact our team to ask about possible participation or collaboration opportunities. Availability may vary.</p>
    </details>
    <details>
      <summary>Is Seaborne Care a registered NGO?</summary>
      <p>Please contact our team for information about our organizational or legal registration status.</p>
    </details>
  </div>
</section>

<section id="contact" class="page">
  <div class="page-banner">
    <h1>Contact Us</h1>
    <p>Have a question, suggestion, or collaboration idea? We'd love to hear from you.</p>
  </div>
  <div class="container">
    <div class="section-heading">
      <span class="tag">Connect With Us</span>
      <h2>Let's Spread Kindness Together</h2>
      <p>Reach out through the contact details below.</p>
    </div>
    <div class="contact-grid">
      <div class="contact-card">
        <div class="symbol">📞</div>
        <h3>Call Us</h3>
        <a href="tel:+919650285586">+91 9650285586</a>
        <p>Tap to call our team</p>
      </div>
      <div class="contact-card">
        <div class="symbol">✉️</div>
        <h3>Email Us</h3>
        <a href="mailto:Care@seabornemcs.in">Care@seabornemcs.in</a>
        <p>Tap to send us an email</p>
      </div>
    </div>
    <div style="text-align:center;margin-top:40px">
      <a class="btn" href="mailto:Care@seabornemcs.in?subject=Enquiry%20for%20Seaborne%20Care">Send an Enquiry</a>
    </div>
  </div>
</section>

<section id="privacy" class="page">
  <div class="page-banner">
    <h1>Privacy Policy</h1>
    <p>Information about privacy when using our website.</p>
  </div>
  <div class="container prose">
    <p><strong>Last Updated:</strong> 24 October 2026</p>
    <h2>1. Introduction</h2>
    <p>Seaborne Care respects your privacy. This policy describes how information may be handled when you interact with our website.</p>
    <h2>2. Information You Share</h2>
    <p>If you contact us by phone or email, you may voluntarily provide information such as your name, email address, phone number, and message.</p>
    <h2>3. Use of Information</h2>
    <p>Information shared with us may be used to respond to enquiries, communicate about our activities, and coordinate relevant requests.</p>
    <h2>4. External Services</h2>
    <p>Our website may use third-party services, including website hosting and externally hosted images. Such providers may process technical information according to their own policies.</p>
    <h2>5. Data Security</h2>
    <p>We aim to handle information responsibly, although no method of internet communication can be guaranteed completely secure.</p>
    <h2>6. Your Requests</h2>
    <p>To ask about information you have shared with us, contact Care@seabornemcs.in.</p>
    <h2>7. Policy Updates</h2>
    <p>This policy may be updated as our website and activities evolve.</p>
    <h2>8. Contact</h2>
    <p>Email: <a href="mailto:Care@seabornemcs.in">Care@seabornemcs.in</a></p>
  </div>
</section>

<section id="terms" class="page">
  <div class="page-banner">
    <h1>Terms & Conditions</h1>
    <p>Guidelines for using the Seaborne Care website.</p>
  </div>
  <div class="container prose">
    <p><strong>Last Updated:</strong> 24 October 2026</p>
    <h2>1. Website Purpose</h2>
    <p>This website provides information about Seaborne Care, its objectives, and its community support activities.</p>
    <h2>2. Use of Content</h2>
    <p>Visitors should use the website lawfully and should not misuse its content, branding, or communication channels.</p>
    <h2>3. Activities and Availability</h2>
    <p>Activities, distribution events, participation opportunities, and available assistance may change depending on resources and circumstances. Website information does not guarantee any particular assistance or service.</p>
    <h2>4. Accuracy</h2>
    <p>We aim to provide useful and accurate information, but website content may occasionally require corrections or updates.</p>
    <h2>5. External Links</h2>
    <p>We are not responsible for the content or practices of independent third-party websites linked from our pages.</p>
    <h2>6. Changes</h2>
    <p>Website content and these terms may be updated from time to time.</p>
    <h2>7. Contact</h2>
    <p>For questions about these terms, email <a href="mailto:Care@seabornemcs.in">Care@seabornemcs.in</a>.</p>
  </div>
</section>

</main>

<div class="cta">
  <h2>Every Act of Care Matters</h2>
  <p>Join the spirit of kindness and help create a world where happiness is shared and compassion has no boundaries.</p>
  <a href="#contact" class="btn">Connect With Seaborne Care</a>
</div>

<footer>
  <div class="footer-grid">
    <div>
      <h3>♥ Seaborne Care</h3>
      <p>Spreading kindness, sharing happiness, and supporting communities through compassion and meaningful action.</p>
    </div>
    <div>
      <h3>Quick Links</h3>
      <a href="#home">Home</a>
      <a href="#about">About Us</a>
      <a href="#mission">Our Mission</a>
      <a href="#vision">Our Vision</a>
      <a href="#faq">FAQ</a>
    </div>
    <div>
      <h3>Information</h3>
      <a href="#contact">Contact Us</a>
      <a href="#privacy">Privacy Policy</a>
      <a href="#terms">Terms & Conditions</a>
      <a href="mailto:Care@seabornemcs.in">Care@seabornemcs.in</a>
      <a href="tel:+919650285586">+91 9650285586</a>
    </div>
  </div>
  <div class="copyright">
    © <span id="year"></span> Seaborne Care. All Rights Reserved.
    <br>Made with ♥ for Humanity.
  </div>
</footer>

<script>
const pages = document.querySelectorAll(".page");
const links = document.querySelectorAll('a[href^="#"]');
const nav = document.getElementById("nav");
const menuBtn = document.getElementById("menuBtn");

function showPage() {
  const valid = [...pages].map(p => p.id);
  const requested = location.hash.substring(1);
  const id = valid.includes(requested) ? requested : "home";

  pages.forEach(page => {
    page.classList.toggle("active", page.id === id);
  });

  document.querySelectorAll("nav a").forEach(link => {
    link.classList.toggle("active", link.getAttribute("href") === "#" + id);
  });

  nav.classList.remove("open");
  menuBtn.setAttribute("aria-expanded", "false");
  window.scrollTo({top:0,behavior:"instant"});
  document.title = (id === "home" ? "Seaborne Care" :
    id.charAt(0).toUpperCase() + id.slice(1).replace("-"," ") +
    " | Seaborne Care");
}

menuBtn.addEventListener("click", () => {
  const isOpen = nav.classList.toggle("open");
  menuBtn.setAttribute("aria-expanded", String(isOpen));
});

window.addEventListener("hashchange", showPage);
document.getElementById("year").textContent = new Date().getFullYear();
showPage();
</script>
</body>
</html>
