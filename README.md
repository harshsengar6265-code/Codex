# Codex
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>College Students Helper</title>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: Arial, sans-serif;
}

body {
    background: #f4f7fb;
    color: #222;
}

header {
    background: linear-gradient(135deg, #4f46e5, #7c3aed);
    color: white;
    padding: 25px 15px;
    text-align: center;
}

header h1 {
    font-size: 28px;
}

header p {
    margin-top: 8px;
}

nav {
    background: white;
    padding: 12px;
    display: flex;
    justify-content: center;
    gap: 8px;
    flex-wrap: wrap;
    box-shadow: 0 2px 8px #ccc;
    position: sticky;
    top: 0;
    z-index: 10;
}

nav button {
    border: none;
    background: #eef2ff;
    color: #4338ca;
    padding: 10px 15px;
    border-radius: 8px;
    cursor: pointer;
    font-weight: bold;
}

nav button:hover {
    background: #4f46e5;
    color: white;
}

.container {
    max-width: 1000px;
    margin: auto;
    padding: 25px 15px;
}

.section {
    display: none;
}

.section.active {
    display: block;
}

.welcome {
    background: white;
    padding: 25px;
    border-radius: 15px;
    box-shadow: 0 3px 12px #ddd;
    text-align: center;
}

.welcome h2 {
    color: #4f46e5;
    margin-bottom: 10px;
}

.cards {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 15px;
    margin-top: 20px;
}

.card {
    background: white;
    padding: 22px;
    border-radius: 14px;
    box-shadow: 0 3px 10px #ddd;
    text-align: center;
}

.card .icon {
    font-size: 40px;
    margin-bottom: 10px;
}

.card h3 {
    margin-bottom: 8px;
    color: #4f46e5;
}

.subject {
    cursor: pointer;
    transition: 0.2s;
}

.subject:hover {
    transform: translateY(-4px);
}

.notes-box {
    background: white;
    padding: 20px;
    border-radius: 15px;
    box-shadow: 0 3px 10px #ddd;
}

input, textarea, select {
    width: 100%;
    padding: 12px;
    margin: 8px 0;
    border: 1px solid #ccc;
    border-radius: 8px;
}

textarea {
    height: 150px;
    resize: none;
}

.main-btn {
    background: #4f46e5;
    color: white;
    border: none;
    padding: 12px 20px;
    border-radius: 8px;
    cursor: pointer;
    margin-top: 5px;
}

.main-btn:hover {
    background: #3730a3;
}

table {
    width: 100%;
    border-collapse: collapse;
    background: white;
    margin-top: 15px;
    box-shadow: 0 3px 10px #ddd;
}

th, td {
    border: 1px solid #ddd;
    padding: 12px;
    text-align: center;
}

th {
    background: #4f46e5;
    color: white;
}

.contact {
    background: white;
    padding: 25px;
    border-radius: 15px;
    box-shadow: 0 3px 10px #ddd;
}

footer {
    margin-top: 30px;
    background: #111827;
    color: white;
    text-align: center;
    padding: 20px;
}

#language {
    width: auto;
    padding: 8px;
}
</style>
</head>

<body>

<header>
    <h1>🎓 College Students Helper</h1>
    <p id="subtitle">Your Smart College Study Assistant</p>
</header>

<nav>
    <button onclick="showSection('home')">🏠 Home</button>
    <button onclick="showSection('subjects')">📚 Subjects</button>
    <button onclick="showSection('notes')">📝 Notes</button>
    <button onclick="showSection('timetable')">📅 Timetable</button>
    <button onclick="showSection('contact')">📞 Contact</button>

    <select id="language" onchange="changeLanguage()">
        <option value="en">English</option>
        <option value="hi">हिंदी</option>
    </select>
</nav>

<div class="container">

<!-- HOME -->
<section id="home" class="section active">

    <div class="welcome">
        <h2 id="welcomeTitle">Welcome Students! 👋</h2>
        <p id="welcomeText">
            Manage your subjects, notes and timetable in one place.
        </p>
    </div>

    <div class="cards">

        <div class="card">
            <div class="icon">📚</div>
            <h3>Subjects</h3>
            <p>View your college subjects.</p>
        </div>

        <div class="card">
            <div class="icon">📝</div>
            <h3>Notes</h3>
            <p>Create and save study notes.</p>
        </div>

        <div class="card">
            <div class="icon">📅</div>
            <h3>Timetable</h3>
            <p>Check your daily classes.</p>
        </div>

        <div class="card">
            <div class="icon">📞</div>
            <h3>Contact</h3>
            <p>Contact college support.</p>
        </div>

    </div>
</section>


