<html>
<head>
    <style>
        body {
            background-color: #E7D8ED;
        }
        .button {
            background-color: #ca552e;
            color: #fff;
            border: none;
            border-radius: 5px;
            padding: 10px 20px;
            text-decoration: none;
            cursor: pointer;
            display: inline-block;
            text-align: center;
            margin-top: 15px;
        }
        .button:hover {
            background-color: #682222;
        }
        .button.arthub {
            background-color: #fff;
            color: #000;
        }
    </style>
</head>

<button class='button arthub' onclick="location.href='//ellierozen.github.io/arthubfrontend-/homepage';">ArtHub</button>

<body>
    <h1>Find Nearby Museums</h1>
    <input type="text" id="zipcode" placeholder="Enter Zipcode">
    <button onclick="searchMuseums()">Search</button>
    <div id="results"></div>
    <script>
        function searchMuseums() {
            const zipcode = document.getElementById('zipcode').value;
            fetch(`/get_art_museum_data?zipcode=${zipcode}`)
                .then(response => response.json())
                .then(data => {
                    // Display data in 'results' div
                    displayResults(data);
                })
                .catch(error => console.error('Error:', error));
        }
        function displayResults(data) {
            const resultsDiv = document.getElementById('results');
            resultsDiv.innerHTML = ''; // Clear previous results
            data.forEach(item => {
                const museum = document.createElement('div');
                museum.innerHTML = `<strong>${item.name}</strong><br>
                                    Rating: ${item.rating}<br>
                                    Address: ${item.vicinity}<br>
                                    <a href="${item.url}" target="_blank">View on Google Maps</a><br><br>`;
                resultsDiv.appendChild(museum);
            });
        }
    </script>
</body>
</html>



