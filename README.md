<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Anime Birthday Invitation</title>

<style>

body{
    margin:0;
    padding:0;
    font-family:Arial,sans-serif;
    background:linear-gradient(135deg,#000428,#004e92);
    color:white;
    text-align:center;
    overflow-x:hidden;
}

h1{
    margin-top:20px;
    font-size:42px;
    text-shadow:0 0 15px cyan;
}

.box{
    width:90%;
    max-width:650px;
    margin:30px auto;
    background:rgba(255,255,255,0.1);
    padding:30px;
    border-radius:20px;
    backdrop-filter:blur(10px);
    box-shadow:0 0 20px rgba(0,255,255,0.5);
}

input{
    width:90%;
    padding:14px;
    margin:15px;
    border:none;
    border-radius:10px;
    font-size:16px;
}

button{
    padding:14px 30px;
    font-size:18px;
    border:none;
    border-radius:12px;
    cursor:pointer;
    background:cyan;
    color:black;
    font-weight:bold;
    transition:0.3s;
}

button:hover{
    transform:scale(1.05);
    background:white;
}

#output{
    margin-top:30px;
    font-size:22px;
    line-height:1.8;
}

.quote{
    margin-top:20px;
    color:#ffd700;
    font-style:italic;
    font-size:24px;
}

.character{
    color:#00ffff;
    font-size:30px;
    margin-top:20px;
}

.invite{
    margin-top:20px;
    font-size:26px;
    color:#ff99ff;
}

</style>
</head>

<body>

<h1>✨ Anime Birthday Invitation ✨</h1>

<div class="box">

    <h2>Enter Your Details</h2>

    <input type="date" id="dob">

    <br>

    <input type="text" id="animeCharacter"
    placeholder="Enter your favourite anime character">

    <br>

    <button onclick="generateInvitation()">
        Generate Invitation
    </button>

    <div id="output"></div>

</div>

<script>

async function generateInvitation(){

    let dob = document.getElementById("dob").value;
    let animeCharacter =
    document.getElementById("animeCharacter").value;

    let output = document.getElementById("output");

    if(dob === "" || animeCharacter === ""){
        output.innerHTML =
        "⚠ Please enter all details!";
        return;
    }

    let today = new Date();
    let enteredDate = new Date(dob);

    let invitationMessage = "";

    if(enteredDate < today){

        invitationMessage =
        "🎉 BELATED HAPPY BIRTHDAY 🎉<br>" +
        "You are invited to the Anime World Celebration!";

    }else{

        invitationMessage =
        "🎊 ADVANCE HAPPY BIRTHDAY 🎊<br>" +
        "Your Anime Invitation has arrived!";

    }

    // =========================
    // ALL ANIME QUOTES
    // =========================

    const quotes = {

        // DEMON SLAYER

        "tanjiro":
        "\"No matter how many people you may lose, you have no choice but to go on living.\"",

        "nezuko":
        "\"Humans are to be protected and saved.\"",

        "zenitsu":
        "\"I may be scared, but I never run away!\"",

        "inosuke":
        "\"I’m the king of the mountains!\"",

        "giyu":
        "\"The weak have no rights or choices.\"",

        "shinobu":
        "\"If we all work together, we can defeat the demons.\"",

        "rengoku":
        "\"Set your heart ablaze!\"",

        "obanai":
        "\"I do not trust anyone who breaks the rules.\"",

        "mitsuri":
        "\"Love makes you stronger!\"",

        "muichiro":
        "\"Sometimes drifting away helps you find yourself.\"",

        "sanemi":
        "\"Strength alone decides victory.\"",

        "gyomei":
        "\"Only through suffering can people grow.\"",

        "tengen":
        "\"Flashiness is everything!\"",

        "akaza":
        "\"Strength is the only thing that matters.\"",

        "muzan":
        "\"I can do whatever I want.\"",

        // ATTACK ON TITAN

        "eren":
        "\"If someone tries to take my freedom, I won’t hesitate to take theirs.\"",

        "mikasa":
        "\"This world is cruel, but also beautiful.\"",

        "armin":
        "\"People who can’t throw something away can never change anything.\"",

        "levi":
        "\"The only thing we’re allowed to do is believe.\"",

        "erwin":
        "\"My soldiers, rage!\"",

        "hange":
        "\"Curiosity drives humanity forward.\"",

        "annie":
        "\"Everyone has to be drunk on something.\"",

        "reiner":
        "\"I’m a warrior.\"",

        // NARUTO

        "naruto":
        "\"I never go back on my word. That's my ninja way!\"",

        "sasuke":
        "\"My name is Sasuke Uchiha. I hate many things.\"",

        "sakura":
        "\"A smile is the easiest way out of a difficult situation.\"",

        "kakashi":
        "\"Those who break the rules are scum, but those who abandon their friends are worse.\"",

        "itachi":
        "\"People live their lives bound by what they accept as correct.\"",

        "madara":
        "\"Wake up to reality.\"",

        "minato":
        "\"Believe in yourself and never give up.\"",

        "jiraiya":
        "\"A person grows up when he has to.\"",

        "gaara":
        "\"Love only yourself.\"",

        "hinata":
        "\"Never give up! Keep reaching higher!\"",

        "pain":
        "\"Sometimes you must hurt to know.\"",

        "obito":
        "\"Those who abandon their friends are worse than trash.\"",

        // JUJUTSU KAISEN

        "gojo":
        "\"Throughout heaven and earth, I alone am the honored one.\"",

        "yuji":
        "\"I don’t want to regret the way I live.\"",

        "megumi":
        "\"I save people unequally.\"",

        "nobara":
        "\"I love myself when I’m pretty and all dressed up!\"",

        "sukuna":
        "\"Know your place, fool.\"",

        "toji":
        "\"Instinct beats planning.\"",

        "geto":
        "\"Are you the strongest because you're Gojo Satoru?\"",

        "yuta":
        "\"I want the confidence to say it’s okay to live.\"",

        "nanami":
        "\"Work is shit.\"",

        "mahito":
        "\"The soul comes before the body.\"",

        // BLACK CLOVER

        "asta":
        "\"My magic is never giving up!\"",

        "yuno":
        "\"I’ll become the Wizard King.\"",

        "noelle":
        "\"I’m royalty after all!\"",

        "yami":
        "\"Surpass your limits. Right here. Right now.\"",

        "julius":
        "\"Time is truly fascinating.\"",

        "luck":
        "\"Let’s fight until one of us dies!\"",

        "magna":
        "\"A real man never gives up!\"",

        "finral":
        "\"Running away isn’t always cowardly.\"",

        "nacht":
        "\"Humans are at their best when cornered.\"",

        "mereoleona":
        "\"Natural talent alone cannot win.\"",

        "william":
        "\"Peace is born from understanding.\"",

        "licht":
        "\"Hatred only creates more hatred.\"",

        "patri":
        "\"Justice must prevail.\""

    };

    let key = animeCharacter.toLowerCase();

    let quote = quotes[key];

    if(!quote){
        quote =
        "\"Power comes from never giving up.\"";
    }

    output.innerHTML =

    `
    <div class="character">
        🌟 Favourite Character: ${animeCharacter}
    </div>

    <div class="invite">
        ${invitationMessage}
    </div>

    <div class="quote">
        💬 Famous Quote:<br><br>
        ${quote}
    </div>
    `;
}

