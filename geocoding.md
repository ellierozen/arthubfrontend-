<html>
<head>
    <style>
        body {
            background-color: #E7D8ED;
            margin: 0;
        }
        .rectangle2 {
            background-color: #f3eef4;
            height: 56px;
            display: flex;
            align-items: center;
            padding: 0 20px; /* Added padding */
        }
        .button {
            background-color: #ca552e;
            color: #fff;
            border: none;
            border-radius: 5px;
            padding: 10px 20px;
            text-decoration: none;
            cursor: pointer;
            display: block;
            text-align: left;
            margin-top: 15px;
        }
        .button:hover {
            background-color: #682222;
        }
        .button.arthub {
            background-color: #fff;
            color: #000;
            padding: 10px 20px;
        }
        h1 {
            font-size: 40px;
            color: #333;
            text-align: center;
            flex-grow: 1;
            margin-top: 20px;
        }
         #searchBar {
            margin-top: 20px; /* Adjust the margin here */
        }
        #results {
            font-size: 20px; /* Increased font size for the results */
        }
    </style>
</head>
<body>
    <div id='rectangle2' class='rectangle2'>
        <button class='button arthub' onclick="location.href='//ellierozen.github.io/arthubfrontend-/homepage';">Home</button>
        <h1>Find Nearby Museums</h1>
    </div>
    <div id="searchBar">
        <input type="text" id="zipcode" placeholder="Enter Zipcode">
        <button class='button arthub' onclick="searchMuseums()">Search</button>
    </div>
    <div id="results"></div>
    <script>
        const host = "https://arthub.stu.nighthawkcodingsociety.com";
        //const host = "https://localhost:8974";
        const zip_search = host + "/api/geocoding/?zipcode=";
        const options = {
            method: 'GET',
            mode: 'cors',
            cache: 'default',
            credentials: 'omit',
            headers: {
                'Content-Type': 'application/json'
            }
        };
        function searchMuseums() {
            const zipcode = document.getElementById('zipcode').value;
            fetch(zip_search + zipcode, options)
                .then(response => response.json())
                .then(data => {
                    displayResults(data.art_museums); // Pass the art_museums array to display
                })
                .catch(error => console.error('Error:', error));
        }
        function displayResults(data) {
            const resultsDiv = document.getElementById('results');
            resultsDiv.innerHTML = ''; // Clear previous results
            data.forEach(item => {
                const museum = document.createElement('div');
                const googleMapsLink = `https://www.google.com/maps/search/?api=1&query=${encodeURIComponent(item.vicinity)}`;
                museum.innerHTML = `<strong>${item.name}</strong><br>
                                    Address: <a href="${googleMapsLink}" target="_blank">${item.vicinity} (View on Google Maps)</a><br><br>`;
                resultsDiv.appendChild(museum);
            });
        }
    </script>
</body>
</html>