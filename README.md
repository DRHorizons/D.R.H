<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>D.R. Horizons - Auteur</title>
    <meta name="description" content="Découvrez l'univers captivant de D.R. Horizons, écrivain de thrillers psychologiques et de récits mystérieux. Soutenez son œuvre littéraire.">
    <meta name="keywords" content="Thriller psychologique, Roman Thriller, Thriller au Vermont, Chalet des oubliés, Roman Chalet, Roman séquestration, Suspense intense, Roman à suspense, Mystère psychologique, Thème de la domination">
    <link rel="stylesheet" href="styles.css">
    <style>
        body { font-family: Arial, sans-serif; margin: 0; padding: 0; text-align: center; }
        nav { background: #222; padding: 15px; }
        nav a { color: white; text-decoration: none; font-size: 20px; margin: 0 20px; font-weight: bold; transition: color 0.3s ease; }
        nav a:hover { color: #ff8c00; }
        .big-button { display: inline-block; background-color: #ff8c00; color: white; padding: 15px 30px; font-size: 18px; text-decoration: none; font-weight: bold; border-radius: 5px; margin: 15px 0; transition: background 0.3s; }
        .big-button:hover { background-color: #e07b00; }
        .bio-container { display: flex; align-items: center; justify-content: center; margin: 40px auto; max-width: 900px; text-align: left; }
        .photo { width: 250px; border-radius: 10px; margin-right: 30px; }
        .bio-text { font-family: 'Dancing Script', cursive; font-size: 22px; font-style: italic; max-width: 500px; }
        .bio-text::before { content: '"'; font-size: 30px; color: #ff8c00; }
        .bio-text::after { content: '"'; font-size: 30px; color: #ff8c00; }
    </style>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@400;700&display=swap" rel="stylesheet">
</head>
<body>
    <nav>
        <a href="#">Accueil</a>
        <a href="#">À propos</a>
        <a href="#">Œuvres</a>
        <a href="#">Contact</a>
    </nav>
    <div class="bio-container">
        <img src="photo.jpeg" alt="Portrait de l'écrivain D.R. Horizons" class="photo">
        <p class="bio-text">
            D.R. Horizons est un explorateur de l’imaginaire, un conteur aux mille facettes, porté par une soif d’aventure et une curiosité insatiable pour l’âme humaine. Écrivain atypique, il puise dans sa liberté de pensée et son goût pour la psychologie pour tisser des récits où le mystère flirte avec l’émotion, et où chaque détail a son importance. Installé à Montréal, une ville vibrante qui cultive l’ouverture d’esprit et la diversité des idées, il trouve dans ses rues, ses contrastes et son énergie créative une source d’inspiration inépuisable. L’écriture est pour lui une passion, un espace où il donne libre cours à son imagination débordante, façonnant des univers envoûtants où rien n’est jamais tout à fait ce qu’il semble être.
        </p>
    </div>
    <nav>
        <a href="#oeuvres">Mon Livre</a>
        <a href="#about">À propos</a>
        <a href="#contact">Contact</a>
        <a href="#don">Soutenir</a>
    </nav>
    <section class="section" id="oeuvres">
        <h1>Mon premier livre</h1>
        <p>Après des vacances paradisiaques au Mexique, Chloé et Madison, deux amies inséparables, rentrent à Montréal, prêtes à reprendre leur routine. Mais une rencontre inattendue va bouleverser le cours des choses. Charles, un homme charismatique et mystérieux, croise le chemin de Chloé et l’invite à passer un week-end dans son vaste domaine enneigé du Vermont.

D’abord hésitante, Chloé accepte finalement l’invitation, rassurée par la présence de Madison et de son copain Kevin. Très vite, le trio se retrouve immergé dans un décor somptueux, entre le manoir imposant et un chalet plus intime, perdu en pleine nature. Charles, hôte attentif et raffiné, les accueille avec une générosité presque trop parfaite. Luxe, dîners élaborés, moments sous les étoiles… tout semble trop beau pour être vrai.

Mais alors que la nuit s’installe et que les ombres du passé refont surface, une tension étrange s’insinue dans l’atmosphère feutrée du chalet. Des regards appuyés, des silences lourds, des détails qui ne collent pas… Chloé commence à se demander si elle a eu raison d’accepter cette invitation. Que cache réellement Charles derrière son sourire énigmatique et ses attentions presque obsessionnelles ?

Alors que la neige recouvre le paysage d’un voile immaculé, la vérité, elle, s’apprête à éclater… et elle pourrait bien être plus glaçante que l’hiver lui-même.
</p>
        <img src="Cover.png" alt="Couverture du livre de D.R. Horizons" class="book-cover">
        <p>Bientôt disponible. Plongez dans une œuvre captivante et hors du commun.</p>
        <div class="rating-container">
    <div class="rating" id="rating-stars">
        <span class="star" data-value="1">★</span>
        <span class="star" data-value="2">★</span>
        <span class="star" data-value="3">★</span>
        <span class="star" data-value="4">★</span>
        <span class="star" data-value="5">☆</span>
    </div>
    <p>Moyenne des évaluations : <span id="average-rating">0</span>/5</p>
    <textarea id="rating-comment" class="rating-comment" rows="2" placeholder="Laissez un court commentaire..."></textarea>
    <button onclick="submitRating()">Envoyer</button>

    <h3>Meilleurs commentaires :</h3>
    <div id="top-comments"></div>
</div>

<script>
    let ratings = JSON.parse(localStorage.getItem("ratings")) || [];
    let bestComments = JSON.parse(localStorage.getItem("bestComments")) || [];

    function submitRating() {
        let selectedStars = document.querySelectorAll('.star.selected').length;
        let comment = document.getElementById('rating-comment').value.trim();

        if (!comment) {
            alert("Veuillez écrire un commentaire.");
            return;
        }

        ratings.push(selectedStars);
        localStorage.setItem("ratings", JSON.stringify(ratings));
        updateAverageRating();

        if (selectedStars >= 4) {
            bestComments.push(comment);
            if (bestComments.length > 3) bestComments = bestComments.slice(-3);
            localStorage.setItem("bestComments", JSON.stringify(bestComments));
            updateTopComments();
        }

        document.getElementById('rating-comment').value = "";
    }

    function updateAverageRating() {
        let sum = ratings.reduce((a, b) => a + b, 0);
        let average = ratings.length ? (sum / ratings.length).toFixed(1) : 0;
        document.getElementById("average-rating").textContent = average;
    }

    function updateTopComments() {
        let commentsDiv = document.getElementById("top-comments");
        commentsDiv.innerHTML = bestComments.map(c => `<p class="italic">“${c}”</p>`).join("");
    }

    document.querySelectorAll('.star').forEach(star => {
        star.addEventListener('click', function() {
            let value = this.getAttribute('data-value');
            document.querySelectorAll('.star').forEach(s => {
                s.textContent = s.getAttribute('data-value') <= value ? '★' : '☆';
                s.classList.toggle('selected', s.getAttribute('data-value') <= value);
            });
        });
    });

    // Mettre à jour les valeurs au chargement
    updateAverageRating();
    updateTopComments();
</script>
<section class="section" id="about">
        <h2>À propos</h2>
        <p>D.R. Horizons est un explorateur de l’imaginaire, un conteur aux mille facettes, porté par une soif d’aventure et une curiosité insatiable pour l’âme humaine. Écrivain atypique, il puise dans sa liberté de pensée et son goût pour la psychologie pour tisser des récits où le mystère flirte avec l’émotion, et où chaque détail a son importance. Installé à Montréal, une ville vibrante qui cultive l’ouverture d’esprit et la diversité des idées, il trouve dans ses rues, ses contrastes et son énergie créative une source d’inspiration inépuisable. L’écriture est pour lui une passion, un espace où il donne libre cours à son imagination débordante, façonnant des univers envoûtants où rien n’est jamais tout à fait ce qu’il semble être. </p>
<section class="section" id="contact">
    <h2>Contact</h2>
    <form id="contact-form" action="https://formspree.io/f/moveaedn" method="POST">
        <label for="name">Nom :</label>
        <input type="text" id="name" name="name" required>

        <label for="email">Email :</label>
        <input type="email" id="email" name="email" required>

        <label for="message">Message :</label>
        <textarea id="message" name="message" rows="4" required></textarea>

        <input type="hidden" name="_captcha" value="false">

        <button type="submit" class="big-button">Envoyer</button>
    </form>
</section>


    </section>
    
    <section class="section" id="don">
        <h2>Donnez vie à mes histoires</h2>
        <p> ✨
Écrire, c’est explorer, donner naissance à des mondes où le mystère, l’émotion et l’inattendu se rencontrent. Mon imagination déborde de projets – romans, récits captivants, et même des scénarios prêts à être portés à l’écran. Mais pour leur donner l’espace qu’ils méritent, j’ai besoin de votre soutien.

Chaque contribution est une impulsion précieuse qui me permet de me consacrer pleinement à l’écriture, de publier plus régulièrement et de partager avec vous des histoires qui sortent des sentiers battus.

🎁 En guise de remerciement, vous aurez accès à des contenus exclusifs. 

Si vous croyez en l’importance des récits qui transportent et questionnent, embarquez avec moi dans cette aventure littéraire et cinématographique.

Merci infiniment pour votre soutien ! ❤️📚
</p>
        <a href="https://paypal.me/DRHorizons?country.x=CA&locale.x=fr_CA" class="big-button">Faire un don</a>
  <section id="english">

    <footer>
        <p>&copy; 2025 - Tous droits réservés.</p>
    </footer>
</body>