</script>

</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Anime Birthday Invitation</title>

<style>

body{
    margin:0;
    padding:0;
    font-family:Arial,sans-serif;
    background:linear-gradient(135deg,#000428,#004e92);
    color:white;
    text-align:center;
    overflow-x:hidden;
}

h1{
    margin-top:20px;
    font-size:42px;
    text-shadow:0 0 15px cyan;
}

.box{
    width:90%;
    max-width:650px;
    margin:30px auto;
    background:rgba(255,255,255,0.1);
    padding:30px;
    border-radius:20px;
    backdrop-filter:blur(10px);
    box-shadow:0 0 20px rgba(0,255,255,0.5);
}

input{
    width:90%;
    padding:14px;
    margin:15px;
    border:none;
    border-radius:10px;
    font-size:16px;
}

button{
    padding:14px 30px;
    font-size:18px;
    border:none;
    border-radius:12px;
    cursor:pointer;
    background:cyan;
    color:black;
    font-weight:bold;
    transition:0.3s;
}

button:hover{
    transform:scale(1.05);
    background:white;
}

#output{
    margin-top:30px;
    font-size:22px;
    line-height:1.8;
}

.quote{
    margin-top:20px;
    color:#ffd700;
    font-style:italic;
    font-size:24px;
}

.character{
    color:#00ffff;
    font-size:30px;
    margin-top:20px;
}

.invite{
    margin-top:20px;
    font-size:26px;
    color:#ff99ff;
}

</style>
</head>

<body>

<h1>✨ Anime Birthday Invitation ✨</h1>

<div class="box">

    <h2>Enter Your Details</h2>

    <input type="date" id="dob">

    <br>

    <input type="text" id="animeCharacter"
    placeholder="Enter your favourite anime character">

    <br>

    <button onclick="generateInvitation()">
        Generate Invitation
    </button>

    <div id="output"></div>

</div>

<script>

