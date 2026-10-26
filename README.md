<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GlobalVisa Portal - Official Visa Processing & Assistance</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts (Poppins) -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            font-family: 'Poppins', sans-serif;
        }

        body {
            background: radial-gradient(circle at top right, #1e293b, #0f172a, #020617);
            color: #f8fafc;
            min-height: 100vh;
        }

        /* Glassmorphism styling */
        .glass-card {
            background: rgba(30, 41, 59, 0.75);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.5);
        }

        .glass-header {
            background: rgba(15, 23, 42, 0.85);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.08);
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #0f172a;
        }
        ::-webkit-scrollbar-thumb {
            background: #334155;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #475569;
        }

        /* Modal Animation */
        @keyframes modalFadeIn {
            from { opacity: 0; transform: scale(0.95) translateY(10px); }
            to { opacity: 1; transform: scale(1) translateY(0); }
        }

        .animate-modal {
            animation: modalFadeIn 0.3s cubic-bezier(0.16, 1, 0.3, 1) forwards;
        }

        .gradient-text {
            background: linear-gradient(135deg, #38bdf8, #818cf8);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .pulse-badge {
            box-shadow: 0 0 0 0 rgba(16, 185, 129, 0.4);
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { box-shadow: 0 0 0 0 rgba(16, 185, 129, 0.4); }
            70% { box-shadow: 0 0 0 10px rgba(16, 185, 129, 0); }
            100% { box-shadow: 0 0 0 0 rgba(16, 185, 129, 0); }
        }
    </style>
</head>
<body class="flex flex-col min-h-screen antialiased selection:bg-sky-500 selection:text-white">

    <!-- Header Navigation -->
    <header class="glass-header sticky top-0 z-40 w-full px-4 sm:px-8 py-3.5 flex flex-wrap justify-between items-center gap-4">
        <div class="flex items-center gap-3">
            <div class="bg-gradient-to-tr from-sky-500 to-indigo-600 p-2.5 rounded-xl shadow-lg shadow-sky-500/20">
                <i class="fa-solid fa-passport text-white text-xl"></i>
            </div>
            <div>
                <span class="text-xl font-bold tracking-tight text-white flex items-center gap-1.5">
                    GlobalVisa <span class="text-sky-400 font-light">Portal</span>
                </span>
                <span class="text-[10px] uppercase tracking-widest text-slate-400 font-semibold block">Official Application Portal</span>
            </div>
        </div>

        <!-- Success Rate Badge in Header -->
        <div class="flex items-center gap-2 bg-emerald-500/10 border border-emerald-500/30 px-4 py-1.5 rounded-full pulse-badge">
            <span class="relative flex h-2.5 w-2.5">
                <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-emerald-400 opacity-75"></span>
                <span class="relative inline-flex rounded-full h-2.5 w-2.5 bg-emerald-500"></span>
            </span>
            <p class="text-xs font-semibold text-emerald-400 flex items-center gap-1">
                <i class="fa-solid fa-circle-check text-emerald-400"></i>
                Success Rate: <span class="text-white font-bold">88%</span>
            </p>
        </div>
    </header>

    <!-- Main Content Section -->
    <main class="flex-1 flex items-center justify-center p-4 sm:p-6 lg:p-8">
        <div class="w-full max-w-xl">
            
            <!-- Title and Subtitle -->
            <div class="text-center mb-8">
                <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-sky-500/10 border border-sky-500/20 text-sky-400 text-xs font-medium mb-3">
                    <i class="fa-solid fa-shield-halved text-sky-400"></i> Verified Application Process
                </div>
                <h1 class="text-3xl sm:text-4xl font-extrabold tracking-tight text-white mb-3">
                    Visa Pre-Screening & <span class="gradient-text">Application</span>
                </h1>
                <p class="text-slate-400 text-sm sm:text-base leading-relaxed max-w-md mx-auto">
                    Select your required visa category and destination to proceed with your application.
                </p>
            </div>

            <!-- Selection Form Card -->
            <div class="glass-card rounded-2xl p-6 sm:p-8 border border-slate-700/50 relative overflow-hidden">
                <div class="absolute -top-24 -right-24 w-48 h-48 bg-sky-500/10 rounded-full blur-3xl pointer-events-none"></div>
                
                <form id="visaSelectionForm" onsubmit="event.preventDefault();">
                    
                    <!-- Dropdown 1: Select Visa Type -->
                    <div class="space-y-2 mb-6">
                        <label for="visaType" class="block text-xs font-semibold uppercase tracking-wider text-slate-300 flex items-center justify-between">
                            <span>1. Select Visa Type <span class="text-rose-400">*</span></span>
                            <span class="text-[10px] text-slate-400 lowercase font-normal">(required)</span>
                        </label>
                        <div class="relative">
                            <select id="visaType" onchange="handleVisaChange()" class="w-full bg-slate-900/90 border border-slate-700 rounded-xl px-4 py-3.5 text-slate-100 text-sm focus:ring-2 focus:ring-sky-500 focus:border-sky-500 outline-none transition appearance-none cursor-pointer">
                                <option value="" disabled selected>-- Select Visa Category --</option>
                                <option value="Schengen Visa">Schengen Visa (Europe Tourism / Business / Work)</option>
                                <option value="C1/D Visa (US)">C1/D Visa (US Maritime Crew & Transit)</option>
                            </select>
                            <div class="pointer-events-none absolute inset-y-0 right-0 flex items-center px-4 text-slate-400">
                                <i class="fa-solid fa-chevron-down text-xs"></i>
                            </div>
                        </div>
                    </div>

                    <!-- Dropdown 2: Select Destination (Dynamically Populated) -->
                    <div id="countryGroup" class="space-y-2 mb-8 hidden transition-all duration-300">
                        <label for="countrySelect" id="countryLabel" class="block text-xs font-semibold uppercase tracking-wider text-slate-300">
                            2. Select Destination Country / Port <span class="text-rose-400">*</span>
                        </label>
                        <div class="relative">
                            <select id="countrySelect" onchange="handleCountryChange()" class="w-full bg-slate-900/90 border border-slate-700 rounded-xl px-4 py-3.5 text-slate-100 text-sm focus:ring-2 focus:ring-sky-500 focus:border-sky-500 outline-none transition appearance-none cursor-pointer">
                                <option value="" disabled selected>-- Select Destination --</option>
                            </select>
                            <div class="pointer-events-none absolute inset-y-0 right-0 flex items-center px-4 text-slate-400">
                                <i class="fa-solid fa-chevron-down text-xs"></i>
                            </div>
                        </div>
                    </div>

                    <!-- Proceed Button -->
                    <div id="proceedContainer" class="hidden transition-all duration-300">
                        <button type="button" onclick="openDetailsModal()" class="w-full bg-gradient-to-r from-sky-500 to-blue-600 hover:from-sky-400 hover:to-blue-500 text-white font-semibold py-4 px-6 rounded-xl shadow-lg shadow-sky-500/25 transition transform active:scale-[0.98] flex items-center justify-center gap-2 group">
                            <span>Proceed Now</span>
                            <i class="fa-solid fa-arrow-right text-sm transition-transform group-hover:translate-x-1"></i>
                        </button>
                    </div>

                </form>

                <!-- Information Badges -->
                <div class="mt-8 pt-6 border-t border-slate-700/50 grid grid-cols-2 gap-4 text-center">
                    <div class="bg-slate-900/50 p-3 rounded-xl border border-slate-800">
                        <p class="text-xs text-slate-400 mb-0.5"><i class="fa-solid fa-bolt text-amber-400 me-1"></i> Fast Track</p>
                        <p class="text-sm font-bold text-slate-200">Express Processing</p>
                    </div>
                    <div class="bg-slate-900/50 p-3 rounded-xl border border-slate-800">
                        <p class="text-xs text-slate-400 mb-0.5"><i class="fa-solid fa-lock text-sky-400 me-1"></i> Security</p>
                        <p class="text-sm font-bold text-slate-200">Cashfree Encrypted</p>
                    </div>
                </div>

            </div>

            <p class="text-center text-xs text-slate-500 mt-6 flex items-center justify-center gap-2">
                <i class="fa-solid fa-shield text-slate-600"></i> Encrypted Candidate Information System &bull; Fast-Track Application Desk
            </p>

        </div>
    </main>

    <!-- MODAL 1: Candidate Details Form -->
    <div id="candidateModal" class="fixed inset-0 z-50 flex items-center justify-center p-4 bg-slate-950/80 backdrop-blur-md hidden transition-opacity">
        <div class="glass-card w-full max-w-lg rounded-2xl border border-slate-700/80 overflow-hidden shadow-2xl animate-modal relative max-h-[90vh] flex flex-col">
            
            <!-- Modal 1 Header -->
            <div class="px-6 py-4 border-b border-slate-700/60 flex items-center justify-between bg-slate-900/80 sticky top-0 z-10">
                <div class="flex items-center gap-2.5">
                    <div class="w-8 h-8 rounded-lg bg-sky-500/20 border border-sky-500/30 flex items-center justify-center text-sky-400">
                        <i class="fa-solid fa-user-pen text-sm"></i>
                    </div>
                    <div>
                        <h3 class="text-base font-bold text-white">Candidate Details Form</h3>
                        <p class="text-[11px] text-slate-400">Step 1 of 2: Basic Passport Information</p>
                    </div>
                </div>
                <button type="button" onclick="closeDetailsModal()" class="w-8 h-8 rounded-lg bg-slate-800 hover:bg-slate-700 text-slate-400 hover:text-white transition flex items-center justify-center">
                    <i class="fa-solid fa-xmark text-lg"></i>
                </button>
            </div>

            <!-- Modal 1 Body -->
            <div class="p-6 overflow-y-auto space-y-5">
                
                <!-- Selection Summary Box -->
                <div class="bg-sky-950/40 border border-sky-500/30 rounded-xl p-3.5 text-xs text-sky-200 flex items-start gap-3">
                    <i class="fa-solid fa-circle-info text-sky-400 text-sm mt-0.5"></i>
                    <div class="space-y-0.5">
                        <p class="font-medium text-slate-300">Selected Application Route:</p>
                        <p id="summaryText" class="text-sky-300 font-bold text-sm"></p>
                    </div>
                </div>

                <!-- Form -->
                <form id="candidateForm" onsubmit="handleFormSubmission(event)" class="space-y-4">
                    
                    <!-- Full Name -->
                    <div>
                        <label for="fullName" class="block text-xs font-semibold text-slate-300 mb-1.5">
                            Full Name (As per Passport) <span class="text-rose-400">*</span>
                        </label>
                        <div class="relative">
                            <span class="absolute inset-y-0 left-0 pl-3.5 flex items-center pointer-events-none text-slate-500 text-xs">
                                <i class="fa-solid fa-user"></i>
                            </span>
                            <input type="text" id="fullName" required placeholder="John Doe" class="w-full bg-slate-900 border border-slate-700/80 rounded-xl pl-9 pr-4 py-2.5 text-sm text-white placeholder-slate-500 focus:ring-2 focus:ring-sky-500 focus:border-sky-500 outline-none transition">
                        </div>
                    </div>

                    <!-- Contact Number & Email -->
                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                        <!-- Contact Number -->
                        <div>
                            <label for="contactNumber" class="block text-xs font-semibold text-slate-300 mb-1.5">
                                Contact Number <span class="text-rose-400">*</span>
                            </label>
                            <div class="relative">
                                <span class="absolute inset-y-0 left-0 pl-3.5 flex items-center pointer-events-none text-slate-500 text-xs">
                                    <i class="fa-solid fa-phone"></i>
                                </span>
                                <input type="tel" id="contactNumber" required pattern="[0-9]{10}" placeholder="10-digit mobile number" class="w-full bg-slate-900 border border-slate-700/80 rounded-xl pl-9 pr-4 py-2.5 text-sm text-white placeholder-slate-500 focus:ring-2 focus:ring-sky-500 focus:border-sky-500 outline-none transition">
                            </div>
                        </div>

                        <!-- Email Address -->
                        <div>
                            <label for="emailAddress" class="block text-xs font-semibold text-slate-300 mb-1.5">
                                Email Address <span class="text-rose-400">*</span>
                            </label>
                            <div class="relative">
                                <span class="absolute inset-y-0 left-0 pl-3.5 flex items-center pointer-events-none text-slate-500 text-xs">
                                    <i class="fa-solid fa-envelope"></i>
                                </span>
                                <input type="email" id="emailAddress" required placeholder="john.doe@example.com" class="w-full bg-slate-900 border border-slate-700/80 rounded-xl pl-9 pr-4 py-2.5 text-sm text-white placeholder-slate-500 focus:ring-2 focus:ring-sky-500 focus:border-sky-500 outline-none transition">
                            </div>
                        </div>
                    </div>

                    <!-- Passport Number & Intended Travel Date -->
                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                        <!-- Passport Number -->
                        <div>
                            <label for="passportNum" class="block text-xs font-semibold text-slate-300 mb-1.5">
                                Passport Number <span class="text-rose-400">*</span>
                            </label>
                            <div class="relative">
                                <span class="absolute inset-y-0 left-0 pl-3.5 flex items-center pointer-events-none text-slate-500 text-xs">
                                    <i class="fa-solid fa-id-card"></i>
                                </span>
                                <input type="text" id="passportNum" required placeholder="A1234567" pattern="[A-Za-z0-9]{6,10}" class="w-full bg-slate-900 border border-slate-700/80 rounded-xl pl-9 pr-4 py-2.5 text-sm text-white placeholder-slate-500 focus:ring-2 focus:ring-sky-500 focus:border-sky-500 outline-none transition uppercase">
                            </div>
                        </div>

                        <!-- Intended Travel Date -->
                        <div>
                            <label for="travelDate" class="block text-xs font-semibold text-slate-300 mb-1.5">
                                Target Travel Date <span class="text-rose-400">*</span>
                            </label>
                            <div class="relative">
                                <input type="date" id="travelDate" required class="w-full bg-slate-900 border border-slate-700/80 rounded-xl px-3.5 py-2.5 text-sm text-white focus:ring-2 focus:ring-sky-500 focus:border-sky-500 outline-none transition cursor-pointer">
                            </div>
                        </div>
                    </div>

                    <!-- Additional Travel Notes -->
                    <div>
                        <label for="travelPurpose" class="block text-xs font-semibold text-slate-300 mb-1.5">
                            Purpose of Travel / Additional Notes <span class="text-slate-500 font-normal">(Optional)</span>
                        </label>
                        <textarea id="travelPurpose" rows="2" placeholder="e.g., Seaman Crew Assignment, Business Visit..." class="w-full bg-slate-900 border border-slate-700/80 rounded-xl p-3 text-sm text-white placeholder-slate-500 focus:ring-2 focus:ring-sky-500 focus:border-sky-500 outline-none transition resize-none"></textarea>
                    </div>

                    <!-- Certification Checkbox -->
                    <div class="flex items-start gap-2.5 pt-1">
                        <input type="checkbox" id="termsCheck" required class="mt-1 rounded bg-slate-900 border-slate-700 text-sky-500 focus:ring-sky-500 focus:ring-offset-slate-900">
                        <label for="termsCheck" class="text-xs text-slate-400 leading-snug">
                            I confirm that the provided information accurately matches my legal passport documents.
                        </label>
                    </div>

                    <!-- Form Submit Button -->
                    <div class="pt-2">
                        <button type="submit" class="w-full bg-gradient-to-r from-sky-500 to-blue-600 hover:from-sky-400 hover:to-blue-500 text-white font-bold py-3.5 px-6 rounded-xl shadow-lg shadow-sky-500/25 transition transform active:scale-[0.98] flex items-center justify-center gap-2">
                            <span>Submit & Review Disclaimer</span>
                            <i class="fa-solid fa-arrow-right text-xs"></i>
                        </button>
                    </div>

                </form>
            </div>

            <!-- Modal 1 Footer -->
            <div class="bg-slate-900/90 px-6 py-3 border-t border-slate-800 text-center text-[11px] text-slate-400 flex items-center justify-center gap-2">
                <i class="fa-solid fa-lock text-sky-400"></i> Encrypted & Secure SSL Transmission
            </div>

        </div>
    </div>

    <!-- MODAL 2: Official Disclaimer & Counselor Warning Popup -->
    <div id="disclaimerModal" class="fixed inset-0 z-50 flex items-center justify-center p-4 bg-slate-950/85 backdrop-blur-md hidden transition-opacity">
        <div class="glass-card w-full max-w-md rounded-2xl border border-amber-500/30 overflow-hidden shadow-2xl animate-modal relative flex flex-col">
            
            <!-- Warning Header Glow -->
            <div class="bg-amber-500/10 border-b border-amber-500/20 px-6 py-5 text-center relative">
                <div class="w-14 h-14 rounded-full bg-amber-500/20 border border-amber-500/40 flex items-center justify-center mx-auto mb-3 text-amber-400 text-2xl shadow-lg shadow-amber-500/10">
                    <i class="fa-solid fa-triangle-exclamation"></i>
                </div>
                <h3 class="text-lg font-bold text-white tracking-wide">Important Visa Notice</h3>
                <p class="text-xs text-amber-300/80 font-medium mt-0.5">Please read carefully before proceeding</p>
            </div>

            <!-- Modal 2 Content Note -->
            <div class="p-6 text-center space-y-4">
                
                <div class="bg-slate-900/90 border border-slate-800 rounded-xl p-4 text-left space-y-2">
                    <div class="flex items-start gap-2.5 text-amber-400 font-semibold text-xs uppercase tracking-wider">
                        <i class="fa-solid fa-shield-cat text-sm mt-0.5"></i>
                        <span>Approval Authority Disclaimer</span>
                    </div>
                    <p class="text-slate-300 text-xs sm:text-sm leading-relaxed">
                        <strong class="text-amber-300">Note:</strong> Final Visa approval is strictly subject to decision and authorization by the embassy, consulate, or official visa counselor.
                    </p>
                </div>

                <p class="text-xs text-slate-400 leading-normal">
                    By clicking <span class="text-slate-200 font-medium">"Continue to Payment"</span>, you acknowledge that our portal assists with pre-screening, documentation structure, and processing, while final issuance authority remains with government counselors.
                </p>

            </div>

            <!-- Modal 2 Action Button -->
            <div class="p-6 pt-0 space-y-3">
                <button type="button" id="continuePayBtn" onclick="redirectToCashfree()" class="w-full bg-gradient-to-r from-emerald-500 to-teal-600 hover:from-emerald-400 hover:to-teal-500 text-white font-bold py-3.5 px-6 rounded-xl shadow-lg shadow-emerald-500/25 transition transform active:scale-[0.98] flex items-center justify-center gap-2 group">
                    <span>Continue to Payment</span>
                    <i class="fa-solid fa-arrow-right text-xs transition-transform group-hover:translate-x-1"></i>
                </button>

                <button type="button" onclick="closeDisclaimerModal()" class="w-full text-xs text-slate-400 hover:text-slate-200 py-1 font-medium transition">
                    &larr; Back to Candidate Details
                </button>
            </div>

            <!-- Modal 2 Footer -->
            <div class="bg-slate-900/90 px-6 py-3 border-t border-slate-800 text-center text-[11px] text-slate-400 flex items-center justify-center gap-2">
                <i class="fa-solid fa-shield-halved text-emerald-400"></i> Redirecting to Official Cashfree Gateway
            </div>

        </div>
    </div>

    <!-- JavaScript Application Logic -->
    <script>
        // 27 Schengen Countries List
        const schengenCountries = [
            "Austria", "Belgium", "Croatia", "Czech Republic", "Denmark", 
            "Estonia", "Finland", "France", "Germany", "Greece", 
            "Hungary", "Iceland", "Italy", "Latvia", "Liechtenstein", 
            "Lithuania", "Luxembourg", "Malta", "Netherlands", "Norway", 
            "Poland", "Portugal", "Slovakia", "Slovenia", "Spain", 
            "Sweden", "Switzerland"
        ];

        // C1/D US Maritime Entry Ports List
        const usC1DDestinations = [
            "United States - Primary Entry Port",
            "Port of Miami (Florida, USA)",
            "Port of New York & New Jersey (USA)",
            "Port of Los Angeles (California, USA)",
            "Port of Seattle (Washington, USA)",
            "Port of Galveston (Texas, USA)",
            "Port Everglades (Florida, USA)",
            "US Virgin Islands Maritime Port",
            "Puerto Rico (US Territory Port)",
            "Hawaii Maritime Ports (USA)"
        ];

        // Set minimum travel date selector to today
        document.addEventListener("DOMContentLoaded", () => {
            const today = new Date().toISOString().split('T')[0];
            const travelDateInput = document.getElementById("travelDate");
            if (travelDateInput) {
                travelDateInput.setAttribute('min', today);
            }
        });

        // Handle Visa Category Dropdown Change
        function handleVisaChange() {
            const visaType = document.getElementById("visaType").value;
            const countryGroup = document.getElementById("countryGroup");
            const countrySelect = document.getElementById("countrySelect");
            const countryLabel = document.getElementById("countryLabel");
            const proceedContainer = document.getElementById("proceedContainer");

            // Reset sub-options and hide proceed button
            countrySelect.innerHTML = '<option value="" disabled selected>-- Select Destination --</option>';
            proceedContainer.classList.add("hidden");

            if (visaType === "Schengen Visa") {
                countryLabel.innerHTML = '2. Select Schengen Country <span class="text-rose-400">*</span>';
                schengenCountries.forEach(country => {
                    let option = document.createElement("option");
                    option.value = country;
                    option.textContent = country;
                    countrySelect.appendChild(option);
                });
                countryGroup.classList.remove("hidden");
            } else if (visaType === "C1/D Visa (US)") {
                countryLabel.innerHTML = '2. Select US Port / Destination <span class="text-rose-400">*</span>';
                usC1DDestinations.forEach(destination => {
                    let option = document.createElement("option");
                    option.value = destination;
                    option.textContent = destination;
                    countrySelect.appendChild(option);
                });
                countryGroup.classList.remove("hidden");
            }
        }

        // Handle Destination Option Selection
        function handleCountryChange() {
            const countrySelect = document.getElementById("countrySelect").value;
            const proceedContainer = document.getElementById("proceedContainer");
            
            if (countrySelect) {
                proceedContainer.classList.remove("hidden");
            }
        }

        // Open Modal 1 (Details Form)
        function openDetailsModal() {
            const visaType = document.getElementById("visaType").value;
            const selectedCountry = document.getElementById("countrySelect").value;
            const summaryText = document.getElementById("summaryText");

            summaryText.innerHTML = `${visaType} &bull; <span class="text-white">${selectedCountry}</span>`;
            
            document.getElementById("candidateModal").classList.remove("hidden");
        }

        // Close Modal 1
        function closeDetailsModal() {
            document.getElementById("candidateModal").classList.add("hidden");
        }

        // Handle Submission of Form 1 -> Opens Modal 2 (Disclaimer)
        function handleFormSubmission(event) {
            event.preventDefault(); // Prevent standard page reload

            // Close Candidate Form Modal
            closeDetailsModal();

            // Open Disclaimer / Counselor Warning Modal
            document.getElementById("disclaimerModal").classList.remove("hidden");
        }

        // Close Modal 2
        function closeDisclaimerModal() {
            document.getElementById("disclaimerModal").classList.add("hidden");
            // Re-open Form 1 in case candidate wants to adjust details
            document.getElementById("candidateModal").classList.remove("hidden");
        }

        // Final Action: Continue Button Click -> Redirects to Cashfree Gateway
        function redirectToCashfree() {
            const continuePayBtn = document.getElementById("continuePayBtn");
            
            // Show loading animation
            continuePayBtn.disabled = true;
            continuePayBtn.innerHTML = `<i class="fa-solid fa-spinner fa-spin me-2"></i> Connecting to Cashfree...`;

            // Cashfree Form Gateway URL
            const paymentUrl = "https://payments.cashfree.com/forms/visaprep";

            // Redirect candidate
            setTimeout(() => {
                window.location.href = paymentUrl;
            }, 600);
        }
    </script>
</body>
</html>
