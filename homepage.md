
<html>
<head>
    <style>
        body {
            background-color: #E7D8ED;
        }
        .rectangle2 {
            background-color: #f3eef4;
            height: 56px;
            width: fill;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }
        .button {
            color: #000000;
            font-size: 30px;
            font-family: Roboto;
            line-height: auto;
            border-style: hidden;
            outline: none;
            background: none;
            border: none;
            cursor: pointer;
        }
        .button:hover {
            text-decoration: underline;
        }
        .arthub {
            font-size: 36px;
            width: auto;
        }
        .findmuseumsnearyou {
            color: #000000;
            text-align: center;
            font-size: 40px;
            font-family: Kaisei Tokumin;
            line-height: auto;
            border-style: hidden;
            outline: none;
            width: 608px;
        }
        .dropdown {
            position: relative;
            display: inline-block;
        }
        .dropdown-content {
            display: none;
            position: absolute;
            background-color: #f9f9f9;
            min-width: 160px;
            box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
            z-index: 1;
        }
        .dropdown-content a {
            color: black;
            padding: 12px 16px;
            text-decoration: none;
            display: block;
        }
        .dropdown:hover .dropdown-content {
            display: block;
        }
        h1 {
            font-size: 40px; /* Change the font size */
            color: #333; /* Change the text color */
            text-align: center; /* Change the alignment */
            margin-top: 20px; /* Change the top margin */
        }
        .image-container {
        display: flex;
        justify-content: space-around;
        align-items: center;
        margin: 20px 0;
        }
        .image-container img {
            max-width: 600px;
            max-height: 600px;
            margin: 10px;
        }
    </style>
</head>
<body>
    <div id='rectangle2' class='rectangle2'>
        <div class="dropdown">
            <button class='button artists' onclick="location.href='//ellierozen.github.io/arthubfrontend-/homepage';';">Artists</button>
            <div class="dropdown-content">
                <a href="baroqueartists.html">Baroque Artists </a>
                <a href="cubismartists.html">Cubism Artists</a>
                <a href="impressionistartists.html">Impressionist Artists</a>
                <a href="modernismartists.html">Modernism Artists</a>
                <a href="popartists.html">Pop Art Artists</a>
                <a href="postimpressionismartists.html">Post Impressionism Artists</a>
                <a href="realismartists.html">Realism Artists</a>
                <a href="renaissanceartists.html">Renaissance Artists</a>
                <a href="romantartists.html">Romanticism Artists</a>
                <!-- Add more artist links as needed -->
            </div>
        </div>
        <div class="dropdown">
            <button class='button arthub' onclick="location.href='//ellierozen.github.io/arthubfrontend-/homepage';">ArtHub</button>
            <div class="dropdown-content">
                <a href="artquiz.html">Art Quiz</a>
            </div>
        </div>
        <button class='button' id='museums' onclick="location.href='//ellierozen.github.io/arthubfrontend-/geocoding';">Museums</button>
        </div>
        <h1>Explore More Art</h1>
            <div class="image-container">
                <table>
            <tr>
                <td><img src="images/Museum-1.png" alt="Image 1 Description"></td>
                <td><img src="images/Museum-2.png" alt="Image 2 Description"></td>
            </tr>
            <tr>
                <td><img src="images/Museum-3.png" alt="Image 3 Description"></td>
                <td><img src="images/Museum-4.png" alt="Image 4 Description"></td>
            </tr>
        </table>
        </div>

    <!-- Add other sections and content for your homepage here -->

</body>
</html>