async function generateInvitation(){

    let dob = document.getElementById("dob").value;
    let animeCharacter =
    document.getElementById("animeCharacter").value;

    let output = document.getElementById("output");

    if(dob === "" || animeCharacter === ""){
        output.innerHTML =
        "⚠ Please enter all details!";
        return;
    }

    let today = new Date();
    let enteredDate = new Date(dob);

    let invitationMessage = "";

    if(enteredDate < today){

        invitationMessage =
        "🎉 BELATED HAPPY BIRTHDAY 🎉<br>" +
        "You are invited to the Anime World Celebration!";

    }else{

        invitationMessage =
        "🎊 ADVANCE HAPPY BIRTHDAY 🎊<br>" +
        "Your Anime Invitation has arrived!";

    }

    // =========================
    // ALL ANIME QUOTES
    // =========================

    const quotes = {

        // DEMON SLAYER

        "tanjiro":
        "\"No matter how many people you may lose, you have no choice but to go on living.\"",

        "nezuko":
        "\"Humans are to be protected and saved.\"",

        "zenitsu":
        "\"I may be scared, but I never run away!\"",

        "inosuke":
        "\"I’m the king of the mountains!\"",

        "giyu":
        "\"The weak have no rights or choices.\"",

        "shinobu":
        "\"If we all work together, we can defeat the demons.\"",

        "rengoku":
        "\"Set your heart ablaze!\"",

        "obanai":
        "\"I do not trust anyone who breaks the rules.\"",

        "mitsuri":
        "\"Love makes you stronger!\"",

        "muichiro":
        "\"Sometimes drifting away helps you find yourself.\"",

        "sanemi":
        "\"Strength alone decides victory.\"",

        "gyomei":
        "\"Only through suffering can people grow.\"",

        "tengen":
        "\"Flashiness is everything!\"",

        "akaza":
        "\"Strength is the only thing that matters.\"",

        "muzan":
        "\"I can do whatever I want.\"",

        // ATTACK ON TITAN

        "eren":
        "\"If someone tries to take my freedom, I won’t hesitate to take theirs.\"",

        "mikasa":
        "\"This world is cruel, but also beautiful.\"",

        "armin":
        "\"People who can’t throw something away can never change anything.\"",

        "levi":
        "\"The only thing we’re allowed to do is believe.\"",

        "erwin":
        "\"My soldiers, rage!\"",

        "hange":
        "\"Curiosity drives humanity forward.\"",

        "annie":
        "\"Everyone has to be drunk on something.\"",

        "reiner":
        "\"I’m a warrior.\"",

        // NARUTO

        "naruto":
        "\"I never go back on my word. That's my ninja way!\"",

        "sasuke":
        "\"My name is Sasuke Uchiha. I hate many things.\"",

        "sakura":
        "\"A smile is the easiest way out of a difficult situation.\"",

        "kakashi":
        "\"Those who break the rules are scum, but those who abandon their friends are worse.\"",

        "itachi":
        "\"People live their lives bound by what they accept as correct.\"",

        "madara":
        "\"Wake up to reality.\"",

        "minato":
        "\"Believe in yourself and never give up.\"",

        "jiraiya":
        "\"A person grows up when he has to.\"",

        "gaara":
        "\"Love only yourself.\"",

        "hinata":
        "\"Never give up! Keep reaching higher!\"",

        "pain":
        "\"Sometimes you must hurt to know.\"",

        "obito":
        "\"Those who abandon their friends are worse than trash.\"",

        // JUJUTSU KAISEN

        "gojo":
        "\"Throughout heaven and earth, I alone am the honored one.\"",

        "yuji":
        "\"I don’t want to regret the way I live.\"",

        "megumi":
        "\"I save people unequally.\"",

        "nobara":
        "\"I love myself when I’m pretty and all dressed up!\"",

        "sukuna":
        "\"Know your place, fool.\"",

        "toji":
        "\"Instinct beats planning.\"",

        "geto":
        "\"Are you the strongest because you're Gojo Satoru?\"",

        "yuta":
        "\"I want the confidence to say it’s okay to live.\"",

        "nanami":
        "\"Work is shit.\"",

        "mahito":
        "\"The soul comes before the body.\"",

        // BLACK CLOVER

        "asta":
        "\"My magic is never giving up!\"",

        "yuno":
        "\"I’ll become the Wizard King.\"",

        "noelle":
        "\"I’m royalty after all!\"",

        "yami":
        "\"Surpass your limits. Right here. Right now.\"",

        "julius":
        "\"Time is truly fascinating.\"",

        "luck":
        "\"Let’s fight until one of us dies!\"",

        "magna":
        "\"A real man never gives up!\"",

        "finral":
        "\"Running away isn’t always cowardly.\"",

        "nacht":
        "\"Humans are at their best when cornered.\"",

        "mereoleona":
        "\"Natural talent alone cannot win.\"",

        "william":
        "\"Peace is born from understanding.\"",

        "licht":
        "\"Hatred only creates more hatred.\"",

        "patri":
        "\"Justice must prevail.\""

    };

    let key = animeCharacter.toLowerCase();

    let quote = quotes[key];

    if(!quote){
        quote =
        "\"Power comes from never giving up.\"";
    }

    output.innerHTML =

    `
    <div class="character">
        🌟 Favourite Character: ${animeCharacter}
    </div>

    <div class="invite">
        ${invitationMessage}
    </div>

    <div class="quote">
        💬 Famous Quote:<br><br>
        ${quote}
    </div>
    `;
}

</script>

</body>
</html>

