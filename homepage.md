---
layout: default
title: Homepage
---

<!DOCTYPE html>
<html>
<head>
<style>
    .rectangle2 {
        background-color: #f3eef4;
        height: 56px;
        width: 943px;
        display: flex;
        align-items: center;
        justify-content: space-between;
    }
    .button {
        color: #000000;
        font-size: 30px;
        font-family: Kaisei Tokumin;
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

    /* Add additional CSS styling here for the entire page */

</style>
</head>
<body>
    <div id='rectangle2' class='rectangle2'>
        <button class='button' id='artists'>Artists</button>
        <button class='button' id='arthub'>ArtHub</button>
        <button class='button' id='museums'>Museums</button>
    </div>
    <div id='findmuseumsnearyou' class='findmuseumsnearyou'>
        Find Museums Near You
    </div>

    <!-- Add other sections and content for your homepage here -->

</body>
</html>
