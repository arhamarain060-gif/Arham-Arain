<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Phone Number Tracking Device</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            margin: 0;
            padding: 0;
        }

        header {
            background-color: #4CAF50;
            color: #fff;
            padding: 20px;
            text-align: center;
        }

        nav ul {
            list-style: none;
            margin: 10px 0 0 0;
            padding: 0;
        }

        nav ul li {
            display: inline;
            margin-right: 10px;
        }

        nav ul li a {
            color: #fff;
            text-decoration: none;
            font-weight: bold;
        }

        section {
            max-width: 800px;
            margin: 20px auto;
            padding: 20px;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        footer {
            background-color: #4CAF50;
            color: #fff;
            padding: 20px;
            text-align: center;
        }

        button {
            padding: 10px 20px;
            background-color: #4CAF50;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        button:hover {
            background-color: #3e8e41;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 10px;
        }

        table, th, td {
            border: 1px solid #ddd;
        }

        th {
            background-color: #f0f0f0;
            padding: 10px;
            text-align: left;
        }

        td {
            padding: 10px;
        }

        textarea {
            width: 100%;
            height: 100px;
            resize: vertical;
        }

        input, textarea {
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            margin-bottom: 10px;
        }

        h1, h2 {
            color: #333;
        }
    </style>
</head>
<body>
    <header>
        <h1>Phone Number Tracking Device</h1>
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#track">Track</a></li>
                <li><a href="#features">Features</a></li>
                <li><a href="#pricing">Pricing</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <section id="home">
        <h2>Welcome to Phone Number Tracking Device</h2>
        <p>Our device allows you to track the location of any phone number in the world.</p>
    </section>

    <section id="track">
        <h2>Track Phone Number</h2>
        <form id="track-form">
            <label for="phone-number">Enter phone number:</label>
            <input type="text" id="phone-number" name="phone-number" placeholder="+92xxxxxxxxxx" required>
            <button type="submit">Track</button>
        </form>
        <div id="result"></div>
    </section>

    <section id="features">
        <h2>Features</h2>
        <ul>
            <li>Real-time tracking</li>
            <li>Accurate location data</li>
            <li>Easy to use interface</li>
            <li>Secure and reliable</li>
        </ul>
    </section>

    <section id="pricing">
        <h2>Pricing</h2>
        <table>
            <tr>
                <th>Plan</th>
                <th>Price</th>
                <th>Features</th>
            </tr>
            <tr>
                <td>Basic</td>
                <td>$19.99/month</td>
                <td>Real-time tracking, accurate location data</td>
            </tr>
            <tr>
                <td>Premium</td>
                <td>$39.99/month</td>
                <td>All Basic plan features, additional analytics, customizable interface</td>
            </tr>
        </table>
    </section>

    <section id="contact">
        <h2>Contact Us</h2>
        <form id="contact-form">
            <label for="name">Name:</label>
            <input type="text" id="name" name="name" placeholder="Your name" required>

            <label for="email">Email:</label>
            <input type="email" id="email" name="email" placeholder="your@email.com" required>

            <label for="message">Message:</label>
            <textarea id="message" name="message" placeholder="Write your message here..." required></textarea>

            <button type="submit">Send</button>
        </form>
    </section>

    <footer>
        <p>&copy; 2025 Phone Number Tracking Device. All rights reserved.</p>
    </footer>

    <script>
        const trackForm = document.getElementById('track-form');
        const resultDiv = document.getElementById('result');
        const contactForm = document.getElementById('contact-form');

        // Fake tracking (demo only)
        trackForm.addEventListener('submit', (event) => {
            event.preventDefault();
            const phoneNumber = document.getElementById('phone-number').value;
            resultDiv.innerHTML = `<p>Tracking ${phoneNumber}...</p>`;

            // Simulate tracking response
            setTimeout(() => {
                resultDiv.innerHTML = `
                    <p><strong>Phone Number:</strong> ${phoneNumber}</p>
                    <p><strong>Location:</strong> Karachi, Pakistan</p>
                    <p><strong>Carrier:</strong> Jazz</p>
                    <p><strong>Status:</strong> Active</p>
                `;
            }, 1500);
        });

        // Contact form
        contactForm.addEventListener('submit', async (event) => {
            event.preventDefault();
            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;
            const message = document.getElementById('message').value;

            // Fake form sending
            setTimeout(() => {
                alert(`Thank you ${name}! Your message has been sent successfully.`);
                contactForm.reset();
            }, 1000);
        });
    </script>
</body>
</html>
