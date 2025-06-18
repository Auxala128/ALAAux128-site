from zipfile import ZipFile
from pathlib import Path

# Define the directory and HTML content
output_dir = Path("ala_unit_128_site")
output_dir.mkdir(parents=True, exist_ok=True)

html_content = """<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Bernard L. Tobin Unit 128 | American Legion Auxiliary</title>
  <style>
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      margin: 0;
      padding: 0;
      background-color: #f4f7f9;
      color: #2a2a2a;
    }
    header {
      background-color: #1e3d59;
      color: white;
      padding: 20px;
      text-align: center;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-wrap: wrap;
    }
    header img {
      max-height: 80px;
      margin-right: 20px;
    }
    nav {
      background-color: #41729f;
      padding: 10px;
      text-align: center;
    }
    nav a {
      color: white;
      text-decoration: none;
      margin: 0 15px;
      font-weight: bold;
    }
    section {
      padding: 40px 20px;
      max-width: 1000px;
      margin: auto;
    }
    .card {
      background: #ffffff;
      padding: 25px;
      border-radius: 10px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
      margin-bottom: 30px;
    }
    h1, h2 {
      color: #1e3d59;
    }
    .contact-info {
      line-height: 1.8;
    }
    .btn {
      display: inline-block;
      background-color: #41729f;
      color: white;
      padding: 10px 20px;
      border-radius: 5px;
      text-decoration: none;
      font-weight: bold;
    }
    iframe {
      border-radius: 8px;
    }
    footer {
      background-color: #1e3d59;
      color: white;
      text-align: center;
      padding: 15px;
    }
  </style>
</head>
<body>
<header>
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/49/American_Legion_Auxiliary_Logo.svg/1200px-American_Legion_Auxiliary_Logo.svg.png" alt="American Legion Auxiliary Logo" />
  <div>
    <h1>American Legion Auxiliary</h1>
    <h2>Bernard L. Tobin Unit 128 - Department of Maryland</h2>
  </div>
</header>
<nav>
  <a href="#about">About</a>
  <a href="#mission">Mission</a>
  <a href="#events">Events</a>
  <a href="#contact">Contact</a>
</nav>
<section id="about">
  <div class="card">
    <h2>Welcome to Unit 128</h2>
    <p>We proudly support our veterans, active-duty military, and their families through service, volunteerism, and outreach in the local community of Bernard L. Tobin Unit 128.</p>
  </div>
</section>
<section id="mission">
  <div class="card">
    <h2>Our Mission</h2>
    <p>The American Legion Auxiliary is dedicated to supporting The American Legion and honoring the sacrifice of those who serve by enhancing the lives of our veterans, military, and their families through meaningful service and programs.</p>
  </div>
</section>
<section id="events">
  <div class="card">
    <h2>Upcoming Events</h2>
    <ul>
      <li><strong>July 4, 2025:</strong> Independence Day Parade & Community BBQ</li>
      <li><strong>August 15, 2025:</strong> Back-to-School Supplies Drive</li>
      <li><strong>November 11, 2025:</strong> Veterans Day Ceremony & Luncheon</li>
    </ul>
  </div>
</section>
<section id="contact">
  <div class="card">
    <h2>Contact Us</h2>
    <div class="contact-info">
      <p><strong>Bernard L. Tobin Unit 128</strong><br>
      Department of Maryland, American Legion Auxiliary</p>
      <p>Email: <a href="mailto:info@alaunit128.org">info@alaunit128.org</a></p>
      <p>Address:<br>
      44 N. Parke Street<br>
      Aberdeen, MD 21001</p>
      <p>Follow us: 
        <a href="#">Facebook</a> | 
        <a href="#">Instagram</a>
      </p>
    </div>
    <p style="margin-top: 15px;">
      <a href="https://www.google.com/maps/dir/?api=1&destination=44+N+Parke+Street,+Aberdeen,+MD+21001" 
         target="_blank" 
         class="btn">
        📍 Get Directions
      </a>
    </p>
    <div style="margin-top: 20px;">
      <iframe 
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3068.4710300088434!2d-76.16891712413458!3d39.511630709209464!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x89c81c2295f2c7c3%3A0x2d22979ac474129e!2s44%20N%20Parke%20St%2C%20Aberdeen%2C%20MD%2021001%2C%20USA!5e0!3m2!1sen!2sus!4v1718740307293!5m2!1sen!2sus" 
        width="100%" 
        height="350" 
        allowfullscreen="" 
        loading="lazy" 
        referrerpolicy="no-referrer-when-downgrade">
      </iframe>
    </div>
  </div>
</section>
<footer>
  <p>&copy; 2025 Bernard L. Tobin Unit 128, American Legion Auxiliary, Department of Maryland. All rights reserved.</p>
</footer>
</body>
</html>
"""

# Write the HTML file
(output_dir / "index.html").write_text(html_content, encoding="utf-8")

# Create ZIP archive
with ZipFile("ALA_Unit_128_Website.zip", "w") as zipf:
    zipf.write(output_dir / "index.html", arcname="index.html")

print("Website zipped successfully as 'ALA_Unit_1
