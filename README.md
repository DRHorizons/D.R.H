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
        .rating-container { margin: 20px auto; text-align: center; }
        .rating { display: flex; justify-content: center; cursor: pointer; }
        .star { font-size: 25px; color: #ff8c00; cursor: pointer; }
        .rating-comment { margin-top: 10px; }
        .rating-summary { font-size: 18px; font-weight: bold; margin-top: 15px; }
        .small-button { padding: 10px 20px; font-size: 14px; }
    </style>
</head>
<body>
    <header>
        <img src="photo.jpeg" alt="Portrait de l'écrivain D.R. Horizons" class="photo">
    </header>
    <nav>
        <a href="#oeuvres">Mon Livre</a>
        <a href="#about">À propos</a>
        <a href="#contact">Contact</a>
        <a href="#don">Soutenir</a>
        <a href="#english">English</a>
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
        <h2>English Section</h2>
        <p><html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>D.R. Horizons - Author</title>
    <meta name="description" content="Discover the captivating world of D.R. Horizons, a writer of psychological thrillers and mysterious stories. Support his literary work.">
    <meta name="keywords" content="Psychological thriller, Thriller novel, Thriller in Vermont, Forgotten Chalet, Chalet novel, Confinement novel, Intense suspense, Suspense novel, Psychological mystery, Theme of domination">
    <link rel="stylesheet" href="styles.css">
    <style>
        body { font-family: Arial, sans-serif; margin: 0; padding: 0; text-align: center; }
        nav { background: #222; padding: 15px; }
        nav a { color: white; text-decoration: none; font-size: 20px; margin: 0 20px; font-weight: bold; transition: color 0.3s ease; }
        nav a:hover { color: #ff8c00; }
        .big-button { display: inline-block; background-color: #ff8c00; color: white; padding: 15px 30px; font-size: 18px; text-decoration: none; font-weight: bold; border-radius: 5px; margin: 15px 0; transition: background 0.3s; }
        .big-button:hover { background-color: #e07b00; }
        .rating-container { margin: 20px auto; text-align: center; }
        .rating { display: flex; justify-content: center; cursor: pointer; }
        .star { font-size: 25px; color: #ff8c00; cursor: pointer; }
        .rating-comment { margin-top: 10px; }
        .rating-summary { font-size: 18px; font-weight: bold; margin-top: 15px; }
        .small-button { padding: 10px 20px; font-size: 14px; }
    </style>
</head>
<body>
    <header>
        <img src="photo.jpeg" alt="Portrait of the writer D.R. Horizons" class="photo">
    </header>
    <nav>
        <a href="#works">My Book</a>
        <a href="#about">About</a>
        <a href="#contact">Contact</a>
        <a href="#donate">Support</a>
        <a href="#french">Français</a>
    </nav>
    <section class="section" id="works">
        <h1>My First Book</h1>
        <p>After a dream vacation in Mexico, Chloé and Madison, two inseparable friends, return to Montreal, ready to resume their routine. But an unexpected encounter will change everything. Charles, a charismatic and mysterious man, crosses Chloé’s path and invites her to spend a weekend at his vast snowy estate in Vermont.

Initially hesitant, Chloé eventually accepts the invitation, reassured by the presence of Madison and her boyfriend Kevin. Quickly, the trio finds themselves immersed in a sumptuous setting, between the imposing manor and a more intimate chalet, lost in nature. Charles, an attentive and refined host, welcomes them with an almost too perfect generosity. Luxury, elaborate dinners, moments under the stars… everything seems too good to be true.

But as night falls and shadows of the past resurface, a strange tension infiltrates the chalet’s cozy atmosphere. Intense gazes, heavy silences, details that don’t add up… Chloé begins to wonder if she made the right decision. What is Charles really hiding behind his enigmatic smile and almost obsessive attention?

As the snow blankets the landscape in a pristine veil, the truth is about to be revealed… and it may be colder than winter itself.</p>
        <img src="Cover.png" alt="Cover of D.R. Horizons' book" class="book-cover">
        <p>Coming soon. Immerse yourself in a captivating and unique work.</p>
    </section>

    <section class="section" id="about">
        <h2>About</h2>
        <p>D.R. Horizons is an explorer of the imagination, a storyteller with a thousand facets, driven by a thirst for adventure and an insatiable curiosity about the human soul. An unconventional writer, he draws from his freedom of thought and his passion for psychology to weave stories where mystery flirts with emotion, and where every detail matters. Based in Montreal, a vibrant city that fosters open-mindedness and diversity of ideas, he finds in its streets, contrasts, and creative energy an inexhaustible source of inspiration. Writing is a passion for him, a space where he unleashes his overflowing imagination, crafting enchanting worlds where nothing is ever quite as it seems.</p>
    </section>
    
    <section class="section" id="contact">
        <h2>Contact</h2>
        <form id="contact-form" action="https://formspree.io/f/moveaedn" method="POST">
            <label for="name">Name:</label>
            <input type="text" id="name" name="name" required>

            <label for="email">Email:</label>
            <input type="email" id="email" name="email" required>

            <label for="message">Message:</label>
            <textarea id="message" name="message" rows="4" required></textarea>

            <input type="hidden" name="_captcha" value="false">

            <button type="submit" class="big-button">Send</button>
        </form>
    </section>

    <section class="section" id="donate">
        <h2>Bring My Stories to Life</h2>
        <p>✨ Writing is about exploring, creating worlds where mystery, emotion, and the unexpected meet. My imagination overflows with projects—novels, captivating stories, and even scripts ready to come to life on screen. But to give them the space they deserve, I need your support.

Each contribution is a valuable boost that allows me to dedicate myself fully to writing, publish more regularly, and share with you stories that break the mold.

🎁 As a token of appreciation, you’ll have access to exclusive content.

If you believe in the importance of stories that transport and challenge, join me on this literary and cinematic journey.

Thank you so much for your support! ❤️📚</p>
        <a href="https://paypal.me/DRHorizons?country.x=CA&locale.x=en_CA" class="big-button">Donate</a>
    </section>
</body>
</html>
</p>
    </section>

    <footer>
        <p>&copy; 2025 - Tous droits réservés.</p>
    </footer>
</body>
