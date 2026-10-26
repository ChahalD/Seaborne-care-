
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Seaborne International MCS - Cruise Ship Visa Preparation</title>
    <!-- Google Fonts & FontAwesome for Icons -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        :root {
            --primary: #004d7a;
            --secondary: #008793;
            --accent: #ff6b6b;
            --dark: #1a1a1a;
            --light: #f4f7f6;
            --white: #ffffff;
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
            scroll-behavior: smooth;
        }

        body {
            background-color: var(--light);
            color: var(--dark);
            line-height: 1.6;
        }

        /* Header & Navbar */
        header {
            background: var(--white);
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 1000;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 15px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 22px;
            font-weight: 700;
            color: var(--primary);
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo i {
            color: var(--secondary);
        }

        .nav-links {
            list-style: none;
            display: flex;
            gap: 25px;
            align-items: center;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 500;
            transition: var(--transition);
        }

        .nav-links a:hover {
            color: var(--secondary);
        }

        .cta-btn {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: var(--white) !important;
            padding: 10px 20px;
            border-radius: 5px;
            font-weight: 600;
            cursor: pointer;
            border: none;
            transition: var(--transition);
        }

        .cta-btn:hover {
            opacity: 0.9;
            transform: translateY(-2px);
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(0, 77, 122, 0.8), rgba(0, 135, 147, 0.8)), url('https://images.unsplash.com/photo-1548574505-5e239809ee19?auto=format&fit=crop&w=1920&q=80') no-repeat center center/cover;
            height: 90vh;
            display: flex;
            align-items: center;
            text-align: center;
            color: var(--white);
            padding: 0 20px;
            margin-top: 70px;
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
        }

        .hero h1 {
            font-size: 42px;
            margin-bottom: 20px;
            font-weight: 700;
        }

        .hero p {
            font-size: 18px;
            margin-bottom: 30px;
            opacity: 0.9;
        }

        /* Sections General Styling */
        section {
            padding: 80px 20px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            font-size: 32px;
            margin-bottom: 15px;
            color: var(--primary);
            font-weight: 700;
        }

        .section-subtitle {
            text-align: center;
            color: #666;
            margin-bottom: 50px;
            font-size: 16px;
        }

        /* About, Mission, Vision Cards */
        .about-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .card {
            background: var(--white);
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: var(--transition);
            border-top: 4px solid var(--secondary);
        }

        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(0,0,0,0.1);
        }

        .card i {
            font-size: 40px;
            color: var(--secondary);
            margin-bottom: 20px;
        }

        .card h3 {
            font-size: 22px;
            margin-bottom: 15px;
            color: var(--primary);
        }

        /* FAQ Section */
        .faq-container {
            max-width: 800px;
            margin: 0 auto;
        }

        .faq-item {
            background: var(--white);
            margin-bottom: 15px;
            border-radius: 8px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.05);
            overflow: hidden;
        }

        .faq-question {
            padding: 20px;
            font-weight: 600;
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: var(--white);
            transition: var(--transition);
        }

        .faq-question:hover {
            color: var(--secondary);
        }

        .faq-answer {
            padding: 0 20px;
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease, padding 0.3s ease;
            color: #555;
        }

        .faq-item.active .faq-answer {
            padding: 0 20px 20px 20px;
            max-height: 200px;
        }

        .faq-item.active .faq-question i {
            transform: rotate(180deg);
        }

        /* Contact Section */
        .contact-box {
            background: var(--white);
            padding: 40px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            text-align: center;
            max-width: 600px;
            margin: 0 auto;
        }

        .contact-info {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-top: 20px;
            flex-wrap: wrap;
        }

        .contact-info div {
            display: flex;
            align-items: center;
            gap: 10px;
            font-weight: 500;
        }

        .contact-info i {
            color: var(--secondary);
            font-size: 20px;
        }

        /* Footer & Policies Links */
        footer {
            background: var(--dark);
            color: var(--white);
            padding: 40px 20px 20px;
            text-align: center;
        }

        .footer-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-bottom: 20px;
            flex-wrap: wrap;
        }

        .footer-links a {
            color: #aaa;
            text-decoration: none;
            font-size: 14px;
            transition: var(--transition);
        }

        .footer-links a:hover {
            color: var(--white);
        }

        .copyright {
            color: #777;
            font-size: 13px;
            border-top: 1px solid #333;
            padding-top: 20px;
            margin-top: 20px;
        }

        /* Modal / Notice Page Styling */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.7);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 2000;
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
        }

        .modal-overlay.active {
            opacity: 1;
            visibility: visible;
        }

        .modal-content {
            background: var(--white);
            padding: 40px;
            border-radius: 12px;
            max-width: 550px;
            width: 90%;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
            transform: translateY(-20px);
            transition: transform 0.3s ease;
        }

        .modal-overlay.active .modal-content {
            transform: translateY(0);
        }

        .modal-content h2 {
            color: var(--primary);
            margin-bottom: 20px;
        }

        .notice-box {
            background: #fff3cd;
            border: 1px solid #ffeeba;
            color: #856404;
            padding: 15px;
            border-radius: 6px;
            text-align: left;
            font-size: 14px;
            margin-bottom: 25px;
        }

        .modal-buttons {
            display: flex;
            gap: 15px;
            justify-content: center;
        }

        .btn-secondary {
            background: #ccc;
            color: var(--dark);
            padding: 10px 20px;
            border-radius: 5px;
            border: none;
            cursor: pointer;
            font-weight: 600;
        }

        .btn-secondary:hover {
            background: #b3b3b3;
        }

        /* Policy Section (Simple toggle or separate views) */
        .policy-section {
            background: var(--white);
            padding: 40px;
            border-radius: 10px;
            margin-top: 20px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            display: none;
        }

        .policy-section.active {
            display: block;
        }

        .policy-section h2 {
            color: var(--primary);
            margin-bottom: 15px;
        }

        .policy-section p, .policy-section ul {
            margin-bottom: 15px;
            color: #555;
            text-align: left;
        }

        .policy-section ul {
            padding-left: 20px;
        }

        @media(max-width: 768px) {
            .nav-links {
                display: none; /* Mobile menu can be added if needed */
            }
            .hero h1 {
                font-size: 30px;
            }
        }
    </style>
