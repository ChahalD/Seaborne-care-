<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>World Cruise Finder</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <header>
        <h1>🚢 World Cruise Tracker</h1>
        <p>Search any cruise across the world to check its current location</p>
    </header>

    <main>
        <div class="search-container">
            <input type="text" id="searchInput" placeholder="Search cruise name (e.g., Royal Caribbean, Titanic)...">
            <button id="searchBtn">Search</button>
        </div>

        <div id="cruiseList" class="cruise-grid">
            <!-- Cruise cards will be dynamically loaded here -->
        </div>
    </main>

    <script src="script.js"></script>
</body>
</html>
