# Student Activity System
Centralised digital platform for comprehensive student  activity records for HEIs 
<!DOCTYPE html>
<html lang="en">

<head>

    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Student Activity System | Login & Dashboard</title>


    <style>
        /* ==================================== */
        /* === 1. LOGIN PAGE STYLES (Initial View) */
        /* ==================================== */
        
        .login-view {
            display: flex;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            background: linear-gradient(to bottom right, #cbe7f5, #e6f3ff);
            font-family: Arial, sans-serif;
            margin: 0;
            width: 100%;
        }
        
        .login-box {
            background: rgba(255, 255, 255, 0.9);
            padding: 30px 40px;
            border-radius: 15px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
            width: 320px;
            text-align: center;
        }
        
        .login-box h2 {
            color: #1a4966;
            margin-bottom: 25px;
        }
        
        .login-box label {
            display: block;
            text-align: left;
            font-weight: bold;
            color: #20485b;
            margin-bottom: 5px;
        }
        
        .login-box input {
            width: 100%;
            padding: 12px;
            margin: 10px 0 20px;
            border: 1px solid #ccc;
            border-radius: 8px;
            font-size: 1rem;
            outline: none;
            background: rgba(255, 255, 255, 0.9);
        }
        
        .login-box input:focus {
            background: #ffffff;
            box-shadow: 0 0 5px #9ed1ff;
        }
        
        .login-box button {
            width: 100%;
            padding: 14px;
            background: #4ea8de;
            color: white;
            border: none;
            border-radius: 8px;
            font-size: 1.1rem;
            cursor: pointer;
            transition: background 0.3s ease;
        }
        
        .login-box button:hover {
            background: #3b8fc2;
        }
        
        .message {
            margin-top: 10px;
            font-weight: bold;
        }
        
        .error {
            color: #d93025;
        }
        
        .success {
            color: #188038;
        }
        /* ==================================== */
        /* === 2. DASHBOARD STYLES */
        /* ==================================== */
        
        .dashboard-view {
            display: none;
            /* Hidden by default, shown after login */
            min-height: 100vh;
            color: #333;
            background: linear-gradient(135deg, #dbeafe, #e0f2fe, #f0f9ff);
            background-attachment: fixed;
            background-size: cover;
            font-family: "Segoe UI", sans-serif;
            width: 100%;
        }
        
        .dashboard-content {
            display: flex;
            min-height: 100vh;
            padding-top: 64px;
            /* space for fixed top nav */
        }
        
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
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
        /* Re-scoped input/select/textarea to avoid conflict with login view */
        
        main input,
        main select,
        main textarea {
            width: 100%;
            padding: 8px;
            margin: 6px 0 12px;
            border: 1px solid #ccc;
            border-radius: 6px;
        }
        
        main button {
            background: #2563eb;
            color: white;
            border: none;
            padding: 8px 16px;
            border-radius: 6px;
            cursor: pointer;
            transition: 0.3s;
        }
        
        main button:hover {
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
        /* Contact area styling */
        
        .contact-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 12px
        }
        
        .contact-card {
            background: rgba(255, 255, 255, 0.9);
            padding: 12px;
            border-radius: 8px
        }
        
        .contact-form input,
        .contact-form textarea {
            width: 100%;
            padding: 8px;
            margin-top: 6px;
            border: 1px solid #cbd5e1;
            border-radius: 6px
        }
        
        .contact-form button {
            margin-top: 8px
        }
        
        @media(max-width:900px) {
            .contact-grid {
                grid-template-columns: 1fr
            }
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
        /* Top navigation bar for dashboard */
        
        .top-nav {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            background: rgba(255, 255, 255, 0.95);
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
            z-index: 120;
        }
        
        .top-nav .nav-inner {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 10px 20px;
            gap: 12px;
        }
        
        .top-nav .brand {
            font-weight: 700;
            color: #1e3a8a;
            font-size: 1.05rem;
        }
        
        .top-nav a {
            color: #1e3a8a;
            text-decoration: none;
            padding: 8px 10px;
            border-radius: 6px;
            transition: background 0.15s, color 0.15s;
        }
        
        .top-nav a:hover {
            background: #e6f0ff;
            color: #0b2a66;
        }
        /* Hamburger / overlay nav (pop-up) */
        
        .hamburger {
            display: inline-flex;
            flex-direction: column;
            gap: 4px;
            width: 28px;
            height: 22px;
            justify-content: center;
            cursor: pointer;
        }
        
        .hamburger span {
            display: block;
            height: 3px;
            background: #1e3a8a;
            border-radius: 2px;
            transition: transform 0.2s, opacity 0.2s;
        }
        
        .nav-overlay {
            position: fixed;
            inset: 0;
            background: rgba(2, 6, 23, 0.7);
            display: none;
            align-items: center;
            justify-content: center;
            z-index: 200;
        }
        
        .nav-overlay.open {
            display: flex;
        }
        
        .overlay-panel {
            background: #fff;
            width: min(480px, 92%);
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(2, 6, 23, 0.3);
        }
        
        .overlay-links {
            display: flex;
            flex-direction: column;
            gap: 10px;
            margin-top: 8px
        }
        
        .overlay-links a {
            display: block;
            padding: 10px;
            border-radius: 8px;
            text-decoration: none;
            color: #1e3a8a
        }
        
        .overlay-links a:hover {
            background: #eef4ff
        }
    </style>


    <script>
        // Hardcoded user credentials
            
        const correctUser = "student123";    
        const correctPass = "securePass!";

             // Login function with validation and message display
            
        function checkLogin() {      
            const user = document.getElementById('username').value.trim();      
            const pass = document.getElementById('password').value.trim();      
            const message = document.getElementById('message');

                  
            if (user === "" || pass === "") {        
                message.textContent = "Please fill in both fields.";        
                message.className = "message error";        
                return false;      
            }      
            if (user === correctUser && pass === correctPass) {        
                message.innerHTML = `<span class="success">Welcome ${user}!<br/>
                           You have successfully logged in.<br/>
                           Internship Status: Active<br/>
                           Participation Points: 85</span>`;        
                message.className = "message success";

                         // Show dashboard, hide login
                        
                document.getElementById('login-view').style.display = 'none';        
                document.getElementById('dashboard-view').style.display = 'block';        
                document.body.style.background = 'none';        
                return false;      
            } else {        
                message.textContent = "Invalid username or password. Please try again.";        
                message.className = "message error";        
                return false;      
            }    
        }

            
        function logout() {       // Hide dashboard, show login
                  
            document.getElementById('dashboard-view').style.display = 'none';      
            document.getElementById('login-view').style.display = 'flex';       // Reset form and message
                  
            document.getElementById("username").value = "";      
            document.getElementById("password").value = "";      
            document.getElementById("message").textContent = "";      
            document.getElementById("message").className = "message";       // Reset body background
                  
            document.body.style.background = 'linear-gradient(to bottom right, #cbe7f5, #e6f3ff)';    
        }

             // Overlay navigation controls
            
        function openNav() {      
            const o = document.getElementById('navOverlay');      
            if (o) {        
                o.classList.add('open');        
                o.setAttribute('aria-hidden', 'false');      
            }    
        }

            
        function closeNav() {      
            const o = document.getElementById('navOverlay');      
            if (o) {        
                o.classList.remove('open');        
                o.setAttribute('aria-hidden', 'true');      
            }    
        }

             // Contact form handling: save to localStorage
            
        document.addEventListener('DOMContentLoaded', function() {      
            const form = document.getElementById('contactForm');      
            if (form) {        
                form.addEventListener('submit', function(e) {          
                    e.preventDefault();          
                    const name = document.getElementById('cname').value.trim();          
                    const email = document.getElementById('cemail').value.trim();          
                    const message = document.getElementById('cmessage').value.trim();          
                    const store = JSON.parse(localStorage.getItem('contactMessages') || '[]');          
                    store.push({            
                        name,
                                    email,
                                    message,
                                    date: new Date().toISOString()          
                    });          
                    localStorage.setItem('contactMessages', JSON.stringify(store));          
                    const note = document.getElementById('cmsg');          
                    if (note) {            
                        note.style.display = 'block';          
                    }          
                    form.reset();          
                    setTimeout(() => {            
                        if (note) note.style.display = 'none';          
                    }, 4000);        
                });      
            }    
        });
    </script>
</head>

<body>

    <!-- Fixed top navigation -->

    <nav class="top-nav" role="navigation" aria-label="Top Navigation">

        <div class="nav-inner">

            <div class="brand">Student Activity System</div>

            <div style="display:flex;align-items:center;gap:12px">

                <!-- Visible links removed; navigation is available via pop-up menu -->

                <button id="hamburgerBtn" class="hamburger" aria-expanded="false" aria-label="Open menu" aria-controls="navOverlay">
                    <span></span>
                    <span></span>
                    <span></span>
                </button>
            </div>
        </div>
    </nav>


    <!-- Login view -->

    <div id="login-view" class="login-view">

        <div class="login-box">

            <h2>Login</h2>

            <form onsubmit="return checkLogin()">
                <label for="username">Username</label>                 <input type="text" id="username" placeholder="Enter username" autocomplete="username" />                 <label for="password">Password</label>                 <input type="password"
                    id="password" placeholder="Enter password" autocomplete="current-password" />                 <button type="submit">Log In</button>
                <div id="message" class="message"></div>
            </form>
        </div>
    </div>


    <!-- Dashboard view -->

    <div id="dashboard-view" class="dashboard-view">

        <div class="dashboard-content">

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

                <section id="profile">

                    <h2>🔐 Login & Profile Section</h2>

                    <div class="profile-info">

                        <div><strong>Name:</strong> rohan sahu</div>

                        <div><strong>Roll No:</strong> REC2025000</div>

                        <div><strong>Course:</strong> B.Tech Computer Science</div>

                        <div><strong>Department:</strong> CSE</div>

                        <div><strong>Year:</strong> 1st Year</div>

                        <div><strong>Email:</strong> sahurohan@university.edu</div>

                        <div><strong>Contact:</strong> +91 9876543210</div>
                    </div>
                    <button>Edit / Update Profile</button>                     <button style="background:#dc2626;" onclick="logout()">Logout</button>                 </section>


                <section id="activity-log">

                    <h2>📝 Activity Logging Module</h2>

                    <form>
                        <label>Activity Title</label>                         <input type="text" placeholder="Enter activity title" />                         <label>Type of Activity</label>                         <select>
                            <option>Academic</option>
                            <option>Co-Curricular</option>
                            <option>Extra-Curricular</option>
                            <option>Volunteer</option>
                            <option>Research</option>
                            <option>Innovation</option>
                            <option>Sports</option>
                            <option>Cultural</option>
                        </select>                         <label>Date & Duration</label>                         <input type="date" />                         <input type="text" placeholder="Duration (e.g., 2 hours)" />                         <label>Description / Learning Outcome</label>                                                <textarea rows="3" placeholder="Write details..."></textarea>                         <label>Upload Evidence</label>                         <input type="file" />                         <label>Tags / Skills</label>                                                <input type="text" placeholder="Leadership, Communication..." />                         <label>Faculty Validator</label>                         <select>
                            <option>Prof. A. Sharma</option>
                            <option>Prof. R. Nair</option>
                            <option>Prof. M. Singh</option>
                        </select>                         <button>➕ Add New Activity</button>                         <button type="button" style="background:#9ca3af;">💾 Save as Draft</button>                         <button type="button">📤 Submit for Validation</button>                                            </form>
                </section>


                <section id="records">

                    <h2>📊 My Activity Records</h2>

                    <div class="filter-bar">
                        <select>
                            <option>All Types</option>
                        </select>                         <select>
                            <option>Academic Year</option>
                        </select>                         <select>
                            <option>Status</option>
                        </select>                     </div>

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


                <section id="status">

                    <h2>🔍 Activity Status Tracking</h2>

                    <div class="notification">Hackathon 2025 – ✅ Approved by Prof. Sharma</div>

                    <div class="notification">Tech Seminar – ⏳ Under Review by Prof. Nair</div>
                </section>


                <section id="progress">

                    <h2>🗂 Categories & Progress Tracker</h2>

                    <div class="progress">

                        <div>Academic: 70%</div>

                        <div>Co-Curricular: 60%</div>

                        <div>Extra-Curricular: 45%</div>
                    </div>

                    <p>Badges Earned: 🥇 Innovation Star, 🎯 Consistent Performer</p>
                </section>


                <section id="analytics">

                    <h2>🧮 Analytics & Reports</h2>

                    <div class="chart">[Chart Placeholder: Activities per Semester]</div>

                    <div class="chart">[Chart Placeholder: Engagement by Category]</div>
                    <button>⬇ Download PDF Report</button>                     <button>⬇ Export to Excel</button>                 </section>


                <section id="feedback">

                    <h2>💬 Faculty Feedback</h2>

                    <div class="notification">Prof. Sharma commented on “Hackathon 2025”: Excellent presentation.</div>

                    <div class="notification">Prof. Nair requested resubmission for “Tech Seminar”.</div>
                </section>


                <section id="internship">

                    <h2>🎪 Student Events &amp; Functions</h2>

                    <p>Discover upcoming campus events, cultural functions and ways to participate or volunteer.</p>


                    <div style="display:grid;grid-template-columns:1fr 1fr;gap:12px;margin-top:12px;">

                        <article style="background:linear-gradient(180deg,#ffffff,#f7fbff);padding:12px;border-radius:8px;box-shadow:0 4px 12px rgba(2,6,23,0.06);">

                            <div style="font-weight:700;color:#0b3b82;margin-bottom:6px">Winter Science Symposium</div>

                            <div style="color:#0b3b82;font-size:0.95rem;margin-bottom:6px">Dec 5, 2025 · 10:00 AM - 4:00 PM</div>

                            <div style="font-size:0.95rem;margin-bottom:8px">Venue: H-Block Auditorium — Present research posters, attend lightning talks and keynote sessions.</div>

                            <div><button onclick="alert('RSVP recorded (demo)')">RSVP</button> <button style="background:transparent;color:#0b3b82;border:2px solid #0b3b82;padding:6px 10px;border-radius:6px;">Details</button></div>
                        </article>


                        <article style="background:linear-gradient(180deg,#ffffff,#f7fbff);padding:12px;border-radius:8px;box-shadow:0 4px 12px rgba(2,6,23,0.06);">

                            <div style="font-weight:700;color:#0b3b82;margin-bottom:6px">Winter Cultural Fest</div>

                            <div style="color:#0b3b82;font-size:0.95rem;margin-bottom:6px">Dec 20, 2025 · 5:00 PM - 10:00 PM</div>

                            <div style="font-size:0.95rem;margin-bottom:8px">Venue: Open-Air Amphitheatre — Music, dance, food stalls and a handicraft bazaar.</div>

                            <div><button onclick="alert('RSVP recorded (demo)')">RSVP</button> <button style="background:transparent;color:#0b3b82;border:2px solid #0b3b82;padding:6px 10px;border-radius:6px;">Tickets</button></div>
                        </article>
                    </div>


                    <div style="margin-top:14px">

                        <h3 style="margin-bottom:8px">Volunteer / Host Opportunities</h3>

                        <p style="margin-bottom:8px">Want to help run events? Sign up to volunteer — roles include stage management, hospitality, logistics and outreach.</p>
                        <button onclick="alert('Volunteer sign-up (demo)')">Sign up to Volunteer</button>                     </div>
                </section>


                <section id="research">

                    <h2>🔬 Research & Development</h2>

                    <p>Explore R&D projects, faculty-led research groups, and funding opportunities. Request to join a project or propose your idea.</p>
                    <button>Browse Projects</button>                     <button>Propose Project</button>                 </section>


                <section id="contact">

                    <h2>📞 Contact & Support</h2>

                    <div class="contact-grid">

                        <div class="contact-card">

                            <h3>Office</h3>

                            <p><strong>Student Activities Office</strong></p>

                            <p>Room 204, Administration Block</p>

                            <p><strong>Address:</strong> REC collage , College Road, City</p>

                            <p><strong>Office Hours:</strong> Mon–Fri, 9:30 AM – 5:30 PM</p>

                            <p><strong>Phone:</strong> +91 99876 43210</p>

                            <p><strong>Emergency (after hours):</strong> +91 99999 00000</p>

                            <p>
                                <strong>Social:</strong>                                 <a href="#">Twitter</a> • <a href="#">Facebook</a> • <a href="#">Instagram</a>                             </p>
                        </div>


                        <div class="contact-card contact-form">

                            <h3>Send us a message</h3>

                            <form id="contactForm">
                                <label for="cname">Name</label>                                 <input id="cname" type="text" required />                                 <label for="cemail">Email</label>                               <input id="cemail"
                                    type="email" required />                                 <label for="cmessage">Message</label>                                 <textarea id="cmessage" rows="4" required></textarea>
                                <button type="submit">Send Message</button>
                                <p id="cmsg" style="margin-top:8px;color:green;display:none">Message saved. We'll get back to you shortly.</p>
                            </form>
                        </div>
                    </div>
                </section>


                <section id="events">

                    <h2>📅 Upcoming Events / Opportunities</h2>

                    <ul>

                        <li>AI Workshop – 21 Oct 2025 <button>Register Now</button></li>

                        <li>Annual Sports Meet – 28 Oct 2025 <button>Register Now</button></li>

                        <li>National NSS Camp – Nov 2025 <button>Register Now</button></li>
                    </ul>
                </section>


                <section id="notifications">

                    <h2>🔔 Notification Center</h2>

                    <div class="notification">Your “Hackathon 2025” activity was approved ✅</div>

                    <div class="notification">System Update: Platform maintenance scheduled on 25 Oct.</div>

                    <div class="notification">Reminder: Submit your Semester Activity Report by 31 Oct.</div>
                </section>


                <section id="support">

                    <h2>🧰 Support & Help</h2>

                    <div class="support-links">
                        <a href="#">📘 User Manual</a> |                         <a href="#">🔁 Reset Password</a> |                         <a href="#">🐞 Report Issue</a>                     </div>

                    <p style="margin-top:10px;">For further assistance, email: <b>support@university.edu</b></p>
                </section>


                <section id="settings">

                    <h2>⚙ Settings & Account Management</h2>
                    <label>Change Password</label>                     <input type="password" placeholder="Enter new password" />                     <label>Notification Preferences</label>                     <select>
                        <option>Email</option>
                        <option>SMS</option>
                        <option>Both</option>
                    </select>                     <label><input type="checkbox" /> I accept the privacy policy and terms.</label>                     <button>Save Settings</button>                 </section>


                <footer>© 2025 Centralized Student Activity Platform | Designed for HEIs</footer>
            </main>
        </div>

        <!-- Overlay navigation panel -->
        <div id="navOverlay" class="nav-overlay" aria-hidden="true">
            <div class="overlay-panel" role="dialog" aria-modal="true" aria-label="Navigation menu">
                <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:8px">
                    <h3 style="margin:0;color:#1e3a8a">Menu</h3>
                    <button id="overlayClose" aria-label="Close menu" style="background:transparent;border:none;font-size:1.1rem;cursor:pointer;color:#dc2626">✕</button>
                </div>
                <div class="overlay-links">
                    <a href="#profile" onclick="closeNav()">Home</a>
                    <a href="events.html" onclick="closeNav()">Event</a>
                    <a href="functions.html" onclick="closeNav()">Function</a>
                    <a href="scholarship.html" onclick="closeNav()">Scholarship</a>
                    <a href="research.html" onclick="closeNav()">Research & Development</a>
                    <a href="internship.html" onclick="closeNav()">Internship</a>
                    <a href="#contact" onclick="closeNav()">Contact</a>
                    <a href="code1.html" onclick="closeNav()">feedback</a>
                </div>
            </div>
        </div>

        <script>
            (function() {
                const btn = document.getElementById('hamburgerBtn');
                const overlay = document.getElementById('navOverlay');
                const closeBtn = document.getElementById('overlayClose');
                const firstLink = overlay && overlay.querySelector('.overlay-links a');

                function openEnh() {
                    if (!overlay) return;
                    overlay.classList.add('open');
                    overlay.setAttribute('aria-hidden', 'false');
                    if (btn) btn.setAttribute('aria-expanded', 'true');
                    if (firstLink) firstLink.focus();
                    document.addEventListener('keydown', escHandler);
                }

                function closeEnh() {
                    if (!overlay) return;
                    overlay.classList.remove('open');
                    overlay.setAttribute('aria-hidden', 'true');
                    if (btn) btn.setAttribute('aria-expanded', 'false');
                    if (btn) btn.focus();
                    document.removeEventListener('keydown', escHandler);
                }

                function escHandler(e) {
                    if (e.key === 'Escape') closeEnh();
                }

                if (btn) {
                    btn.addEventListener('click', function() {
                        if (overlay && overlay.classList.contains('open')) closeEnh();
                        else openEnh();
                    });
                }

                if (closeBtn) closeBtn.addEventListener('click', closeEnh);

                if (overlay) overlay.addEventListener('click', function(e) {
                    if (e.target === overlay) closeEnh();
                });

                // If legacy openNav/closeNav are used elsewhere, keep them in sync
                const origOpen = window.openNav;
                const origClose = window.closeNav;
                if (typeof origOpen === 'function') window.openNav = function() {
                    openEnh();
                    origOpen();
                };
                if (typeof origClose === 'function') window.closeNav = function() {
                    closeEnh();
                    origClose();
                };
            })();
        </script>

</body>

</html>
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Animated Student Feedback</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins&display=swap');
        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #6a11cb, #2575fc);
            color: #fff;
            margin: 0;
            padding: 0;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        
        .feedback-container {
            background: rgba(255, 255, 255, 0.1);
            padding: 40px 30px;
            border-radius: 15px;
            box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
            width: 400px;
            backdrop-filter: blur(8px);
            animation: fadeInUp 1.2s ease forwards;
        }
        
        h2 {
            text-align: center;
            margin-bottom: 30px;
            font-weight: 600;
            color: #fff;
            letter-spacing: 1.2px;
            animation: colorShift 4s infinite alternate;
        }
        
        form {
            display: flex;
            flex-direction: column;
        }
        
        label {
            position: relative;
            margin-bottom: 15px;
            color: #eee;
            font-weight: 500;
            cursor: text;
            animation: fadeInLeft 1.5s ease forwards;
        }
        
        input[type="text"],
        input[type="email"],
        textarea {
            width: 100%;
            padding: 12px;
            margin-top: 8px;
            border-radius: 8px;
            border: none;
            outline: none;
            font-size: 15px;
            transition: box-shadow 0.3s ease;
        }
        
        input[type="text"]:focus,
        input[type="email"]:focus,
        textarea:focus {
            box-shadow: 0 0 8px 2px #ffd700;
            background-color: rgba(255, 255, 255, 0.15);
            color: #fff;
        }
        
        textarea {
            resize: vertical;
            min-height: 80px;
            font-family: 'Poppins', sans-serif;
        }
        
        .radio-group {
            margin-bottom: 25px;
            display: flex;
            justify-content: space-around;
            animation: fadeInRight 1.5s ease forwards;
        }
        
        .radio-group label {
            font-weight: 400;
        }
        
        .radio-group input[type="radio"] {
            margin-right: 6px;
            cursor: pointer;
        }
        
        button {
            background: #ffd700;
            border: none;
            padding: 15px 0;
            border-radius: 12px;
            font-weight: 600;
            color: #333;
            font-size: 16px;
            cursor: pointer;
            transition: background-color 0.3s ease, transform 0.3s ease;
            animation: fadeInUp 1.8s ease forwards;
        }
        
        button:hover {
            background-color: #e6c200;
            transform: scale(1.05);
        }
        
        .note {
            margin-top: 12px;
            text-align: center;
            color: #fff;
            display: none;
        }
        /* Animations */
        
        @keyframes fadeInUp {
            0% {
                opacity: 0;
                transform: translateY(20px);
            }
            100% {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes fadeInLeft {
            0% {
                opacity: 0;
                transform: translateX(-20px);
            }
            100% {
                opacity: 1;
                transform: translateX(0);
            }
        }
        
        @keyframes fadeInRight {
            0% {
                opacity: 0;
                transform: translateX(20px);
            }
            100% {
                opacity: 1;
                transform: translateX(0);
            }
        }
        
        @keyframes colorShift {
            0% {
                color: #ffd700;
            }
            50% {
                color: #fff;
            }
            100% {
                color: #ffd700;
            }
        }
    </style>
</head>

<body>
    <div class="feedback-container">
        <h2>Student Website Feedback</h2>
        <form id="feedbackForm">
            <label for="name">Name
				<input type="text" id="name" name="name" placeholder="Your name" required />
			</label>
            <label for="email">Email
				<input type="email" id="email" name="email" placeholder="Your email" required />
			</label>
            <div class="radio-group">
                <label><input type="radio" name="satisfaction" value="Yes" checked /> Satisfied</label>
                <label><input type="radio" name="satisfaction" value="No" /> Not Satisfied</label>
            </div>
            <label for="feedback">Feedback
				<textarea id="feedback" name="feedback" placeholder="Write your feedback here..." required></textarea>
			</label>
            <button type="submit">Submit Feedback</button>
            <p class="note" id="note">Thanks — your feedback was saved.</p>
        </form>
    </div>

    <script>
        (function() {
            const form = document.getElementById('feedbackForm');
            const note = document.getElementById('note');

            function saveFeedback(data) {
                const key = 'siteFeedback';
                const store = JSON.parse(localStorage.getItem(key) || '[]');
                store.push(data);
                localStorage.setItem(key, JSON.stringify(store));
            }

            form.addEventListener('submit', function(e) {
                e.preventDefault();
                const data = {
                    name: document.getElementById('name').value.trim(),
                    email: document.getElementById('email').value.trim(),
                    satisfaction: form.satisfaction.value,
                    feedback: document.getElementById('feedback').value.trim(),
                    date: new Date().toISOString()
                };

                saveFeedback(data);
                note.style.display = 'block';
                form.reset();
                setTimeout(() => note.style.display = 'none', 3500);
            });
        })();
    </script>
</body>

</html>