</head>
<body>

    <!-- Header & Navigation -->
    <header>
        <div class="nav-container">
            <a href="#" class="logo"><i class="fa-solid fa-ship"></i> Seaborne MCS</a>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About Us</a></li>
                <li><a href="#faq">FAQ</a></li>
                <li><a href="#contact">Contact Us</a></li>
                <li><button class="cta-btn" onclick="openNoticeModal()">Prepare Now</button></li>
            </ul>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>Schengen & U.S. C1D Visa Preparation for Cruise Ship Aspirants</h1>
            <p>Turn your dream of working on international cruise lines into reality with professional document readiness and interview preparation.</p>
            <button class="cta-btn" style="font-size: 18px; padding: 12px 30px;" onclick="openNoticeModal()">Prepare Now</button>
        </div>
    </section>

    <!-- About Us, Mission, Vision Section -->
    <section id="about">
        <h2 class="section-title">Who We Are</h2>
        <p class="section-subtitle">Empowering candidates with valid documentation to step aboard international cruise ships.</p>
        
        <div class="about-grid">
            <div class="card">
                <i class="fa-solid fa-users-viewfinder"></i>
                <h3>About Us</h3>
                <p><strong>Seaborne International MCS</strong> specializes in guiding candidates who possess valid all documents to successfully clear their Schengen and U.S. C1D visa processes required for top global cruise lines.</p>
            </div>
            <div class="card">
                <i class="fa-solid fa-bullseye"></i>
                <h3>Our Mission</h3>
                <p>To provide accurate, transparent, and structured visa preparation support, ensuring zero errors during consular interviews for dedicated cruise ship job seekers.</p>
            </div>
            <div class="card">
                <i class="fa-solid fa-eye"></i>
                <h3>Our Vision</h3>
                <p>To become the world's most trusted maritime visa preparation partner, bridging the gap between qualified candidates and global cruise career opportunities.</p>
            </div>
        </div>
    </section>

    <!-- FAQ Section -->
    <section id="faq">
        <h2 class="section-title">Frequently Asked Questions</h2>
        <p class="section-subtitle">Got questions about your Schengen or U.S. C1D visa? Find answers here.</p>
        
        <div class="faq-container">
            <div class="faq-item">
                <div class="faq-question" onclick="toggleFaq(this)">
                    <span>Who is eligible for your visa preparation service?</span>
                    <i class="fa-solid fa-chevron-down"></i>
                </div>
                <div class="faq-answer">
                    <p>Candidates who already have all their valid documents (passport, contract, CDC, STCW certificates, etc.) and are preparing for Schengen or U.S. C1D visas for cruise ship jobs are eligible.</p>
                </div>
            </div>

            <div class="faq-item">
                <div class="faq-question" onclick="toggleFaq(this)">
                    <span>Do you guarantee visa approval?</span>
                    <p></p>
                    <i class="fa-solid fa-chevron-down"></i>
                </div>
                <div class="faq-answer">
                    <p>Visa approval is solely at the discretion of the respective Embassy or Consulate officers. We provide expert preparation, interview grooming, and application file review to maximize your success chances.</p>
                </div>
            </div>

            <div class="faq-item">
                <div class="faq-question" onclick="toggleFaq(this)">
                    <span>How does the payment process work via Cashfree?</span>
                    <p></p>
                    <i class="fa-solid fa-chevron-down"></i>
                </div>
                <div class="faq-answer">
                    <p>Clicking "Prepare Now" leads you to our secure notice page. Upon confirmation, you will be redirected to our official Cashfree payment gateway link to complete your enrollment safely.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Us Section -->
    <section id="contact">
        <h2 class="section-title">Contact Us</h2>
        <p class="section-subtitle">Reach out to our team for any assistance or inquiries.</p>
        
        <div class="contact-box">
            <h3 style="color: var(--primary); margin-bottom: 15px;">Seaborne International MCS</h3>
            <p>Get in touch with us for your cruise visa preparation journey.</p>
            <div class="contact-info">
                <div><i class="fa-solid fa-envelope"></i> support@seaborne.com</div>
                <div><i class="fa-solid fa-phone"></i> +91 XXXXXXXXXX</div>
            </div>
        </div>
    </section>

    <!-- Policy Sections Container (Hidden by default, shown when clicked in footer) -->
    <section id="policy-container" style="display:none; max-width:800px;">
        <!-- Privacy Policy -->
        <div id="privacy-policy" class="policy-section">
            <h2>Privacy Policy</h2>
            <p>At Seaborne International MCS, we respect your privacy and are committed to protecting your personal data...</p>
            <p>We collect information only when necessary for visa preparation support and never share your details with third parties without your consent.</p>
            <button class="cta-btn" onclick="closePolicy()">Back to Home</button>
        </div>

        <!-- Terms & Conditions -->
        <div id="terms" class="policy-section">
            <h2>Terms & Conditions</h2>
            <p>By using our services and making payments via Cashfree, you agree to our terms of service...</p>
            <p>We act as a guidance and preparation partner. Final visa issuance decisions rest entirely with the respective embassies.</p>
            <button class="cta-btn" onclick="closePolicy()">Back to Home</button>
        </div>

        <!-- Refund Policy -->
        <div id="refund-policy" class="policy-section">
            <h2>Refund Policy</h2>
            <p>Our preparation fees cover professional consultation, document structuring, and mock interview grooming.</p>
            <p>Fees once paid through our official Cashfree link are generally non-refundable once the preparation sessions have commenced.</p>
            <button class="cta-btn" onclick="closePolicy()">Back to Home</button>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-links">
            <a href="#home">Home</a>
            <a href="#about">About Us</a>
            <a href="#faq">FAQ</a>
            <a href="#contact">Contact Us</a>
            <a href="#" onclick="showPolicy('privacy-policy')">Privacy Policy</a>
            <a href="#" onclick="showPolicy('terms')">Terms & Conditions</a>
            <a href="#" onclick="showPolicy('refund-policy')">Refund Policy</a>
        </div>
        <p>&copy; 2026 Seaborne International MCS. All Rights Reserved.</p>
    </footer>

    <!-- Notice Modal / Page (As requested) -->
    <div id="noticeModal" class="modal-overlay">
        <div class="modal-content">
            <h2>Important Notice</h2>
            <div class="notice-box">
                <p><strong>Please Note:</strong> You are about to proceed with the visa preparation service for Schengen & U.S. C1D Visas. Please ensure that you have <strong>valid all documents</strong> ready before proceeding to payment.</p>
            </div>
            <p style="margin-bottom: 20px; font-size: 14px; color: #555;">Clicking below will securely redirect you to our official payment partner (Cashfree).</p>
            <div class="modal-buttons">
                <button class="btn-secondary" onclick="closeNoticeModal()">Cancel</button>
                <button class="cta-btn" onclick="proceedToCashfree()">Prepare Now</button>
            </div>
        </div>
    </div>

    <!-- JavaScript functionality -->
    <script>
        // FAQ Toggle
        function toggleFaq(element) {
            const item = element.parentElement;
            item.classList.toggle('active');
        }

        // Modal Controls
        function openNoticeModal() {
            document.getElementById('noticeModal').classList.add('active');
        }

        function closeNoticeModal() {
            document.getElementById('noticeModal').classList.remove('active');
        }

        // Proceed to Cashfree Link
        function proceedToCashfree() {
            window.location.href = "https://payments.cashfree.com/forms/visaprep";
        }

        // Policy view handler
        function showPolicy(policyId) {
            // Hide main sections
            document.getElementById('home').style.display = 'none';
            document.getElementById('about').style.display = 'none';
            document.getElementById('faq').style.display = 'none';
            document.getElementById('contact').style.display = 'none';
            
            // Hide all policies first
            document.querySelectorAll('.policy-section').forEach(el => el.classList.remove('active'));
            
            // Show policy container and specific policy
            document.getElementById('policy-container').style.display = 'block';
            document.getElementById(policyId).classList.add('active');
            window.scrollTo({top: 0, behavior: 'smooth'});
        }

        function closePolicy() {
            document.getElementById('policy-container').style.display = 'none';
            document.getElementById('home').style.display = 'block';
            document.getElementById('about').style.display = 'block';
            document.getElementById('faq').style.display = 'block';
            document.getElementById('contact').style.display = 'block';
            window.scrollTo({top: 0, behavior: 'smooth'});
        }
    </script>
</body>
</html>
