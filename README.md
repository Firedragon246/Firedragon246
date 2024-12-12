<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript Piano</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>

    <button onclick="openPiano()">Open Piano</button>

    <div id="piano-popup" class="popup" style="display:none;">
        <div class="piano">
            <button class="key white" onclick="playSound('C')"></button>
            <button class="key black" onclick="playSound('C#')"></button>
            <button class="key white" onclick="playSound('D')"></button>
            <button class="key black" onclick="playSound('D#')"></button>
            <button class="key white" onclick="playSound('E')"></button>
            <button class="key white" onclick="playSound('F')"></button>
            <button class="key black" onclick="playSound('F#')"></button>
            <button class="key white" onclick="playSound('G')"></button>
            <button class="key black" onclick="playSound('G#')"></button>
            <button class="key white" onclick="playSound('A')"></button>
            <button class="key black" onclick="playSound('A#')"></button>
            <button class="key white" onclick="playSound('B')"></button>
            <button class="key white" onclick="playSound('C2')"></button>
        </div>
        <button onclick="closePiano()">Close Piano</button>
    </div>

    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    padding: 20px;
}

.popup {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: white;
    padding: 20px;
    border: 1px solid #ccc;
    z-index: 1000;
}

.piano {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
}

.key {
    width: 40px;
    height: 120px;
    margin: 1px;
    border: 1px solid #333;
    cursor: pointer;
}

.white {
    background-color: white;
    z-index: 1;
}

.black {
    background-color: black;
    width: 30px;
    height: 80px;
    position: absolute;
    margin-left: -15px;
    z-index: 2;
}
// Function to play sound based on the key
function playSound(note) {
    const audio = new Audio(`sounds/${note}.mp3`);
    audio.play();
}

// Function to open the piano popup
function openPiano() {
    document.getElementById("piano-popup").style.display = "block";
}

// Function to close the piano popup
function closePiano() {
    document.getElementById("piano-popup").style.display = "none";
}
/your-project-directory
│
├── index.html      # Main HTML file
├── styles.css      # CSS for styling the piano
├── script.js       # JavaScript to handle key presses
└── /sounds         # Folder containing the sound files (e.g., C.mp3, D.mp3, etc.)

