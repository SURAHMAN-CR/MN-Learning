<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>EduPlatform Ultimate</title>

  <!-- Firebase -->
  <script src="https://www.gstatic.com/firebasejs/10.7.1/firebase-app.js"></script>
  <script src="https://www.gstatic.com/firebasejs/10.7.1/firebase-auth.js"></script>
  <script src="https://www.gstatic.com/firebasejs/10.7.1/firebase-firestore.js"></script>

  <style>
    body {margin:0;font-family:Arial;background:#f4f6f9}
    header {background:#0f172a;color:#fff;padding:15px;text-align:center;font-size:22px}
    nav {display:flex;gap:10px;padding:10px;background:#1e293b}
    nav button {flex:1;padding:10px;border:none;border-radius:8px;cursor:pointer}
    .container{padding:20px}
    .card{background:#fff;padding:15px;border-radius:12px;margin-bottom:15px;box-shadow:0 3px 8px rgba(0,0,0,0.1)}
    input,textarea,select{width:100%;padding:10px;margin:5px 0;border-radius:8px;border:1px solid #ccc}
    button.primary{background:#2563eb;color:white;border:none;padding:10px;border-radius:8px;cursor:pointer}
  </style>
</head>
<body>

<header>EduPlatform Ultimate</header>

<nav id="nav" style="display:none">
  <button onclick="showPage('dashboard')">Dashboard</button>
  <button onclick="showPage('courses')">Kelas</button>
  <button onclick="showPage('quiz')">Kuis</button>
  <button onclick="showPage('forum')">Forum</button>
  <button onclick="logout()">Logout</button>
</nav>

<div class="container">

<!-- AUTH -->
<div id="auth" class="card">
  <h2>Login / Register</h2>
  <input type="email" id="email" placeholder="Email">
  <input type="password" id="password" placeholder="Password">
  <select id="role">
    <option value="siswa">Siswa</option>
    <option value="guru">Guru</option>
  </select>
  <button class="primary" onclick="register()">Register</button>
  <button onclick="login()">Login</button>
</div>

<!-- DASHBOARD -->
<div id="dashboard" class="page" style="display:none">
  <div class="card">
    <h2>Dashboard</h2>
    <p id="userInfo"></p>
  </div>
</div>

<!-- COURSES -->
<div id="courses" class="page" style="display:none">
  <div class="card">
    <h3>Tambah Kelas</h3>
    <input id="courseTitle" placeholder="Judul">
    <textarea id="courseDesc"></textarea>
    <input id="videoUrl" placeholder="Link Video YouTube">
    <button class="primary" onclick="addCourse()">Tambah</button>
  </div>
  <div id="courseList"></div>
</div>

<!-- QUIZ -->
<div id="quiz" class="page" style="display:none">
  <div class="card">
    <h3>Buat Soal</h3>
    <input id="q" placeholder="Soal">
    <input id="a" placeholder="Jawaban">
    <button onclick="addQuestion()">Tambah</button>
  </div>
  <div id="quizList"></div>
</div>

<!-- FORUM -->
<div id="forum" class="page" style="display:none">
  <div class="card">
    <input id="post" placeholder="Diskusi...">
    <button onclick="addPost()">Kirim</button>
  </div>
  <div id="posts"></div>
</div>

</div>

<script>
// CONFIG (ISI PUNYA LU)
const firebaseConfig = {
  apiKey: "ISI_APIKEY",
  authDomain: "ISI",
  projectId: "ISI",
};

firebase.initializeApp(firebaseConfig);
const auth = firebase.auth();
const db = firebase.firestore();

// AUTH
function register(){
  let email = emailInput();
  let pass = passInput();
  let role = document.getElementById('role').value;

  auth.createUserWithEmailAndPassword(email,pass)
  .then(user=>{
    db.collection('users').doc(user.user.uid).set({email,role});
  });
}

function login(){
  auth.signInWithEmailAndPassword(emailInput(),passInput());
}

function logout(){auth.signOut();}

function emailInput(){return document.getElementById('email').value}
function passInput(){return document.getElementById('password').value}

// SESSION
auth.onAuthStateChanged(async user=>{
  if(user){
    document.getElementById('auth').style.display='none';
    document.getElementById('nav').style.display='flex';

    let doc = await db.collection('users').doc(user.uid).get();
    document.getElementById('userInfo').innerText = doc.data().email + ' ('+doc.data().role+')';

    showPage('dashboard');
    loadCourses(); loadPosts(); loadQuiz();
  }
});

// NAV
function showPage(id){
  document.querySelectorAll('.page').forEach(p=>p.style.display='none');
  document.getElementById(id).style.display='block';
}

// COURSE
function addCourse(){
  db.collection('courses').add({
    title:courseTitle.value,
    desc:courseDesc.value,
    video:videoUrl.value
  });
}

function loadCourses(){
  db.collection('courses').onSnapshot(snap=>{
    courseList.innerHTML='';
    snap.forEach(doc=>{
      let d=doc.data();
      courseList.innerHTML+=`
      <div class='card'>
        <h3>${d.title}</h3>
        <p>${d.desc}</p>
        <iframe width='100%' height='200' src='${d.video.replace("watch?v=","embed/")}'></iframe>
      </div>`;
    })
  })
}

// QUIZ
function addQuestion(){
  db.collection('quiz').add({q:q.value,a:a.value});
}

function loadQuiz(){
  db.collection('quiz').onSnapshot(snap=>{
    quizList.innerHTML='';
    snap.forEach(doc=>{
      let d=doc.data();
      quizList.innerHTML+=`
      <div class='card'>
        <p>${d.q}</p>
        <input id='ans${doc.id}'>
        <button onclick="check('${doc.id}','${d.a}')">Jawab</button>
      </div>`;
    })
  })
}

function check(id,ans){
  let val=document.getElementById('ans'+id).value;
  alert(val==ans?'Benar':'Salah');
}

// FORUM
function addPost(){
  db.collection('posts').add({text:post.value});
}

function loadPosts(){
  db.collection('posts').onSnapshot(snap=>{
    posts.innerHTML='';
    snap.forEach(doc=>{
      posts.innerHTML+=`<div class='card'>${doc.data().text}</div>`;
    })
  })
}

</script>

</body>
</html>
