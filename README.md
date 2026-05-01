<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Student Paper Hub - Free Sample Papers & Solutions Class 6-10</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-blue: #2c5282;
            --secondary-blue: #4299e1;
            --light-blue: #bee3f8;
            --white: #ffffff;
            --gray: #718096;
            --dark-gray: #4a5568;
            --shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            --shadow-hover: 0 8px 25px rgba(0, 0, 0, 0.15);
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: var(--dark-gray);
            overflow-x: hidden;
        }

        /* Navigation */
        .navbar {
            background: var(--white);
            box-shadow: var(--shadow);
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            padding: 0.5rem 0;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            color: var(--primary-blue);
            text-decoration: none;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--gray);
            font-weight: 500;
            transition: all 0.3s ease;
            position: relative;
        }

        .nav-links a:hover {
            color: var(--primary-blue);
        }

        .nav-links a.active {
            color: var(--primary-blue);
        }

        .nav-links a.active::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 2px;
            background: var(--primary-blue);
        }

        .hamburger {
            display: none;
            flex-direction: column;
            cursor: pointer;
        }

        .hamburger span {
            width: 25px;
            height: 3px;
            background: var(--primary-blue);
            margin: 3px 0;
            transition: 0.3s;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, var(--primary-blue) 0%, var(--secondary-blue) 100%);
            color: white;
            padding: 120px 2rem 80px;
            text-align: center;
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            animation: fadeInUp 1s ease;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            opacity: 0.95;
            animation: fadeInUp 1s ease 0.2s both;
        }

        .search-container {
            max-width: 600px;
            margin: 0 auto;
            display: flex;
            gap: 0;
            background: white;
            border-radius: 50px;
            overflow: hidden;
            box-shadow: var(--shadow);
            animation: fadeInUp 1s ease 0.4s both;
        }

        .search-input {
            flex: 1;
            padding: 1rem 1.5rem;
            border: none;
            font-size: 1rem;
            outline: none;
        }

        .search-btn {
            background: var(--secondary-blue);
            color: white;
            border: none;
            padding: 1rem 2rem;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .search-btn:hover {
            background: var(--primary-blue);
        }

        /* Notification Banner */
        .notification {
            background: #48bb78;
            color: white;
            text-align: center;
            padding: 1rem;
            font-weight: 500;
            animation: slideDown 0.5s ease;
        }

        /* Main Content */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }

        .section {
            display: none;
        }

        .section.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }

        /* Classes Grid */
        .classes-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .class-card {
            background: white;
            border-radius: 15px;
            padding: 2rem;
            text-align: center;
            box-shadow: var(--shadow);
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .class-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, var(--primary-blue), var(--secondary-blue));
        }

        .class-card:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-hover);
        }

        .class-icon {
            font-size: 3rem;
            color: var(--secondary-blue);
            margin-bottom: 1rem;
        }

        .class-card h3 {
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
            color: var(--primary-blue);
        }

        /* Subjects Grid */
        .subjects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .subject-card {
            background: white;
            border-radius: 15px;
            padding: 2rem;
            box-shadow: var(--shadow);
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .subject-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-hover);
        }

        .subject-icon {
            font-size: 2.5rem;
            color: var(--secondary-blue);
            margin-bottom: 1rem;
        }

        /* Papers List */
        .papers-list {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
        }

        .paper-card {
            background: white;
            border-radius: 12px;
            padding: 1.5rem;
            box-shadow: var(--shadow);
            transition: all 0.3s ease;
            border-left: 4px solid var(--secondary-blue);
        }

        .paper-card:hover {
            box-shadow: var(--shadow-hover);
            transform: translateX(5px);
        }

        .paper-title {
            font-size: 1.1rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
            color: var(--dark-gray);
        }

        .paper-meta {
            color: var(--gray);
            font-size: 0.9rem;
            margin-bottom: 1rem;
        }

        .download-btn {
            background: var(--secondary-blue);
            color: white;
            border: none;
            padding: 0.7rem 1.5rem;
            border-radius: 25px;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
        }

        .download-btn:hover {
            background: var(--primary-blue);
            transform: scale(1.05);
        }

        /* Admin Panel */
        .admin-panel {
            background: white;
            border-radius: 15px;
            padding: 2rem;
            box-shadow: var(--shadow);
            margin-top: 2rem;
        }

        .admin-form {
            display: grid;
            gap: 1rem;
            max-width: 500px;
        }

        .form-group {
            display: flex;
            flex-direction: column;
        }

        .form-group label {
            margin-bottom: 0.5rem;
            font-weight: 600;
            color: var(--dark-gray);
        }

        .form-group input, .form-group select {
            padding: 0.8rem;
            border: 2px solid #e2e8f0;
            border-radius: 8px;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus, .form-group select:focus {
            outline: none;
            border-color: var(--secondary-blue);
        }

        .upload-btn {
            background: var(--primary-blue);
            color: white;
            border: none;
            padding: 1rem 2rem;
            border-radius: 8px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .upload-btn:hover {
            background: #2b6cb0;
        }

        /* Footer */
        .footer {
            background: var(--dark-gray);
            color: white;
            text-align: center;
            padding: 3rem 2rem 1.5rem;
            margin-top: 4rem;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
        }

        .social-links {
            margin: 2rem 0;
        }

        .social-links a {
            color: white;
            font-size: 1.5rem;
            margin: 0 1rem;
            transition: all 0.3s ease;
        }

        .social-links a:hover {
            color: var(--secondary-blue);
            transform: translateY(-3px);
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes slideDown {
            from {
                transform: translateY(-100%);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .hamburger {
                display: flex;
            }

            .nav-links {
                position: fixed;
                left: -100%;
                top: 70px;
                flex-direction: column;
                background-color: white;
                width: 100%;
                text-align: center;
                transition: 0.3s;
                box-shadow: var(--shadow);
                padding: 2rem 0;
            }

            .nav-links.active {
                left: 0;
            }

            .hero h1 {
                font-size: 2rem;
            }

            .hero p {
                font-size: 1.1rem;
            }

            .container {
                padding: 1rem;
            }

            .classes-grid,
            .subjects-grid,
            .papers-list {
                grid-template-columns: 1fr;
                gap: 1rem;
            }
        }

        /* Search Results */
        .search-results {
            margin-top: 2rem;
        }

        .no-results {
            text-align: center;
            padding: 3rem;
            color: var(--gray);
        }

        .back-btn {
            background: var(--gray);
            color: white;
            border: none;
            padding: 0.8rem 1.5rem;
            border-radius: 25px;
            cursor: pointer;
            margin-bottom: 2rem;
            font-weight: 500;
            transition: all 0.3s ease;
        }

        .back-btn:hover {
            background: var(--dark-gray);
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav class="navbar">
        <div class="nav-container">
            <a href="#" class="logo" onclick="showSection('home')">
                <i class="fas fa-graduation-cap"></i> Student Paper Hub
            </a>
            <ul class="nav-links" id="navLinks">
                <li><a href="#" onclick="showSection('home')" class="nav-link active">Home</a></li>
                <li><a href="#" onclick="showSection('classes')" class="nav-link">Classes</a></li>
                <li><a href="#" onclick="showSection('downloads')" class="nav-link">Downloads</a></li>
                <li><a href="#" onclick="showSection('admin')" class="nav-link">Admin</a></li>
                <li><a href="#" onclick="showSection('contact')" class="nav-link">Contact</a></li>
            </ul>
            <div class="hamburger" onclick="toggleMobileMenu()">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </div>
    </nav>

    <!-- Notification Banner -->
    <div class="notification">
        <i class="fas fa-star"></i> Latest papers for 2026 exams updated! 
        <span id="notificationClose" style="cursor: pointer; margin-left: 1rem;">✕</span>
    </div>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <h1>Student Paper Hub</h1>
        <p>Free Sample Papers & Solutions for Class 6–10</p>
        <div class="search-container">
            <input type="text" class="search-input" id="searchInput" placeholder="Search papers by class or subject...">
            <button class="search-btn" onclick="performSearch()">
                <i class="fas fa-search"></i> Search
            </button>
        </div>
    </section>

    <div class="container">
        <!-- Classes Section -->
        <section id="classes" class="section">
            <h2 style="text-align: center; margin-bottom: 1rem; color: var(--primary-blue);">
                Select Your Class
            </h2>
            <div class="classes-grid">
                <div class="class-card" onclick="showSubjects(6)">
                    <div class="class-icon"><i class="fas fa-6"></i></div>
                    <h3>Class 6</h3>
                </div>
                <div class="class-card" onclick="showSubjects(7)">
                    <div class="class-icon"><i class="fas fa-7"></i></div>
                    <h3>Class 7</h3>
                </div>
                <div class="class-card" onclick="showSubjects(8)">
                    <div class="class-icon"><i class="fas fa-8"></i></div>
                    <h3>Class 8</h3>
                </div>
                <div class="class-card" onclick="showSubjects(9)">
                    <div class="class-icon"><i class="fas fa-9"></i></div>
                    <h3>Class 9</h3>
                </div>
                <div class="class-card" onclick="showSubjects(10)">
                    <div class="class-icon"><i class="fas fa-10"></i></div>
                    <h3>Class 10</h3>
                </div>
            </div>
        </section>

        <!-- Subjects Section -->
        <section id="subjects" class="section">
            <button class="back-btn" onclick="showSection('classes')">
                <i class="fas fa-arrow-left"></i> Back to Classes
            </button>
            <h2 id="currentClassTitle" style="text-align: center; margin-bottom: 1rem; color: var(--primary-blue);"></h2>
            <div class="subjects-grid" id="subjectsGrid">
                <!-- Subjects will be populated by JS -->
            </div>
        </section>

        <!-- Papers Section -->
        <section id="papers" class="section">
            <button class="back-btn" onclick="showSection('subjects')">
                <i class="fas fa-arrow-left"></i> Back to Subjects
            </button>
            <h2 id="currentSubjectTitle" style="text-align: center; margin-bottom: 1rem; color: var(--primary-blue);"></h2>
            <div class="papers-list" id="papersList">
                <!-- Papers will be populated by JS -->
            </div>
        </section>

        <!-- Search Results -->
        <section id="searchResults" class="section">
            <button class="back-btn" onclick="showSection('home')">
                <i class="fas fa-arrow-left"></i> Back to Home
            </button>
            <h2 style="text-align: center; margin-bottom: 1rem; color: var(--primary-blue);">Search Results</h2>
            <div id="searchResultsContent" class="papers-list"></div>
        </section>

        <!-- Downloads Section -->
        <section id="downloads" class="section">
            <h2 style="text-align: center; margin-bottom: 2rem; color: var(--primary-blue);">
                All Sample Papers & Solutions
            </h2>
            <div class="papers-list" id="allPapersList"></div>
        </section>

        <!-- Admin Panel -->
        <section id="admin" class="section">
            <h2 style="text-align: center; margin-bottom: 2rem; color: var(--primary-blue);">
                <i class="fas fa-upload"></i> Upload New Paper
            </h2>
            <div class="admin-panel">
                <form class="admin-form" onsubmit="uploadPaper(event)">
                    <div class="form-group">
                        <label>Paper Title</label>
                        <input type="text" id="paperTitle" required>
                    </div>
                    <div class="form-group">
                        <label>Class</label>
                        <select id="paperClass" required>
                            <option value="">Select Class</option>
                            <option value="6">Class 6</option>
                            <option value="7">Class 7</option>
                            <option value="8">Class 8</option>
                            <option value="9">Class 9</option>
                            <option value="10">Class 10</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label>Subject</label>
                        <select id="paperSubject" required>
                            <option value="">Select Subject</option>
                            <option value="Maths">Maths</option>
                            <option value="Science">Science</option>
                            <option value="English">English</option>
                            <option value="Social Science">Social Science</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label>File</label>
                        <input type="file" id="paperFile" accept=".pdf" required>
                    </div>
                    <button type="submit" class="upload-btn">
                        <i class="fas fa-cloud-upload-alt"></i> Upload Paper
                    </button>
                </form>
            </div>
        </section>

        <!-- Contact Section -->
        <section id="contact" class="section">
            <h2 style="text-align: center; margin-bottom: 2rem; color: var(--primary-blue);">
                Contact Us
            </h2>
            <div style="text-align: center; max-width: 600px; margin: 0 auto;">
                <p><i class="fas fa-envelope"></i> Email: support@studentpaperhub.com</p>
                <p><i class="fas fa-phone"></i> Phone: +91 98765 43210</p>
                <p><i class="fas fa-map-marker-alt"></i> Delhi, India</p>
                <p style="margin-top: 2rem; font-size: 0.9rem; color: var(--gray);">
                    © 2024 Student Paper Hub. All rights reserved. | For CBSE students Class 6-10
                </p>
            </div>
        </section>
    </div>

    <!-- Footer -->
    <footer class="footer">
        <div class="footer-content">
            <h3>Student Paper Hub</h3>
            <p>Empowering students with quality practice papers</p>
            <div class="social-links">
                <a href="#"><i class="fab fa-facebook"></i></a>
                <a href="#"><i class="fab fa-twitter"></i></a>
                <a href="#"><i class="fab fa-instagram"></i></a>
                <a href="#"><i class="fab fa-youtube"></i></a>
            </div>
            <p>&copy; 2024 Student Paper Hub. All rights reserved.</p>
        </div>
    </footer>

    <script>
        // Sample data
        const samplePapers = [
            { id: 1, title: "Class 10 Maths Sample Paper 2026", class: 10, subject: "Maths", type: "Paper" },
            { id: 2, title: "Class 10 Maths Solution 2026", class: 10, subject: "Maths", type: "Solution" },
            { id: 3, title: "Class 10 Science Sample Paper 2026", class: 10, subject: "Science", type: "Paper" },
            { id: 4, title: "Class 10 Science Solution 2026", class: 10, subject: "Science", type: "Solution" },
            { id: 5, title: "Class 9 English Sample Paper 2026", class: 9, subject: "English", type: "Paper" },
            { id: 6, title: "Class 8 Social Science Sample Paper 2026", class: 8, subject: "Social Science", type: "Paper" },
            { id: 7, title: "Class 7 Maths Sample Paper 2026", class: 7, subject: "Maths", type: "Paper" },
            { id: 8, title: "Class 6 Science Sample Paper 2026", class: 6, subject: "Science", type: "Paper" },
            { id: 9, title: "Class 10 Social Science Sample Paper 2026", class: 10, subject: "Social Science", type: "Paper" },
            { id: 10, title: "Class 9 Maths Solution 2026", class: 9, subject: "Maths", type: "Solution" }
        ];

        let currentClass = null;
        let currentSubject = null;

        // Initialize
        document.addEventListener('DOMContentLoaded', function() {
            showSection('home');
            populateDownloads();
            document.getElementById('notificationClose').onclick = () => {
                document.querySelector('.notification').style.display = 'none';
            };
        });

        // Navigation
        function showSection(sectionId) {
            document.querySelectorAll('.section').forEach(section => {
                section.classList.remove('active');
            });
            document.getElementById(sectionId).classList.add('active');
            
            document.querySelectorAll('.nav-link').forEach(link => {
                link.classList.remove('active');
            });
            event?.target?.classList.add('active');

            if (sectionId === 'home') {
                document.body.scrollTop = 0;
                document.documentElement.scrollTop = 0;
            }
        }

        function toggleMobileMenu() {
            const navLinks = document.getElementById('navLinks');
            navLinks.classList.toggle('active');
        }

        // Classes to Subjects
        function showSubjects(classNum) {
            currentClass = classNum;
            document.getElementById('currentClassTitle').textContent = `Class ${classNum} - Select Subject`;
            showSection('subjects');
        }

        // Subjects
        function showSubjectPapers(subject) {
            currentSubject = subject;
            document.getElementById('currentSubjectTitle').textContent = `${getClassName(currentClass)} ${subject}`;
            
            const filteredPapers = samplePapers.filter(paper => 
                paper.class === currentClass && paper.subject === subject
            );
            populatePapersList(filteredPapers);
            showSection('papers');
        }

        function getClassName(classNum) {
            return `Class ${classNum}`;
        }

        // Populate Subjects
        function populateSubjects() {
            const subjectsGrid = document.getElementById('subjectsGrid');
            const subjects = ['Maths', 'Science', 'English', 'Social Science'];
            
            subjectsGrid.innerHTML = subjects.map(subject => `
                <div class="subject-card" onclick="showSubjectPapers('${subject}')">
                    <div class="subject-icon">
                        ${getSubjectIcon(subject)}
                    </div>
                    <h3>${subject}</h3>
                    <p>Sample Papers & Solutions</p>
                </div>
            `).join('');
        }

        function getSubjectIcon(subject) {
            const icons = {
                'Maths': '<i class="fas fa-calculator"></i>',
                'Science': '<i class="fas fa-flask"></i>',
                'English': '<i class="fas fa-book"></i>',
                'Social Science': '<i class="fas fa-globe"></i>'
            };
            return icons[subject] || '<i class="fas fa-book"></i>';
        }

        // Papers List
        function populatePapersList(papers) {
            const papersList = document.getElementById('papersList');
            papersList.innerHTML = papers.map(paper => `
                <div class="paper-card">
                    <div class="paper-title">${paper.title}</div>
                    <div class="paper-meta">
                        <i class="fas fa-file-pdf"></i> PDF • ${paper.type}
                    </div>
                    <a href="#" class="download-btn" onclick="downloadPaper(event)">
                        <i class="fas fa-download"></i> Download
                    </a>
                </div>
            `).join('');
        }

        function populateDownloads() {
            const allPapersList = document.getElementById('allPapersList');
            allPapersList.innerHTML = samplePapers.map(paper => `
                <div class="paper-card">
                    <div class="paper-title">${paper.title}</div>
                    <div class="paper-meta">
                        ${getClassName(paper.class)} • ${paper.subject} • ${paper.type}
                    </div>
                    <a href="#" class="download-btn" onclick="downloadPaper(event)">
                        <i class="fas fa-download"></i> Download
                    </a>
                </div>
            `).join('');
        }

        // Search
        function performSearch() {
            const query = document.getElementById('searchInput').value.toLowerCase();
            const results = samplePapers.filter(paper => 
                paper.title.toLowerCase().includes(query) ||
                getClassName(paper.class).toLowerCase().includes(query) ||
                paper.subject.toLowerCase().includes(query)
            );

            const resultsContent = document.getElementById('searchResultsContent');
            if (results.length === 0) {
                resultsContent.innerHTML = `
                    <div class="no-results">
                        <i class="fas fa-search" style="font-size: 4rem; color: var(--gray); margin-bottom: 1rem;"></i>
                        <h3>No papers found</h3>
                        <p>Try searching with class name or subject</p>
                    </div>
                `;
            } else {
                resultsContent.innerHTML = results.map(paper => `
                    <div class="paper-card">
                        <div class="paper-title">${paper.title}</div>
                        <div class="paper-meta">
                            ${getClassName(paper.class)} • ${paper.subject} • ${paper.type}
                        </div>
                        <a href="#" class="download-btn" onclick="downloadPaper(event)">
                            <i class="fas fa-download"></i> Download
                        </a>
                    </div>
                `).join('');
            }
            showSection('searchResults');
        }

        // Download (simulated)
        function downloadPaper(event) {
            event.preventDefault();
            alert('Download started! (Demo - In real app, this would trigger PDF download)');
        }

        // Admin Upload (simulated)
        function uploadPaper(event) {
            event.preventDefault();
            alert('Paper uploaded successfully! (Demo - Form data would be sent to backend)');
            event.target.reset();
        }

        // Event Listeners
        document.getElementById('searchInput').addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                performSearch();
            }
        });

        // Auto-populate subjects when subjects section is shown
        document.getElementById('subjects').addEventListener('transitionend', function() {
            if (this.classList.contains('active') && !document.getElementById('subjectsGrid').innerHTML) {
                populateSubjects();
            }
        });
    </script>
</body>
</html>
