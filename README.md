<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width,initial-scale=1.0">
  <title>All-in-One Website</title>
  <style>
    * {
      margin: 0; padding: 0; box-sizing: border-box;
      font-family: Arial, sans-serif;
    }
    body { line-height: 1.6; background: #f9f9f9; color: #333; }
    header { background: #333; color: #fff; padding: 1rem; }
    nav { display: flex; justify-content: center; flex-wrap: wrap; background: #444; }
    nav a { color: white; padding: 1rem; text-decoration: none; }
    nav a:hover { background: #666; }
    section { padding: 2rem; }
    h2 { margin-bottom: 1rem; }

    /* Hero */
    .hero { background: #222; color: white; text-align: center; padding: 5rem 1rem; }
    .hero h1 span { color: yellow; }
    .btn { display: inline-block; padding: 10px 20px; background: #333; color: white; text-decoration: none; border-radius: 5px; }
    .btn:hover { background: #555; }

    /* About */
    .about-content { display: flex; flex-wrap: wrap; align-items: center; gap: 20px; }
    .about-content img { max-width: 200px; border-radius: 50%; }

    /* Projects */
    .project-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 1rem; }
    .project-card { background: white; padding: 1rem; border-radius: 8px; box-shadow: 0 0 5px rgba(0,0,0,0.2); }

    /* Contact */
    form { display: flex; flex-direction: column; gap: 10px; max-width: 400px; }
    input, textarea { padding: 10px; border: 1px solid #ccc; border-radius: 5px; }
    button { background: #333; color: white; padding: 10px; border: none; border-radius: 5px; cursor: pointer; }
    button:hover { background: #555; }
    footer { text-align: center; background: #333; color: white; padding: 1rem; margin-top: 1rem; }

    /* Quiz */
    .quiz-container { background: white; padding: 20px; border-radius: 10px; width: 90%; max-width: 500px; margin: auto; box-shadow: 0 0 10px rgba(0,0,0,0.2); }
    .quiz-container h2 { margin-bottom: 15px; }
    .quiz-container ul { list-style: none; margin-bottom: 20px; }
    .quiz-container li { margin: 10px 0; }
    .quiz-container .result { font-size: 18px; font-weight: bold; text-align: center; }

    /* Blog */
    .post { background: white; padding: 15px; margin-bottom: 20px; border-radius: 8px; box-shadow: 0 0 5px rgba(0,0,0,0.1); }

    /* Responsive Page */
    .container { display: grid; grid-template-columns: 3fr 1fr; gap: 1rem; }
    .content, .sidebar { background: white; padding: 1rem; border-radius: 8px; }
    @media (max-width: 768px) {
      .container { grid-template-columns: 1fr; }
    }
  </style>

  <!-- EmailJS SDK -->
  <script src="https://cdn.emailjs.com/dist/email.min.js"></script>
  <script>
    (function(){ emailjs.init("YOUR_PUBLIC_KEY"); })();
  </script>
</head>
<body>

  <!-- Navbar -->
  <header>
    <h1 style="text-align:center;">All-in-One Portfolio</h1>
  </header>
  <nav>
    <a href="#home">Home</a>
    <a href="#about">About</a>
    <a href="#projects">Projects</a>
    <a href="#blog">Blog</a>
    <a href="#quiz">Quiz</a>
    <a href="#responsive">Responsive Demo</a>
    <a href="#contact">Contact</a>
  </nav>

  <!-- Hero -->
  <section id="home" class="hero">
    <h1>Hello, I'm <span>MS__ VARSHA SREE</span></h1>
    <p>I am the veti officer</p>
    <a href="#projects" class="btn">View My Work</a>
  </section>

  <!-- About -->
  <section id="about" class="about">
    <h2>About Me</h2>
    <div class="about-content">
      <img src="IMG_20250828_134708600.jpg" alt="Profile Photo">
      <p>I am a student enthusiastic about technology and design. I love building interactive,
         user-friendly web applications and exploring new tools in the tech world.</p>
    </div>
  </section>

  <!-- Projects -->
  <section id="projects" class="projects">
    <h2>My Projects</h2>
    <div class="project-grid">
      <div class="project-card"><h3>Responsive Website</h3><p>Simple grid-based layout.</p></div>
      <div class="project-card"><h3>Quiz App</h3><p>JavaScript-based quiz app.</p></div>
      <div class="project-card"><h3>Personal Blog</h3><p>LocalStorage-powered blog system.</p></div>
    </div>
  </section>

  <!-- Blog -->
  <section id="blog">
    <h2>My Blog</h2>
    <div class="container" id="postsContainer"></div>
  </section>

  <!-- Quiz -->
  <section id="quiz">
    <h2>Quiz App</h2>
    <div class="quiz-container" id="quizBox">
      <h2 id="question">Question text</h2>
      <ul>
        <li><label><input type="radio" name="answer" class="answer" id="a"> <span id="a_text">Answer A</span></label></li>
        <li><label><input type="radio" name="answer" class="answer" id="b"> <span id="b_text">Answer B</span></label></li>
        <li><label><input type="radio" name="answer" class="answer" id="c"> <span id="c_text">Answer C</span></label></li>
        <li><label><input type="radio" name="answer" class="answer" id="d"> <span id="d_text">Answer D</span></label></li>
      </ul>
      <button id="submit">Submit</button>
      <div class="result" id="result"></div>
    </div>
  </section>

  <!-- Responsive Page -->
  <section id="responsive">
    <h2>Responsive Demo</h2>
    <div class="container">
      <div class="content">
        <h3>Main Content</h3>
        <p>This is the main content area. Resize the window to see the responsive effect.</p>
      </div>
      <div class="sidebar">
        <h3>Sidebar</h3>
        <p>This is a sidebar with some extra information or links.</p>
      </div>
    </div>
  </section>

  <!-- Contact -->
  <section id="contact">
    <h2>Contact Me</h2>
    <form id="contact-form">
      <input type="text" id="name" name="user_name" placeholder="Your Name" required>
      <input type="email" id="email" name="user_email" placeholder="Your Email" required>
      <textarea id="message" name="message" placeholder="Your Message" required></textarea>
      <button type="submit">Send</button>
    </form>
    <p id="form-status"></p>
  </section>

  <!-- Footer -->
  <footer>
    <p>&copy; 2025 MR__ YOGA | All rights reserved</p>
  </footer>

  <!-- Scripts -->
  <script>
    // Blog loader
    function loadPosts() {
      const postsContainer = document.getElementById("postsContainer");
      const posts = JSON.parse(localStorage.getItem("blogPosts")) || [];
      postsContainer.innerHTML = "";
      posts.reverse().forEach(post => {
        const postEl = document.createElement("div");
        postEl.classList.add("post");
        postEl.innerHTML = `<h3>${post.title}</h3>
          <small>${new Date(post.date).toLocaleString()}</small>
          <p>${post.content}</p>`;
        postsContainer.appendChild(postEl);
      });
    }
    loadPosts();

    // Quiz
    const quizData = [
      { question: "How do you insert a comment in a CSS file?", a: "<!-- this is a comment -->", b: "// this is a comment", c: "/* this is a comment */", d: "' this is a comment", correct: "c" },
      { question: "Which language is used for styling web pages?", a: "HTML", b: "JQuery", c: "CSS", d: "XML", correct: "c" },
      { question: "Which is not a JavaScript Framework?", a: "React", b: "Angular", c: "Vue", d: "Django", correct: "d" },
      { question: "Which property is used to change the background color?", a: "background-color", b: "text-color", c: "font-color", d: "color", correct: "a" }
    ];
    const quizBox = document.getElementById("quizBox");
    const answerEls = document.querySelectorAll(".answer");
    const questionEl = document.getElementById("question");
    const a_text = document.getElementById("a_text");
    const b_text = document.getElementById("b_text");
    const c_text = document.getElementById("c_text");
    const d_text = document.getElementById("d_text");
    const submitBtn = document.getElementById("submit");
    const resultEl = document.getElementById("result");
    let currentQuiz = 0, score = 0;

    function loadQuiz() {
      deselectAnswers();
      const currentQuizData = quizData[currentQuiz];
      questionEl.innerText = currentQuizData.question;
      a_text.innerText = currentQuizData.a;
      b_text.innerText = currentQuizData.b;
      c_text.innerText = currentQuizData.c;
      d_text.innerText = currentQuizData.d;
    }
    function getSelected() {
      let answer = undefined;
      answerEls.forEach(el => { if (el.checked) answer = el.id; });
      return answer;
    }
    function deselectAnswers() { answerEls.forEach(el => el.checked = false); }
    submitBtn.addEventListener("click", () => {
      const answer = getSelected();
      if (answer) {
        if (answer === quizData[currentQuiz].correct) score++;
        currentQuiz++;
        if (currentQuiz < quizData.length) { loadQuiz(); }
        else {
          quizBox.innerHTML = `<h2>You answered correctly ${score}/${quizData.length} questions.</h2>
                               <button onclick="location.reload()">Restart</button>`;
        }
      }
    });
    loadQuiz();
  </script>
</body>
</html>
