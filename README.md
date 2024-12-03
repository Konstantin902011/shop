<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Online Shop</title>
    <style>
        /* General Styles */
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f9;
            color: #333;
        }

        header {
            background-color: #007B55; /* Green background */
            padding: 30px 0;
            text-align: center;
            color: white;
            font-size: 32px;
            font-weight: bold;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }

        .container {
            max-width: 1200px;
            margin: 40px auto;
            padding: 0 20px;
        }

        .product {
            background: #fff;
            border-radius: 10px;
            padding: 25px;
            margin-bottom: 30px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
            text-align: center;
        }

        .product h3 {
            font-size: 28px;
            color: #333;
            margin-bottom: 20px;
        }

        .product p {
            font-size: 18px;
            color: #555;
            margin-bottom: 20px;
        }

        .product .price-display {
            font-size: 22px;
            font-weight: bold;
            color: #4CAF50;
            margin-top: 20px;
        }

        .contact {
            margin-top: 20px;
        }

        .contact a {
            font-size: 18px;
            padding: 12px 30px;
            text-decoration: none;
            border-radius: 8px;
            display: inline-block;
            margin: 10px 10px;
            font-weight: bold;
            transition: background-color 0.3s ease;
        }

        .contact a.whatsapp {
            background-color: #25D366; /* WhatsApp Green */
            color: white;
        }

        .contact a.telegram {
            background-color: #0088CC; /* Telegram Blue */
            color: white;
        }

        .contact a:hover {
            opacity: 0.8;
        }

        button {
            padding: 12px 30px;
            font-size: 16px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        button:hover {
            background-color: #45a049;
        }

        .dropdown {
            margin-top: 15px;
        }

        select {
            padding: 12px;
            font-size: 16px;
            border-radius: 8px;
            border: 1px solid #ddd;
            width: 220px;
        }

        footer {
            margin-top: 60px;
            padding: 30px 20px;
            text-align: center;
            background-color: #333;
            color: white;
            font-size: 14px;
        }

        footer a {
            color: #4CAF50;
            text-decoration: none;
        }

        footer a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <header>Online Shop</header>

    <div class="container">
        <!-- Ranked Product -->
        <div class="product">
            <h3>Ranked</h3>
            <p>Reach Master! Select your current rank.</p>
            <div class="dropdown">
                <label for="rank-select">Select your rank:</label>
                <select id="rank-select">
                    <option value="40">Bronze 1, 2, 3 - €40</option>
                    <option value="36">Silver 1, 2, 3 - €36</option>
                    <option value="32">Gold 1, 2, 3 - €32</option>
                    <option value="31">Diamond 1 - €31</option>
                    <option value="29">Diamond 2 - €29</option>
                    <option value="27">Diamond 3 - €27</option>
                    <option value="25">Mythic 1 - €25</option>
                    <option value="23">Mythic 2 - €23</option>
                    <option value="22">Mythic 3 - €22</option>
                    <option value="20">Legendary 1 - €20</option>
                    <option value="17">Legendary 2 - €17</option>
                    <option value="14">Legendary 3 - €14</option>
                </select>
            </div>
            <p class="price-display" id="rank-price-display">Price: €40</p>
            <div class="contact" id="rank-contact"></div>
        </div>

        <!-- Brawler Product -->
        <div class="product">
            <h3>Brawler 🏆</h3>
            <p>Choose your current rank and the rank you want.</p>
            <div class="dropdown">
                <label for="current-brawler">Current rank:</label>
                <select id="current-brawler">
                    <option value="10">0-1000 - €10</option>
                    <option value="9">100-1000 - €9</option>
                    <option value="8">200-1000 - €8</option>
                    <option value="7">300-1000 - €7</option>
                    <option value="6">400-1000 - €6</option>
                    <option value="5">500-1000 - €5</option>
                    <option value="4">600-1000 - €4</option>
                    <option value="3">700-1000 - €3</option>
                    <option value="2">800-1000 - €2</option>
                    <option value="1">900-1000 - €1</option>
                    <option value="0">1000+ - €0</option>
                </select>
            </div>
            <div class="dropdown">
                <label for="desired-brawler">Desired rank:</label>
                <select id="desired-brawler">
                    <option value="7">1100 - €7</option>
                    <option value="12">1200 - €12</option>
                    <option value="18">1300 - €18</option>
                    <option value="24">1400 - €24</option>
                    <option value="28">1500 - €28</option>
                    <option value="34">1600 - €34</option>
                    <option value="38">1700 - €38</option>
                    <option value="44">1800 - €44</option>
                    <option value="50">1900 - €50</option>
                    <option value="59">2000 - €59</option>
                </select>
            </div>
            <p class="price-display" id="brawler-price-display">Price: €10</p>
            <div class="contact" id="brawler-contact"></div>
        </div>
    </div>

    <footer>
        <p>© 2024 Online Shop. All rights reserved.</p>
        <p>Using this site means you agree to our <a href="#">terms and conditions</a>.</p>
    </footer>

    <script>
        // Update price for Ranked product
        const rankSelect = document.getElementById("rank-select");
        const rankPriceDisplay = document.getElementById("rank-price-display");
        const rankContact = document.getElementById("rank-contact");

        rankSelect.addEventListener("change", () => {
            const selectedPrice = rankSelect.value;
            rankPriceDisplay.textContent = `Price: €${selectedPrice}`;
            rankContact.innerHTML = `
                <p>To order, contact us:</p>
                <a href="https://wa.me/79265881185" target="_blank" class="whatsapp">WhatsApp</a>
                <a href="https://t.me/peipya" target="_blank" class="telegram">Telegram</a>
            `;
        });

        // Update price for Brawler product
        const currentBrawler = document.getElementById("current-brawler");
        const desiredBrawler = document.getElementById("desired-brawler");
        const brawlerPriceDisplay = document.getElementById("brawler-price-display");
        const brawlerContact = document.getElementById("brawler-contact");

        function updateBrawlerPrice() {
            const currentPrice = parseInt(currentBrawler.value);
            const desiredPrice = parseInt(desiredBrawler.value);
            const totalPrice = currentPrice + desiredPrice;
            brawlerPriceDisplay.textContent = `Price: €${totalPrice}`;
            brawlerContact.innerHTML = `
                <p>To order, contact us:</p>
                <a href="https://wa.me/79265881185" target="_blank" class="whatsapp">WhatsApp</a>
                <a href="https://t.me/peipya" target="_blank" class="telegram">Telegram</a>
            `;
        }

        currentBrawler.addEventListener("change", updateBrawlerPrice);
        desiredBrawler.addEventListener("change", updateBrawlerPrice);
    </script>
</body>
</html>
