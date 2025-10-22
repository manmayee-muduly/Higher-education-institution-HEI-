# Higher-education-institution-HEI-
Centralised digital platform for comprehensive student  activity records for HEIs 
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login Page</title>

    <style>
        body {
            font-family: Arial, sans-serif;
            background: linear-gradient(to bottom right, #cbe7f5, #e6f3ff);
            height: 100vh;
            margin: 0;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .login-box {
            background: rgba(255, 255, 255, 0.4);
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
            width: 320px;
            text-align: center;
        }
        
        h2 {
            color: #1a4966;
            margin-bottom: 25px;
        }
        
        label {
            display: block;
            text-align: left;
            font-weight: bold;
            color: #20485b;
            margin-bottom: 5px;
        }
        
        input {
            width: 100%;
            padding: 8px 10px;
            margin-bottom: 15px;
            border: none;
            border-radius: 8px;
            background: rgba(255, 255, 255, 0.9);
            outline: none;
            font-size: 14px;
        }
        
        input:focus {
            background: #ffffff;
            box-shadow: 0 0 5px #9ed1ff;
        }
        
        button {
            width: 100%;
            padding: 10px;
            background-color: #4ea8de;
            color: white;
            border: none;
            border-radius: 8px;
            font-size: 15px;
            cursor: pointer;
            transition: 0.3s;
        }
        
        button:hover {
            background-color: #3b8fc2;
        }
        
        .note {
            margin-top: 15px;
            color: #1a4966;
            font-size: 14px;
        }
    </style>

    <script>
        function login(event) {
            event.preventDefault(); // Prevent form refresh

            const username = document.getElementById("username").value.trim();
            const password = document.getElementById("password").value.trim();

            // Simple example check
            if (username && password) {
                // Redirect to another page
                window.location.href = "hackathon2.html";
            } else {
                alert("Please enter both username and password.");
            }
        }
    </script>
</head>

<body>
    <div class="login-box">
        <h2>Login</h2>
        <form onsubmit="login(event)">
            <label for="username">Username</label>
            <input type="text" id="username" placeholder="Enter username" required>

            <label for="password">Password</label>
            <input type="password" id="password" placeholder="Enter password" required>
            <label for="contact ">contact</label>
            <input type="contact " name=" contact " id=" contact details " placeholder="ebter your contact details  " required>

            <button type=" submit ">Login</button>
        </form>

        <div class="note ">
            <p>Hint: Username = <b>any alphabet</b> | Password = <b>any number</b></p>
        </div>
    </div>
</body>

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Student Dashboard | Activity Record System</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: "Segoe UI", sans-serif;
        }
        /* 🌨 Winter Chill Background */
        
        body {
            display: flex;
            min-height: 100vh;
            color: #333;
            background: linear-gradient(135deg, #dbeafe, #e0f2fe, #f0f9ff);
            background-attachment: fixed;
            background-size: cover;
        }
        /* Sidebar */
        
        aside {
            width: 250px;
            background: rgba(30, 58, 138, 0.9);
            color: white;
            height: 100vh;
            padding: 20px;
            position: fixed;
            backdrop-filter: blur(6px);
            box-shadow: 2px 0 10px rgba(0, 0, 0, 0.2);
        }
        
        aside h2 {
            font-size: 20px;
            margin-bottom: 15px;
            text-align: center;
        }
        
        aside ul {
            list-style: none;
        }
        
        aside ul li {
            margin: 10px 0;
        }
        
        aside ul li a {
            color: white;
            text-decoration: none;
            display: block;
            padding: 8px 10px;
            border-radius: 6px;
            transition: background 0.3s;
        }
        
        aside ul li a:hover {
            background: rgba(37, 99, 235, 0.9);
        }
        /* Main Area */
        
        main {
            margin-left: 270px;
            padding: 20px;
            width: calc(100% - 270px);
        }
        /* Frosted Glass Section Styling ❄ */
        
        section {
            background: rgba(255, 255, 255, 0.8);
            padding: 20px;
            border-radius: 12px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            margin-bottom: 20px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.4);
        }
        
        h2 {
            margin-bottom: 10px;
            color: #1e3a8a;
        }
        
        h3 {
            color: #2563eb;
            margin-top: 10px;
        }
        
        .profile-info div {
            margin-bottom: 6px;
        }
        
        input,
        select,
        textarea {
            width: 100%;
            padding: 8px;
            margin: 6px 0 12px;
            border: 1px solid #ccc;
            border-radius: 6px;
        }
        
        button {
            background: #2563eb;
            color: white;
            border: none;
            padding: 8px 16px;
            border-radius: 6px;
            cursor: pointer;
            transition: 0.3s;
        }
        
        button:hover {
            background: #1e40af;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 10px;
        }
        
        th,
        td {
            border: 1px solid #ccc;
            padding: 8px;
            text-align: left;
        }
        
        th {
            background: #e2e8f0;
        }
        
        .filter-bar {
            display: flex;
            gap: 10px;
            margin-top: 10px;
        }
        
        .progress {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
        }
        
        .progress div {
            flex: 1;
            background: rgba(226, 232, 240, 0.8);
            border-radius: 6px;
            padding: 10px;
        }
        
        .chart {
            height: 150px;
            background: rgba(241, 245, 249, 0.7);
            border-radius: 8px;
            margin-top: 10px;
            backdrop-filter: blur(8px);
        }
        
        .notification {
            background: rgba(254, 249, 195, 0.8);
            padding: 10px;
            border-radius: 8px;
            margin: 6px 0;
        }
        
        .support-links a {
            color: #2563eb;
            text-decoration: none;
        }
        
        footer {
            text-align: center;
            font-size: 13px;
            color: #555;
            margin-top: 20px;
        }
    </style>
</head>

<body>

    <aside>
        <h2>🎓 Student Panel</h2>
        <ul>
            <li><a href="#profile">Profile</a></li>
            <li><a href="#activity-log">Log Activity</a></li>
            <li><a href="#records">My Records</a></li>
            <li><a href="#status">Status Tracking</a></li>
            <li><a href="#progress">Progress Tracker</a></li>
            <li><a href="#analytics">Analytics & Reports</a></li>
            <li><a href="#feedback">Faculty Feedback</a></li>
            <li><a href="#events">Upcoming Events</a></li>
            <li><a href="#notifications">Notifications</a></li>
            <li><a href="#support">Support & Help</a></li>
            <li><a href="#settings">Settings</a></li>
        </ul>
    </aside>

    <main>
        <!-- Profile -->
        <section id="profile">
            <h2>🔐 Login & Profile Section</h2>
            <div class="profile-info">
                <div><strong>Name:</strong> John Doe</div>
                <div><strong>Roll No:</strong> 2025CS001</div>
                <div><strong>Course:</strong> B.Tech Computer Science</div>
                <div><strong>Department:</strong> CSE</div>
                <div><strong>Year:</strong> 3rd Year</div>
                <div><strong>Email:</strong> johndoe@university.edu</div>
                <div><strong>Contact:</strong> +91 9876543210</div>
            </div>
            <button>Edit / Update Profile</button>
            <button style="background:#dc2626;">Logout</button>
        </section>

        <!-- Activity Logging -->
        <section id="activity-log">
            <h2>📝 Activity Logging Module</h2>
            <form>
                <label>Activity Title</label>
                <input type="text" placeholder="Enter activity title">
                <label>Type of Activity</label>
                <select>
        <option>Academic</option><option>Co-Curricular</option><option>Extra-Curricular</option>
        <option>Volunteer</option><option>Research</option><option>Innovation</option>
        <option>Sports</option><option>Cultural</option>
      </select>
                <label>Date & Duration</label>
                <input type="date">
                <input type="text" placeholder="Duration (e.g., 2 hours)">
                <label>Description / Learning Outcome</label>
                <textarea rows="3" placeholder="Write details..."></textarea>
                <label>Upload Evidence</label>
                <input type="file">
                <label>Tags / Skills</label>
                <input type="text" placeholder="Leadership, Communication...">
                <label>Faculty Validator</label>
                <select>
        <option>Prof. A. Sharma</option><option>Prof. R. Nair</option><option>Prof. M. Singh</option>
      </select>
                <button>➕ Add New Activity</button>
                <button type="button" style="background:#9ca3af;">💾 Save as Draft</button>
                <button type="button">📤 Submit for Validation</button>
            </form>
        </section>

        <!-- Records -->
        <section id="records">
            <h2>📊 My Activity Records</h2>
            <div class="filter-bar">
                <select><option>All Types</option></select>
                <select><option>Academic Year</option></select>
                <select><option>Status</option></select>
            </div>
            <table>
                <tr>
                    <th>Activity Name</th>
                    <th>Type</th>
                    <th>Date</th>
                    <th>Status</th>
                    <th>Faculty Remarks</th>
                    <th>Points</th>
                </tr>
                <tr>
                    <td>Hackathon 2025</td>
                    <td>Innovation</td>
                    <td>2025-08-12</td>
                    <td>Approved</td>
                    <td>Excellent work</td>
                    <td>20</td>
                </tr>
                <tr>
                    <td>Tech Seminar</td>
                    <td>Academic</td>
                    <td>2025-06-21</td>
                    <td>Pending</td>
                    <td>–</td>
                    <td>–</td>
                </tr>
            </table>
        </section>

        <!-- Status -->
        <section id="status">
            <h2>🔍 Activity Status Tracking</h2>
            <div class="notification">Hackathon 2025 – ✅ Approved by Prof. Sharma</div>
            <div class="notification">Tech Seminar – ⏳ Under Review by Prof. Nair</div>
        </section>

        <!-- Progress -->
        <section id="progress">
            <h2>🗂 Categories & Progress Tracker</h2>
            <div class="progress">
                <div>Academic: 70%</div>
                <div>Co-Curricular: 60%</div>
                <div>Extra-Curricular: 45%</div>
            </div>
            <p>Badges Earned: 🥇 Innovation Star, 🎯 Consistent Performer</p>
        </section>

        <!-- Analytics -->
        <section id="analytics">
            <h2>🧮 Analytics & Reports</h2>
            <div class="chart">[Chart Placeholder: Activities per Semester]</div>
            <div class="chart">[Chart Placeholder: Engagement by Category]</div>
            <button>⬇ Download PDF Report</button>
            <button>⬇ Export to Excel</button>
        </section>

        <!-- Feedback -->
        <section id="feedback">
            <h2>💬 Faculty Feedback</h2>
            <div class="notification">Prof. Sharma commented on “Hackathon 2025”: Excellent presentation.</div>
            <div class="notification">Prof. Nair requested resubmission for “Tech Seminar”.</div>
        </section>

        <!-- Events -->
        <section id="events">
            <h2>📅 Upcoming Events / Opportunities</h2>
            <ul>
                <li>AI Workshop – 21 Oct 2025 <button>Register Now</button></li>
                <li>Annual Sports Meet – 28 Oct 2025 <button>Register Now</button></li>
                <li>National NSS Camp – Nov 2025 <button>Register Now</button></li>
            </ul>
        </section>

        <!-- Notifications -->
        <section id="notifications">
            <h2>🔔 Notification Center</h2>
            <div class="notification">Your “Hackathon 2025” activity was approved ✅</div>
            <div class="notification">System Update: Platform maintenance scheduled on 25 Oct.</div>
            <div class="notification">Reminder: Submit your Semester Activity Report by 31 Oct.</div>
        </section>

        <!-- Support -->
        <section id="support">
            <h2>🧰 Support & Help</h2>
            <div class="support-links">
                <a href="#">📘 User Manual</a> |
                <a href="#">🔁 Reset Password</a> |
                <a href="#">🐞 Report Issue</a>
            </div>
            <p style="margin-top:10px;">For further assistance, email: <b>support@university.edu</b></p>
        </section>

        <!-- Settings -->
        <section id="settings">
            <h2>⚙ Settings & Account Management</h2>
            <label>Change Password</label>
            <input type="password" placeholder="Enter new password">
            <label>Notification Preferences</label>
            <select><option>Email</option><option>SMS</option><option>Both</option></select>
            <label><input type="checkbox"> I accept the privacy policy and terms.</label>
            <button>Save Settings</button>
        </section>

        <footer>© 2025 Centralized Student Activity Platform | Designed for HEIs</footer>
    </main>
    <li><a href="test3.html">Upcoming Events</a></li>


</body>
</html> 

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Student News & Updates</title>
<style>
  body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background: linear-gradient(135deg, #74ebd5, #ACB6E5);
    margin: 0;
    padding: 20px;
    color: #333;
  }
  header {
    text-align: center;
    padding: 40px 0 20px 0;
    color: #4a148c;
    font-size: 2.8rem;
    font-weight: 700;
    animation: fadeInDown 1.2s ease forwards;
  }
  @keyframes fadeInDown {
    from {
      opacity: 0;
      transform: translateY(-50px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
  .news-container {
    max-width: 900px;
    margin: auto;
  }
  .news-item {
    background: white;
    border-radius: 15px;
    box-shadow: 0 6px 15px rgba(74,20,140,0.2);
    margin-bottom: 30px;
    overflow: hidden;
    transform: translateY(50px);
    opacity: 0;
    animation: slideUpFade 1s ease forwards;
  }
  .news-item:nth-child(1) {
    animation-delay: 0.2s;
  }
  .news-item:nth-child(2) {
    animation-delay: 0.4s;
  }
  .news-item:nth-child(3) {
    animation-delay: 0.6s;
  }
  @keyframes slideUpFade {
    to {
      transform: translateY(0);
      opacity: 1;
    }
  }
  .news-header {
    background: linear-gradient(135deg, #6a11cb, #2575fc);
    padding: 15px 25px;
    color: white;
    font-weight: 700;
    font-size: 1.4rem;
  }
  .news-body {
    padding: 20px 25px;
    font-size: 1.1rem;
    line-height: 1.6;
    color: #444;
  }
  .news-footer {
    background: #f3f3f3;
    padding: 15px 25px;
    font-size: 0.9rem;
    color: #777;
    font-style: italic;
  }
  a.read-more {
    display: inline-block;
    margin-top: 10px;
    font-weight: 600;
    color: #6a11cb;
    text-decoration: none;
    transition: color 0.3s ease;
  }
  a.read-more:hover {
    color: #2575fc;
    text-decoration: underline;
  }
</style>
</head>
<body>

<header>Student News & Important Updates</header>

<div class="news-container">
  <article class="news-item">
    <div class="news-header">Campus Reopens with New Safety Protocols</div>
    <div class="news-body">
      The university campus will reopen on November 1st, 2025, with enhanced safety measures including mandatory masks in all indoor areas and frequent sanitization stations. Stay tuned for detailed guidelines.
      <br /><a href="#" class="read-more">Read More</a>
    </div>
    <div class="news-footer">Posted on October 20, 2025</div>
  </article>

  <article class="news-item">
    <div class="news-header">Internship Opportunities Openings for Fall 2025</div>
    <div class="news-body">
      Exciting internship opportunities from top tech and finance companies are now available. Visit the career portal to apply before the deadline on November 15th.
      <br /><a href="#" class="read-more">Read More</a>
    </div>
    <div class="news-footer">Posted on October 18, 2025</div>
  </article>

  <article class="news-item">
    <div class="news-header">New Online Workshops for Skill Development</div>
    <div class="news-body">
      Sign up for free online workshops covering topics like data science, creative writing, and digital marketing. Sessions start from November 5th. Seats are limited.
      <br /><a href="#" class="read-more">Read More</a>
    </div>
    <div class="news-footer">Posted on October 15, 2025</div>
  </article>
</div>

</body>
</html>
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width,initial-scale=1">
    <title>Internships | Student Activity System</title>
    <style>
        body {
            font-family: Segoe UI, Arial, sans-serif;
            margin: 0;
            background: linear-gradient(135deg, #f0f8ff, #e6f3ff);
            color: #04293a
        }
        
        header {
            background: #1e3a8a;
            color: #fff;
            padding: 18px;
            text-align: center;
            font-size: 1.4rem
        }
        
        .container {
            max-width: 900px;
            margin: 24px auto;
            padding: 0 16px
        }
        
        .card {
            background: #fff;
            padding: 16px;
            border-radius: 10px;
            box-shadow: 0 6px 18px rgba(2, 6, 23, 0.06);
            margin-bottom: 16px
        }
        
        .role {
            font-weight: 700;
            color: #0b3b82
        }
        
        .details {
            color: #064679;
            margin-top: 6px
        }
        
        .apply {
            display: inline-block;
            padding: 8px 12px;
            background: #2563eb;
            color: #fff;
            border-radius: 8px;
            text-decoration: none
        }
    </style>
</head>

<body>
    <header>Internship Opportunities</header>
    <div class="container">
        <section class="card">
            <div class="role">Frontend Development Intern — ABC Tech</div>
            <div class="details">Duration: 3 months · Stipend: ₹10,000/month · Skills: HTML/CSS/JS, React</div>
            <p>Work on responsive UI components and college-facing portals. Mentored by senior devs.</p>
            <a class="apply" href="#" onclick="alert('Apply (demo)')">Apply</a>
        </section>

        <section class="card">
            <div class="role">Data Science Intern — Data Labs</div>
            <div class="details">Duration: 6 months · Stipend: ₹15,000/month · Skills: Python, Pandas, ML</div>
            <p>Assist in data cleaning, model training and dashboard development for partner NGOs.</p>
            <a class="apply" href="#" onclick="alert('Apply (demo)')">Apply</a>
        </section>

        <section class="card">
            <h3>How to prepare</h3>
            <ul>
                <li>Update your resume and GitHub/portfolio links</li>
                <li>Prepare a short project summary to share with recruiters</li>
                <li>Attend campus mock interviews and resume workshops</li>
            </ul>
        </section>

        <p style="text-align:center;color:#064679">&copy; 2025 Student Activity Platform</p>
    </div>
</body>

</html>
<html>
    <body>
<!-- Overlay navigation panel -->
    <div id="navOverlay" class="nav-overlay" aria-hidden="true">
        <div class="overlay-panel" role="dialog" aria-modal="true" aria-label="Navigation menu">
            <h3 style="margin:0 0 8px 0;color:#1e3a8a">Menu</h3>
            <div class="overlay-links">
                <a href="#profile" onclick="closeNav()">Home</a>
                <a href="events.html" onclick="closeNav()">Event</a>
                <a href="functions.html" onclick="closeNav()">Function</a>
                <a href="internship.html" onclick="closeNav()">Internship</a>
                <a href="research.html" onclick="closeNav()">Research & Development</a>
                <a href="scholarship.html" onclick="closeNav()">Scholarship</a>
                <a href="#contact" onclick="closeNav()">Contact</a>
                <a href="#" onclick="closeNav()" style="color:#dc2626">Close</a>
            </div>
        </div>
    </div>
</body>

</html>

