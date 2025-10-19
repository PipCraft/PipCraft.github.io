---
layout: default
title: My Crossword
permalink: /crossword/
---

<h2>My Custom Crossword</h2>
<p>Test your knowledge!</p>
<!-- Include the CryptoJS library for hashing the user id before sending it to the PuzzleMe server. -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/crypto-js/4.1.1/crypto-js.min.js"></script>
<!-- Include the javascript library for embedding this puzzle. -->
<script id="pm-script" src="https://puzzleme.amuselabs.com/pmm/js/puzzleme-embed.js"></script>
<!-- Specify the Amuse Labs server name from where the puzzles will be served and trigger the embed flow. -->
<script>
    PM_Config.PM_BasePath = "https://puzzleme.amuselabs.com/pmm/";
</script>
<!-- Specifies the puzzle to be embedded on the page. -->
<div style="position: relative; text-align: center;"><div class="pm-embed-div" data-id="7a383515" data-set="ba5848fce5faea2ee8e568493fe53e2d37891e69711149d1043d87e95b0b141f" data-puzzleType="crossword" data-height="700px" data-mobileMargin="10px"></div><div class="pm-attribution-div" style="font-family: sans-serif; font-size: 12px; color: rgb(102, 102, 102); position: absolute; top: 100%; left: 50%; transform: translate(-50%, 0px); padding-top: 5px; width: 100%;">Constructed with the online <a href="https://amuselabs.com/games/crossword/" target="_blank" style="color: #666666; text-decoration: underline;">crossword generator</a> from Amuse Labs</div></div>
