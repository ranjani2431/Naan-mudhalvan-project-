# Naan-mudhalvan-project-
<!DOCTYPE html>

<html>
<head>
  <meta http-equiv="CONTENT-TYPE" content="text/html; charset=UTF-8">
  <link rel="stylesheet" href="styles/style.css"/>
  <title>Hello, World!</title>
</head>
<body>
  <h1>
    Hello, World!
  </h1>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Student Grading System</title>
    <style>
        body {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
        }
        
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px 40px;
        }
        
        .page {
            display: none;
            animation: fadeIn 0.3s ease-in;
        }
        
        .page.active {
            display: block;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        /* Login Page Styles */
        .login-container {
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 20px;
        }
        
        .login-card {
            background: white;
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
            width: 100%;
            max-width: 400px;
        }
        
        .login-header {
            text-align: center;
            margin-bottom: 30px;
        }
        
        .login-header h1 {
            color: #333;
            margin: 0 0 10px 0;
            font-size: 28px;
        }
        
        .login-header p {
            color: #666;
            margin: 0;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            color: #333;
            font-weight: 500;
        }
        
        .form-group input {
            width: 100%;
            padding: 12px 16px;
            border: 2px solid #e1e5e9;
            border-radius: 10px;
            font-size: 16px;
            transition: border-color 0.3s;
            box-sizing: border-box;
        }
        
        .form-group input:focus {
            outline: none;
            border-color: #667eea;
        }
        
        .login-btn {
            width: 100%;
            padding: 14px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border: none;
            border-radius: 10px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: transform 0.2s;
        }
        
        .login-btn:hover {
            transform: translateY(-2px);
        }
        
        /* Navigation */
        .navbar {
            background: white;
            padding: 15px 0;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            margin-bottom: 30px;
            border-radius: 15px;
        }
        
        .nav-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 40px;
        }
        
        .logo {
            font-size: 24px;
            font-weight: bold;
            color: #667eea;
        }
        
        .nav-links {
            display: flex;
            gap: 25px;
        }
        
        .nav-link {
            padding: 10px 20px;
            background: #f8f9fa;
            color: #333;
            text-decoration: none;
            border-radius: 8px;
            transition: all 0.3s;
            cursor: pointer;
        }
        
        .nav-link:hover, .nav-link.active {
            background: #667eea;
            color: white;
        }
        
        .logout-btn {
            padding: 10px 20px;
            background: #dc3545;
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            transition: background 0.3s;
        }
        
        .logout-btn:hover {
            background: #c82333;
        }
        
        /* Dashboard Styles */
        .dashboard-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 30px;
            margin-bottom: 40px;
        }
        
        .stat-card {
            background: white;
            padding: 40px 30px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            text-align: center;
            transition: transform 0.3s, box-shadow 0.3s;
        }
        
        .stat-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.15);
        }
        
        .stat-number {
            font-size: 36px;
            font-weight: bold;
            color: #667eea;
            margin-bottom: 10px;
        }
        
        .stat-label {
            color: #666;
            font-size: 16px;
        }
        
        .recent-activity {
            background: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .activity-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
            border-bottom: 1px solid #eee;
        }
        
        .activity-item:last-child {
            border-bottom: none;
        }
        
        /* Grading Page Styles */
        .grading-header {
            background: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            margin-bottom: 30px;
        }
        
        .student-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 25px;
        }
        
        .student-card {
            background: white;
            padding: 25px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .student-info {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
        }
        
        .student-avatar {
            width: 50px;
            height: 50px;
            background: #667eea;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
            margin-right: 15px;
        }
        
        .grade-input {
            width: 80px;
            padding: 8px;
            border: 2px solid #e1e5e9;
            border-radius: 8px;
            text-align: center;
            margin-right: 10px;
        }
        
        .save-grade-btn {
            padding: 8px 16px;
            background: #28a745;
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            transition: background 0.3s;
        }
        
        .save-grade-btn:hover {
            background: #218838;
        }
        
        /* Skills Page Styles */
        .skills-container {
            background: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .skill-category {
            margin-bottom: 30px;
        }
        
        .skill-category h3 {
            color: #333;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid #667eea;
        }
        
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
        }
        
        .skill-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px;
            background: #f8f9fa;
            border-radius: 10px;
            transition: background 0.3s;
        }
        
        .skill-item:hover {
            background: #e9ecef;
        }
        
        .skill-progress {
            width: 100px;
            height: 8px;
            background: #e1e5e9;
            border-radius: 4px;
            overflow: hidden;
        }
        
        .skill-progress-bar {
            height: 100%;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            transition: width 0.3s;
        }
        
        .page-title {
            color: white;
            text-align: center;
            margin-bottom: 40px;
            font-size: 42px;
            font-weight: 700;
            text-shadow: 0 2px 4px rgba(0,0,0,0.3);
            letter-spacing: -1px;
        }
        
        @media (max-width: 768px) {
            .nav-content {
                flex-direction: column;
                gap: 15px;
            }
            
            .nav-links {
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .dashboard-grid {
                grid-template-columns: 1fr;
            }
            
            .student-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Login Page -->
    <div id="loginPage" class="page active">
        <div class="login-container">
            <div class="login-card">
                <div class="login-header">
                    <h1>📚 EduGrade</h1>
                    <p>Student Grading System</p>
                </div>
                <form id="loginForm">
                    <div class="form-group">
                        <label for="username">Username</label>
                        <input type="text" id="username" name="username" required>
                    </div>
                    <div class="form-group">
                        <label for="password">Password</label>
                        <input type="password" id="password" name="password" required>
                    </div>
                    <button type="submit" class="login-btn">Sign In</button>
                </form>
            </div>
        </div>
    </div>

    <!-- Dashboard Page -->
    <div id="dashboardPage" class="page">
        <nav class="navbar">
            <div class="nav-content">
                <div class="logo">📚 EduGrade</div>
                <div class="nav-links">
                    <a class="nav-link active" onclick="showPage('dashboard')">Dashboard</a>
                    <a class="nav-link" onclick="showPage('grading')">Grading</a>
                    <a class="nav-link" onclick="showPage('skills')">Skills</a>
                </div>
                <button class="logout-btn" onclick="logout()">Logout</button>
            </div>
        </nav>
        
        <div class="container">
            <h1 class="page-title">Dashboard</h1>
            
            <div class="dashboard-grid">
                <div class="stat-card">
                    <div class="stat-number">156</div>
                    <div class="stat-label">Total Students</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">23</div>
                    <div class="stat-label">Assignments</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">87%</div>
                    <div class="stat-label">Average Grade</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">12</div>
                    <div class="stat-label">Pending Reviews</div>
                </div>
            </div>
            
            <div class="recent-activity">
                <h3>Recent Activity</h3>
                <div class="activity-item">
                    <span>Sarah Johnson submitted Math Assignment #5</span>
                    <span style="color: #666;">2 hours ago</span>
                </div>
                <div class="activity-item">
                    <span>Michael Chen completed Science Quiz</span>
                    <span style="color: #666;">4 hours ago</span>
                </div>
                <div class="activity-item">
                    <span>Emma Davis improved in Problem Solving</span>
                    <span style="color: #666;">1 day ago</span>
                </div>
                <div class="activity-item">
                    <span>Alex Rodriguez submitted English Essay</span>
                    <span style="color: #666;">2 days ago</span>
                </div>
            </div>
        </div>
    </div>

    <!-- Grading Page -->
    <div id="gradingPage" class="page">
        <nav class="navbar">
            <div class="nav-content">
                <div class="logo">📚 EduGrade</div>
                <div class="nav-links">
                    <a class="nav-link" onclick="showPage('dashboard')">Dashboard</a>
                    <a class="nav-link active" onclick="showPage('grading')">Grading</a>
                    <a class="nav-link" onclick="showPage('skills')">Skills</a>
                </div>
                <button class="logout-btn" onclick="logout()">Logout</button>
            </div>
        </nav>
        
        <div class="container">
            <h1 class="page-title">Student Grading</h1>
            
            <div class="grading-header">
                <h2>Math Assignment #5 - Algebra Fundamentals</h2>
                <p>Due Date: March 15, 2024 | Total Points: 100</p>
            </div>
            
            <div class="student-grid">
                <div class="student-card">
                    <div class="student-info">
                        <div class="student-avatar">SJ</div>
                        <div>
                            <h4>Sarah Johnson</h4>
                            <p style="color: #666; margin: 0;">ID: 2024001</p>
                        </div>
                    </div>
                    <div style="display: flex; align-items: center; gap: 10px;">
                        <span>Grade:</span>
                        <input type="number" class="grade-input" value="92" min="0" max="100">
                        <button class="save-grade-btn" onclick="saveGrade('Sarah Johnson', this)">Save</button>
                    </div>
                </div>
                
                <div class="student-card">
                    <div class="student-info">
                        <div class="student-avatar">MC</div>
                        <div>
                            <h4>Michael Chen</h4>
                            <p style="color: #666; margin: 0;">ID: 2024002</p>
                        </div>
                    </div>
                    <div style="display: flex; align-items: center; gap: 10px;">
                        <span>Grade:</span>
                        <input type="number" class="grade-input" value="88" min="0" max="100">
                        <button class="save-grade-btn" onclick="saveGrade('Michael Chen', this)">Save</button>
                    </div>
                </div>
                
                <div class="student-card">
                    <div class="student-info">
                        <div class="student-avatar">ED</div>
                        <div>
                            <h4>Emma Davis</h4>
                            <p style="color: #666; margin: 0;">ID: 2024003</p>
                        </div>
                    </div>
                    <div style="display: flex; align-items: center; gap: 10px;">
                        <span>Grade:</span>
                        <input type="number" class="grade-input" value="95" min="0" max="100">
                        <button class="save-grade-btn" onclick="saveGrade('Emma Davis', this)">Save</button>
                    </div>
                </div>
                
                <div class="student-card">
                    <div class="student-info">
                        <div class="student-avatar">AR</div>
                        <div>
                            <h4>Alex Rodriguez</h4>
                            <p style="color: #666; margin: 0;">ID: 2024004</p>
                        </div>
                    </div>
                    <div style="display: flex; align-items: center; gap: 10px;">
                        <span>Grade:</span>
                        <input type="number" class="grade-input" value="78" min="0" max="100">
                        <button class="save-grade-btn" onclick="saveGrade('Alex Rodriguez', this)">Save</button>
                    </div>
                </div>
                
                <div class="student-card">
                    <div class="student-info">
                        <div class="student-avatar">JW</div>
                        <div>
                            <h4>Jessica Wilson</h4>
                            <p style="color: #666; margin: 0;">ID: 2024005</p>
                        </div>
                    </div>
                    <div style="display: flex; align-items: center; gap: 10px;">
                        <span>Grade:</span>
                        <input type="number" class="grade-input" value="91" min="0" max="100">
                        <button class="save-grade-btn" onclick="saveGrade('Jessica Wilson', this)">Save</button>
                    </div>
                </div>
                
                <div class="student-card">
                    <div class="student-info">
                        <div class="student-avatar">DL</div>
                        <div>
                            <h4>David Lee</h4>
                            <p style="color: #666; margin: 0;">ID: 2024006</p>
                        </div>
                    </div>
                    <div style="display: flex; align-items: center; gap: 10px;">
                        <span>Grade:</span>
                        <input type="number" class="grade-input" value="85" min="0" max="100">
                        <button class="save-grade-btn" onclick="saveGrade('David Lee', this)">Save</button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Skills Page -->
    <div id="skillsPage" class="page">
        <nav class="navbar">
            <div class="nav-content">
                <div class="logo">📚 EduGrade</div>
                <div class="nav-links">
                    <a class="nav-link" onclick="showPage('dashboard')">Dashboard</a>
                    <a class="nav-link" onclick="showPage('grading')">Grading</a>
                    <a class="nav-link active" onclick="showPage('skills')">Skills</a>
                </div>
                <button class="logout-btn" onclick="logout()">Logout</button>
            </div>
        </nav>
        
        <div class="container">
            <h1 class="page-title">Student Skills Assessment</h1>
            
            <div class="skills-container">
                <div class="skill-category">
                    <h3>📊 Mathematical Skills</h3>
                    <div class="skills-grid">
                        <div class="skill-item">
                            <span>Algebra</span>
                            <div class="skill-progress">
                                <div class="skill-progress-bar" style="width: 85%"></div>
                            </div>
                        </div>
                        <div class="skill-item">
                            <span>Geometry</span>
                            <div class="skill-progress">
                                <div class="skill-progress-bar" style="width: 78%"></div>
                            </div>
                        </div>
                        <div class="skill-item">
                            <span>Statistics</span>
                            <div class="skill-progress">
                                <div class="skill-progress-bar" style="width: 92%"></div>
                            </div>
                        </div>
                        <div class="skill-item">
                            <span>Calculus</span>
                            <div class="skill-progress">
                                <div class="skill-progress-bar" style="width: 67%"></div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="skill-category">
                    <h3>🔬 Science Skills</h3>
                    <div class="skills-grid">
                        <div class="skill-item">
                            <span>Physics</span>
                            <div class="skill-progress">
                                <div class="skill-progress-bar" style="width: 88%"></div>
                            </div>
                        </div>
                        <div class="skill-item">
                            <span>Chemistry</span>
                            <div class="skill-progress">
                                <div class="skill-progress-bar" style="width: 75%"></div>
                            </div>
                        </div>
                        <div class="skill-item">
                            <span>Biology</span>
                            <div class="skill-progress">
                                <div class="skill-progress-bar" style="width: 91%"></div>
                            </div>
                        </div>
                        <div class="skill-item">
                            <span>Lab Techniques</span>
                            <div class="skill-progress">
                                <div class="skill-progress-bar" style="width: 83%"></div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="skill-category">
                    <h3>📝 Language Arts</h3>
                    <div class="skills-grid">
                        <div class="skill-item">
                            <span>Reading Comprehension</span>
                            <div class="skill-progress">
                                <div class="skill-progress-bar" style="width: 94%"></div>
                            </div>
                        </div>
                        <div class="skill-item">
                            <span>Creative Writing</span>
                            <div class="skill-progress">
                                <div class="skill-progress-bar" style="width: 87%"></div>
                            </div>
                        </div>
                        <div class="skill-item">
                            <span>Grammar</span>
                            <div class="skill-progress">
                                <div class="skill-progress-bar" style="width: 89%"></div>
                            </div>
                        </div>
                        <div class="skill-item">
                            <span>Public Speaking</span>
                            <div class="skill-progress">
                                <div class="skill-progress-bar" style="width: 72%"></div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="skill-category">
                    <h3>🧠 Critical Thinking</h3>
                    <div class="skills-grid">
                        <div class="skill-item">
                            <span>Problem Solving</span>
                            <div class="skill-progress">
                                <div class="skill-progress-bar" style="width: 86%"></div>
                            </div>
                        </div>
                        <div class="skill-item">
                            <span>Analytical Thinking</span>
                            <div class="skill-progress">
                                <div class="skill-progress-bar" style="width: 81%"></div>
                            </div>
                        </div>
                        <div class="skill-item">
                            <span>Research Skills</span>
                            <div class="skill-progress">
                                <div class="skill-progress-bar" style="width: 90%"></div>
                            </div>
                        </div>
                        <div class="skill-item">
                            <span>Decision Making</span>
                            <div class="skill-progress">
                                <div class="skill-progress-bar" style="width: 77%"></div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Page navigation
        function showPage(pageName) {
            // Hide all pages
            document.querySelectorAll('.page').forEach(page => {
                page.classList.remove('active');
            });
            
            // Show selected page
            document.getElementById(pageName + 'Page').classList.add('active');
            
            // Update navigation
            document.querySelectorAll('.nav-link').forEach(link => {
                link.classList.remove('active');
            });
            
            event.target.classList.add('active');
        }
        
        // Login functionality
        document.getElementById('loginForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;
            
            if (username && password) {
                // Hide login page and show dashboard
                document.getElementById('loginPage').classList.remove('active');
                document.getElementById('dashboardPage').classList.add('active');
            } else {
                alert('Please enter both username and password');
            }
        });
        
        // Logout functionality
        function logout() {
            document.querySelectorAll('.page').forEach(page => {
                page.classList.remove('active');
            });
            document.getElementById('loginPage').classList.add('active');
            
            // Clear form
            document.getElementById('loginForm').reset();
        }
        
        // Save grade functionality
        function saveGrade(studentName, button) {
            const gradeInput = button.parentElement.querySelector('.grade-input');
            const grade = gradeInput.value;
            
            if (grade >= 0 && grade <= 100) {
                button.textContent = 'Saved!';
                button.style.background = '#28a745';
                
                setTimeout(() => {
                    button.textContent = 'Save';
                    button.style.background = '#28a745';
                }, 2000);
                
                // Show success message
                const message = document.createElement('div');
                message.textContent = `Grade ${grade} saved for ${studentName}`;
                message.style.cssText = `
                    position: fixed;
                    top: 20px;
                    right: 20px;
                    background: #28a745;
                    color: white;
                    padding: 15px 20px;
                    border-radius: 8px;
                    z-index: 1000;
                    animation: slideIn 0.3s ease-out;
                `;
                
                document.body.appendChild(message);
                
                setTimeout(() => {
                    message.remove();
                }, 3000);
            } else {
                alert('Please enter a grade between 0 and 100');
            }
        }
        
        // Add slide-in animation for notifications
        const style = document.createElement('style');
        style.textContent = `
            @keyframes slideIn {
                from {
                    transform: translateX(100%);
                    opacity: 0;
                }
                to {
                    transform: translateX(0);
                    opacity: 1;
                }
            }
        `;
        document.head.appendChild(style);
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'98532e4e41ddb0da',t:'MTc1ODg5NDEwOC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>

