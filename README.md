<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>D.R. Horizons - Auteur</title>
    <meta name="description" content="Découvrez l'univers captivant de D.R. Horizons, écrivain de thrillers psychologiques et de récits mystérieux. Soutenez son œuvre littéraire." />
    <meta property="og:title" content="D.R. Horizons - Auteur" />
    <meta property="og:description" content="Plongez dans l'univers troublant de D.R. Horizons, où rêve et réalité se confondent." />
    <meta property="og:image" content="cover.png" />
    <meta property="og:url" content="https://votre-site.com" />
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #ffffff;
            color: #333;
            text-align: center;
            margin: 0;
            padding: 0;
        }
        header {
            display: flex;
            align-items: center;
            justify-content: space-between;
            background-color: #f8f8f8;
            padding: 20px;
            font-size: 28px;
            font-weight: bold;
            flex-wrap: wrap;
        }
        nav {
            background: #444;
            padding: 10px;
        }
        nav a {
            color: white;
            text-decoration: none;
            margin: 0 15px;
            font-size: 18px;
        }
        .section {
            padding: 50px 20px;
            max-width: 800px;
            margin: auto;
        }
        .button {
            display: inline-block;
            padding: 12px 24px;
            margin-top: 20px;
            background-color: #444;
            color: white;
            text-decoration: none;
            border-radius: 5px;
            transition: 0.3s;
        }
        .button:hover {
            background-color: #666;
        }
        .photo, .book-cover {
            width: 200px;
            height: auto;
            border-radius: 5px;
            margin-bottom: 20px;
        }
        .stars {
            display: flex;
            justify-content: center;
            gap: 5px;
        }
        .star {
            font-size: 30px;
            cursor: pointer;
            color: #ccc;
            transition: 0.3s;
        }
        .star:hover, .star.active {
            color: gold;
        }
        .rating-message {
            margin-top: 10px;
            font-size: 16px;
            color: #444;
        }
        footer {
            background-color: #f8f8f8;
            padding: 15px;
            font-size: 14px;
            margin-top: 50px;
        }
        @media (max-width: 600px) {
            header {
                flex-direction: column;
                text-align: center;
            }
        }
    </style>
</head>
<body>
    <header>
        <img src="photo.jpeg" alt="Photo de l'auteur D.R. Horizons" class="photo">
        <span>D.R. Horizons - Aux frontières du réel</span>
    </header>

    <nav>
        <a href="#oeuvres">Mon Livre</a>
        <a href="#about">À propos</a>
        <a href="#contact">Contact</a>
        <a href="#don">Soutenir</a>
    </nav>
    
    <section class="section" id="oeuvres">
        <h1>Mon premier livre</h1>
        <p>Découvrez "Le Chalet des oubliés", un thriller psychologique glaçant...</p>
        <img src="cover.png" alt="Couverture du livre Le Chalet des oubliés" class="book-cover">
        <p>Bientôt disponible. Plongez dans une œuvre captivante.</p>
        <a href="https://www.amazon.com/dp/votre_livre" class="button">Acheter sur Amazon</a>
        <h3>Notez ce livre :</h3>
        <div class="stars">
            <span class="star" data-value="1">★</span>
            <span class="star" data-value="2">★</span>
            <span class="star" data-value="3">★</span>
            <span class="star" data-value="4">★</span>
            <span class="star" data-value="5">★</span>
        </div>
        <p id="rating-message" class="rating-message"></p>
    </section>
    
    <section class="section" id="about">
        <h2>À propos</h2>
        <p>D.R. Horizons est un conteur passionné par les récits à suspense...</p>
    </section>
    
    <section class="section" id="contact">
        <h2>Contact & Soutien</h2>
        <p><a href="mailto:contact@drhorizon.com" class="button">Envoyer un message</a></p>
    </section>
    
    <section class="section" id="don">
        <h2>Soutenez mon écriture</h2>
        <a href="https://paypal.me/DRHorizons?country.x=CA&locale.x=fr_CA" class="button">Faire un don</a>
    </section>
    
    <footer>
        © 2025 D.R. Horizons - Un écrivain hors limites
    </footer>

    <script>
        document.addEventListener("DOMContentLoaded", () => {
            const stars = document.querySelectorAll('.star');
            const ratingMessage = document.getElementById('rating-message');
            stars.forEach(star => {
                star.addEventListener('click', function() {
                    stars.forEach(s => s.classList.remove('active'));
                    this.classList.add('active');
                    let value = this.getAttribute('data-value');
                    ratingMessage.textContent = `Merci pour votre note : ${value} étoiles !`;
                });
            });
        });
    </script>
</body>
</html>
