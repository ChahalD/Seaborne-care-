<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Visa Application Portal</title>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background: linear-gradient(135deg, #0f172a, #1e293b);
            color: #f8fafc;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        /* Top Bar / Header */
        header {
            width: 100%;
            background: rgba(30, 41, 59, 0.8);
            backdrop-filter: blur(10px);
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: #38bdf8;
            letter-spacing: 1px;
        }

        /* Main Container */
        .container {
            max-width: 600px;
            width: 90%;
            margin: 4rem auto;
            background: rgba(30, 41, 59, 0.7);
            backdrop-filter: blur(16px);
            border-radius: 16px;
            padding: 2.5rem;
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4);
            text-align: center;
        }

        h2 {
            font-size: 1.8rem;
            margin-bottom: 0.5rem;
            color: #ffffff;
        }

        p.subtitle {
            color: #94a3b8;
            font-size: 0.95rem;
            margin-bottom: 2rem;
        }

        /* Form Group Styles */
        .form-group {
            margin-bottom: 1.5rem;
            text-align: left;
        }

        label {
            display: block;
            font-size: 0.9rem;
            color: #cbd5e1;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }

        select {
            width: 100%;
            padding: 0.85rem 1rem;
            border-radius: 8px;
            background: #0f172a;
            border: 1px solid #334155;
            color: #f8fafc;
            font-size: 1rem;
            outline: none;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        select:focus {
            border-color: #38bdf8;
            box-shadow: 0 0 0 3px rgba(56, 189, 248, 0.2);
        }

        /* Hidden Class */
        .hidden {
            display: none;
        }

        /* Proceed Button */
        .btn-proceed {
            width: 100%;
            padding: 0.9rem;
            border-radius: 8px;
            border: none;
            background: linear-gradient(135deg, #0284c7, #2563eb);
            color: #ffffff;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-top: 1rem;
            box-shadow: 0 4px 14px rgba(37, 99, 235, 0.4);
        }

        .btn-proceed:hover {
            background: linear-gradient(135deg, #0369a1, #1d4ed8);
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(37, 99, 235, 0.6);
        }

        .btn-proceed:disabled {
            background: #475569;
            cursor: not-allowed;
            box-shadow: none;
            transform: none;
        }

        /* Response Card */
        .result-card {
            margin-top: 2rem;
            padding: 1.2rem;
            border-radius: 8px;
            background: rgba(16, 185, 129, 0.1);
            border: 1px solid #10b981;
            color: #34d399;
            font-size: 0.95rem;
        }
    </style>
</head>
<body>

    <!-- Header Navigation -->
    <header>
        <div class="logo">GlobalVisa Portal</div>
    </header>

    <!-- Main Content Container -->
    <div class="container">
        <h2>Visa Selection</h2>
        <p class="subtitle">Aap jis visa ke liye apply karna chahte hain, kripya select karein.</p>

        <!-- Step 1: Select Visa Type -->
        <div class="form-group">
            <label for="visaType">Select Visa Type</label>
            <select id="visaType" onchange="handleVisaChange()">
                <option value="" disabled selected>-- Select Visa Type --</option>
                <option value="Schengen Visa">Schengen Visa</option>
                <option value="C1D Visa">C1/D Visa (US)</option>
            </select>
        </div>

        <!-- Step 2: Select Country/Destination (Dynamically Populated) -->
        <div class="form-group hidden" id="countryGroup">
            <label for="countrySelect" id="countryLabel">Select Country / Destination</label>
            <select id="countrySelect" onchange="handleCountryChange()">
                <option value="" disabled selected>-- Select Option --</option>
            </select>
        </div>

        <!-- Step 3: Proceed Now Button -->
        <div id="proceedContainer" class="hidden">
            <button class="btn-proceed" onclick="proceedNext()">Proceed Now &rarr;</button>
        </div>

        <!-- Result / Notification Section -->
        <div id="resultCard" class="result-card hidden"></div>
    </div>

    <script>
        // Schengen Countries Data
        const schengenCountries = [
            "Austria", "Belgium", "Croatia", "Czech Republic", "Denmark", 
            "Estonia", "Finland", "France", "Germany", "Greece", 
            "Hungary", "Iceland", "Italy", "Latvia", "Liechtenstein", 
            "Lithuania", "Luxembourg", "Malta", "Netherlands", "Norway", 
            "Poland", "Portugal", "Slovakia", "Slovenia", "Spain", 
            "Sweden", "Switzerland"
        ];

        // US / C1D Port & Region Data
        const usC1DDestinations = [
            "United States - Primary Entry Port",
            "Port of Miami (Florida, USA)",
            "Port of New York & New Jersey (USA)",
            "Port of Los Angeles (California, USA)",
            "Port of Seattle (Washington, USA)",
            "Port of Galveston (Texas, USA)",
            "US Virgin Islands",
            "Puerto Rico (US Territory)",
            "Hawaii Ports (USA)"
        ];

        function handleVisaChange() {
            const visaType = document.getElementById("visaType").value;
            const countryGroup = document.getElementById("countryGroup");
            const countrySelect = document.getElementById("countrySelect");
            const countryLabel = document.getElementById("countryLabel");
            const proceedContainer = document.getElementById("proceedContainer");
            const resultCard = document.getElementById("resultCard");

            // Reset Sub-options & Output
            countrySelect.innerHTML = '<option value="" disabled selected>-- Select Option --</option>';
            proceedContainer.classList.add("hidden");
            resultCard.classList.add("hidden");

            if (visaType === "Schengen Visa") {
                countryLabel.textContent = "Select Schengen Country";
                schengenCountries.forEach(country => {
                    let option = document.createElement("option");
                    option.value = country;
                    option.textContent = country;
                    countrySelect.appendChild(option);
                });
                countryGroup.classList.remove("hidden");
            } else if (visaType === "C1D Visa") {
                countryLabel.textContent = "Select US Destination / Port";
                usC1DDestinations.forEach(destination => {
                    let option = document.createElement("option");
                    option.value = destination;
                    option.textContent = destination;
                    countrySelect.appendChild(option);
                });
                countryGroup.classList.remove("hidden");
            }
        }

        function handleCountryChange() {
            const countrySelect = document.getElementById("countrySelect").value;
            const proceedContainer = document.getElementById("proceedContainer");
            
            if (countrySelect) {
                proceedContainer.classList.remove("hidden");
            }
        }

        function proceedNext() {
            const visaType = document.getElementById("visaType").value;
            const selectedCountry = document.getElementById("countrySelect").value;
            const resultCard = document.getElementById("resultCard");

            resultCard.innerHTML = `<strong>Selection Successful!</strong><br> Aapne <strong>${visaType}</strong> ke andar <strong>${selectedCountry}</strong> select kiya hai. Aage ke process par redirect ho rahe hain...`;
            resultCard.classList.remove("hidden");
        }
    </script>
</body>
</html>