<!-- SUBJECTS -->
<section id="subjects" class="section">

    <h2>📚 College Subjects</h2>

    <div class="cards">

        <div class="card subject">
            <div class="icon">💻</div>
            <h3>Computer Science</h3>
            <p>Programming & Software</p>
        </div>

        <div class="card subject">
            <div class="icon">📊</div>
            <h3>Mathematics</h3>
            <p>College Mathematics</p>
        </div>

        <div class="card subject">
            <div class="icon">⚡</div>
            <h3>Physics</h3>
            <p>Physics & Electronics</p>
        </div>

        <div class="card subject">
            <div class="icon">🧪</div>
            <h3>Chemistry</h3>
            <p>Basic Chemistry</p>
        </div>

    </div>
</section>


<!-- NOTES -->
<section id="notes" class="section">

    <h2>📝 My Notes</h2>

    <div class="notes-box">

        <input type="text" id="noteTitle"
        placeholder="Enter note title">

        <textarea id="noteText"
        placeholder="Write your notes here..."></textarea>

        <button class="main-btn" onclick="saveNote()">
            💾 Save Note
        </button>

        <div id="savedNotes"></div>

    </div>

</section>


<!-- TIMETABLE -->
<section id="timetable" class="section">

    <h2>📅 College Timetable</h2>

    <table>

        <tr>
            <th>Day</th>
            <th>9:00 AM</th>
            <th>10:00 AM</th>
            <th>11:00 AM</th>
            <th>12:00 PM</th>
        </tr>

        <tr>
            <td>Monday</td>
            <td>Maths</td>
            <td>Physics</td>
            <td>Computer</td>
            <td>English</td>
        </tr>

        <tr>
            <td>Tuesday</td>
            <td>Computer</td>
            <td>Maths</td>
            <td>Chemistry</td>
            <td>Physics</td>
        </tr>

        <tr>
            <td>Wednesday</td>
            <td>Physics</td>
            <td>English</td>
            <td>Computer</td>
            <td>Maths</td>
        </tr>

        <tr>
            <td>Thursday</td>
            <td>Chemistry</td>
            <td>Computer</td>
            <td>Maths</td>
            <td>English</td>
        </tr>

        <tr>
            <td>Friday</td>
            <td>Computer</td>
            <td>Physics</td>
            <td>Maths</td>
            <td>Chemistry</td>
        </tr>

    </table>

</section>


<!-- CONTACT -->
<section id="contact" class="section">

    <h2>📞 Contact Us</h2>

    <div class="contact">

        <input type="text"
        id="name"
        placeholder="Your Name">

        <input type="email"
        id="email"
        placeholder="Your Email">

        <textarea id="message"
        placeholder="Write your message"></textarea>

        <button class="main-btn" onclick="sendMessage()">
            Send Message
        </button>

    </div>

</section>

</div>

<footer>
    <p>© 2026 College Students Helper</p>
    <p>Made for College Students ❤️</p>
</footer>


<script>

// Section change
function showSection(sectionId) {

    let sections = document.querySelectorAll(".section");

    sections.forEach(function(section) {
        section.classList.remove("active");
    });

    document.getElementById(sectionId)
        .classList.add("active");

    window.scrollTo(0, 0);
}


// Save Notes
function saveNote() {

    let title = document.getElementById("noteTitle").value;
    let text = document.getElementById("noteText").value;

    if(title === "" || text === "") {
        alert("Please enter title and notes!");
        return;
    }

    let note = document.createElement("div");

    note.style.background = "#f3f4f6";
    note.style.padding = "15px";
    note.style.marginTop = "15px";
    note.style.borderRadius = "10px";

    note.innerHTML =
        "<h3>" + title + "</h3>" +
        "<p>" + text + "</p>";

    document.getElementById("savedNotes")
        .appendChild(note);

    document.getElementById("noteTitle").value = "";
    document.getElementById("noteText").value = "";

    alert("Note Saved Successfully! ✅");
}


// Contact
function sendMessage() {

    let name = document.getElementById("name").value;
    let email = document.getElementById("email").value;
    let message = document.getElementById("message").value;

    if(name === "" || email === "" || message === "") {
        alert("Please fill all fields!");
        return;
    }

    alert("Thank you " + name +
          "! Your message has been submitted. ✅");

    document.getElementById("name").value = "";
    document.getElementById("email").value = "";
    document.getElementById("message").value = "";
}


// Language
function changeLanguage() {

    let language =
        document.getElementById("language").value;

    if(language === "hi") {

        document.getElementById("subtitle").innerText =
        "आपका स्मार्ट कॉलेज स्टडी असिस्टेंट";

        document.getElementById("welcomeTitle").innerText =
        "स्वागत है विद्यार्थियों! 👋";

        document.getElementById("welcomeText").innerText =
        "अपने Subjects, Notes और Timetable को एक जगह मैनेज करें।";

    } else {

        document.getElementById("subtitle").innerText =
        "Your Smart College Study Assistant";

        document.getElementById("welcomeTitle").innerText =
        "Welcome Students! 👋";

        document.getElementById("welcomeText").innerText =
        "Manage your subjects, notes and timetable in one place.";
    }
}

</script>

</body>
</html>
