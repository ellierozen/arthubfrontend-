<html>
<head>
    <style>
        body {
            background-color: #E7D8ED;
        }
        .rectangle2 {
            background-color: #f3eef4;
            height: 56px;
            display: flex;
            align-items: center;
            justify-content: center;
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
        h1 {
            font-size: 40px;
            color: #333;
            text-align: center;
            margin-top: 20px;
        }
        #searchBar {
            text-align: left;
            margin-top: 20px;
        }
    </style>
</head>

<body>
    <div id='rectangle2' class='rectangle2'>
        <h1>Find Nearby Museums</h1>
    </div>
    <div id="searchBar">
        <input type="text" id="zipcode" placeholder="Enter Zipcode">
        <button class='button arthub' onclick="searchMuseums()">Search</button>
    </div>
    <button class='button arthub' onclick="location.href='//ellierozen.github.io/arthubfrontend-/homepage';">Home</button>
    <div id="results"></div>
    <script>
        const host = "https://arthub.stu.nighthawkcodingsociety.com";
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
                                    Address: ${item.vicinity}<br>
                                    <a href="${item.opening_now}" target="_blank">View on Google Maps</a><br><br>`;
                resultsDiv.appendChild(museum);
            });
        }
    </script>
</body>
</html>