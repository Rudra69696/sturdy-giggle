<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Raw Link → Loadstring Converter</title>

<style>
    body {
        background: #0f0f0f;
        color: #ffffff;
        font-family: monospace;
        padding: 20px;
    }

    h2 {
        color: #00ffcc;
    }

    textarea {
        width: 100%;
        height: 80px;
        background: #1a1a1a;
        color: #00ff00;
        border: 1px solid #333;
        padding: 10px;
        font-size: 14px;
        resize: none;
        margin-bottom: 10px;
    }

    button {
        background: #222;
        color: white;
        border: 1px solid #444;
        padding: 10px 15px;
        cursor: pointer;
        margin-right: 5px;
    }

    button:hover {
        background: #333;
    }
</style>
</head>

<body>

<h2>Raw Link → Loadstring Converter</h2>

<p>Paste your <b>RAW LINK</b> below:</p>

<textarea id="input" placeholder="https://pastefy.app/xxxx/raw"></textarea>

<button onclick="convert()">Convert</button>
<button onclick="copyOutput()">Copy</button>

<p>Loadstring Output:</p>

<textarea id="output" readonly></textarea>

<script>
function convert() {
    const link = document.getElementById("input").value.trim();
    if (!link) return;

    const result = `loadstring(game:HttpGet("${link}"))()`;
    document.getElementById("output").value = result;
}

function copyOutput() {
    const out = document.getElementById("output");
    out.select();
    document.execCommand("copy");
    alert("Copied!");
}
</script>

</body>
</html>
