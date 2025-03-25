<html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>WD_01-SURAJ</title>
    <style>
        *{
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        } 
        
        body {
            font-family: Arial,sans-serif;
            line-height: 1.6;
        }

        /*Navigation Styles */
        .navbar {
            position:fixed;
            top: 0;
            width: 100%;
            background-color: #ffffff;
            padding: 1rem;
            transition: all 0.3s ease;
            z-index: 1000;
            box-shadow: 0 2px 5px rgba(0,0,0.1);
            }

        .nav-menu {
            list-style: none;
            display: flex;
            justify-content: center;
            gap: 2rem;
        }

        .nav-item {
            position: relative;
        }

        .nav-item a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            padding: 0.5rem 1rem;
            transition: all 0.3s ease;
        }

        /*Hover Effects */
        .nav-item a:hover {
            color: #007bff;
            transform: translateY(-2px);
        }

        .nav-item::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 50%;
            background-color: #007bff;
            transition: all 0.3s ease;
        }

        .nav-item:hover::after {
            width: 100%;
            left: 0;
        }

        /*Scrolled State */
        .navbar.scrolled {
            background-color: #007bff;
            padding: 0.8rem;
        }

        .navbar.scrolled .nav-item a {
            color: #ffffff;
        }

        .navbar.scrolled .nav-item::after {
            background-color: #ffffff;
        }

        /* Content Styles (for demo) */
        .content section {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            background-color: #f5f5f5;
            margin: 2rem 0;
        }
     </style>
</head>
<body>
    <nav class="navbar">
        <ul class="nav-menu">
            <li class="nav-item"><a href="#home">Home</a></li>
            <li class="nav-item"><a href="#about">About</a></li>
            <li class="nav-item"><a href="#services">Services</a></li>
            <li class="nav-item"><a href="#contact">Contact</a></li>
        
        </ul>
    </nav>

    <!-- SAMPLE CONTENT FOR SCROLLING-->
    <div class="content">
        <section id="home"><h1>This is home tab where the main content of our website will be shown.</h1></section>
        <section id="about"><h1>This section contains the details the details of your site.</h1></section>
        <section id="services"><h1>This section contains the services which our organisation offers.</h1></section>
        <section id="contact"><h1>Here, the contact details of our organisation will be shown with the help of, customers can reach to us.</h1></section>
        </div>

<script>
        document.addEventListener('DOMContentLoaded', () => {
            const navbar = document.querySelector('.navbar');

            //Handle scroll Effect
            window.addEventListener('scroll', () => {
                if (window.scrollY > 50) {
                    navbar.classList.add('scrolled');
                } else {
                    navbar.classlist.remove('scrolled');
                }
            });

            //Smooth scrolling for new links
            const navLinks = documents.querySelectorAll('.nav-item a');
            navLinks.forEach(link => {
                link.addEventListener('click', (e) => {
                    e.preventDefault();
                    const targetId = link.getAttribute('href');
                    const targetSection = document.querySelector(targetId);

                    targetSection.scrollIntoview({
                        behaviour:'smooth',
                        block: 'start'
                    });
                });
            });
        });
</script>
</body>
</html>
