<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HYRA - Malte Webdesigner aus Hürth | Super Custom Websites</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700&display=swap" rel="stylesheet">
    
    <style>
        /* Grundlegende Resets */
        :root {
            --primary-color: #007bff; /* Ein modernes Blau für den CTA */
            --text-color: #333;
            --background-color: #ffffff;
            --light-gray: #f9f9f9;
            --font-family: 'Montserrat', sans-serif;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: var(--font-family);
            color: var(--text-color);
            background-color: var(--background-color);
            line-height: 1.6;
        }

        /* Typografie */
        h1 {
            font-size: 3em;
            font-weight: 700;
            margin-bottom: 0.5em;
        }

        h2 {
            font-size: 2em;
            font-weight: 700;
            margin-bottom: 1.5em;
            text-align: center;
        }

        h3 {
            font-size: 1.2em;
            margin-bottom: 0.8em;
        }

        p {
            margin-bottom: 1em;
        }

        a {
            color: var(--primary-color);
            text-decoration: none;
            transition: color 0.3s;
        }

        a:hover {
            color: #0056b3;
        }

        /* Header und Navigation */
        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 5%;
            background-color: var(--background-color);
            border-bottom: 1px solid var(--light-gray);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .logo {
            font-size: 1.5em;
            font-weight: 700;
        }

        nav a {
            margin-left: 20px;
            font-size: 0.9em;
            color: var(--text-color);
        }

        .cta-nav {
            background-color: var(--primary-color);
            color: white !important;
            padding: 8px 15px;
            border-radius: 5px;
            transition: background-color 0.3s;
        }

        .cta-nav:hover {
            background-color: #0056b3;
        }

        /* Buttons (CTA) */
        .button {
            display: inline-block;
            padding: 12px 30px;
            border-radius: 5px;
            font-weight: 700;
            text-transform: uppercase;
            transition: background-color 0.3s, transform 0.2s;
        }

        .primary-cta {
            background-color: var(--primary-color);
            color: white;
        }

        .primary-cta:hover {
            background-color: #0056b3;
            transform: translateY(-2px);
        }

        .large {
            font-size: 1.1em;
            padding: 15px 40px;
        }

        /* Sektionen allgemein */
        section {
            padding: 80px 5%;
        }

        .content-section {
            max-width: 900px;
            margin: 0 auto;
        }

        /* Hero Sektion */
        .hero {
            min-height: 80vh;
            display: flex;
            align-items: center;
            text-align: left;
            background-color: var(--light-gray); /* Leichter Kontrast */
        }

        .hero-content {
            max-width: 700px;
        }

        .hero h1 {
            font-size: 3.5em;
        }

        .hero h2 {
            font-size: 1.5em;
            font-weight: 400;
            color: #555;
            margin-bottom: 2em;
            text-align: left;
        }

        /* Über mich Sektion */
        #ueber-mich h2 {
            text-align: left;
            border-bottom: 2px solid var(--primary-color);
            display: inline-block;
            padding-bottom: 5px;
        }

        .text-block p {
            font-size: 1.1em;
        }

        /* Leistungen Sektion (Grid) */
        .services {
            background-color: var(--light-gray);
            text-align: center;
        }

        .service-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }

        .service-card {
            background-color: var(--background-color);
            padding: 30px;
            border-left: 5px solid var(--primary-color);
            text-align: left;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s;
        }

        .service-card:hover {
            transform: translateY(-5px);
        }

        /* CTA Sektion (Kontakt) */
        .cta-section {
            text-align: center;
            padding: 100px 5%;
            background-color: #222;
            color: white;
        }

        .cta-section h2 {
            color: white;
        }

        .cta-section p {
            font-size: 1.2em;
            margin-bottom: 40px;
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 20px;
            font-size: 0.8em;
            border-top: 1px solid var(--light-gray);
            color: #888;
        }

        footer a {
            color: #888;
            margin: 0 5px;
        }

        footer a:hover {
            color: var(--primary-color);
        }

        /* Responsivität für kleinere Bildschirme */
        @media (max-width: 768px) {
            .hero {
                text-align: center;
            }
            .hero h1 {
                font-size: 2.5em;
            }
            .hero h2 {
                font-size: 1.2em;
                text-align: center;
            }
            header {
                flex-direction: column;
            }
            nav {
                margin-top: 15px;
            }
            nav a {
                margin: 0 10px;
                display: inline-block;
                margin-bottom: 5px;
            }
            #ueber-mich h2 {
                text-align: center;
            }
        }
    </style>
</head>
<body>

    <header>
        <div class="logo">HYRA</div>
        <nav>
            <a href="#ueber-mich">Über mich</a>
            <a href="#leistungen">Leistungen</a>
            <a href="#kontakt" class="cta-nav">Jetzt starten</a>
        </nav>
    </header>

    <section id="hero" class="hero">
        <div class="hero-content">
            <h1>Dein Online-Erfolg beginnt in Hürth.</h1>
            <h2>Super Custom Websites von Malte. Extrem schnell & günstig.</h2>
            <p>Wir bauen minimalistische und moderne Websites für lokale Businesses – Friseure, kleine Läden & mehr.</p>
            <a href="#kontakt" class="button primary-cta">Kostenlose Beratung anfragen</a>
        </div>
    </section>

    <section id="ueber-mich" class="content-section">
        <h2>Wer ich bin.</h2>
        <div class="text-block">
            <p><strong>Hi, ich bin Malte. Webdesigner aus Hürth</strong> und Gründer von HYRA. Ich kenne die Herausforderungen von lokalen Unternehmen und weiß, wie wichtig ein professioneller, schneller und günstiger Online-Auftritt ist, um neue Kunden zu gewinnen.</p>
            <p>Mein Ziel ist es, Dir eine digitale Visitenkarte zu geben, die nicht nur gut aussieht, sondern auch funktioniert – ohne versteckte Kosten und mit maximaler Geschwindigkeit bei der Umsetzung.</p>
        </div>
    </section>

    <section id="leistungen" class="content-section services">
        <h2>Was wir verkaufen.</h2>
        <div class="service-grid">
            <div class="service-card">
                <h3>Super Custom Design</h3>
                <p>Keine Standard-Templates. Jede Website wird von Grund auf neu und modern für Dein Business designed. **Minimalistisch** und zielgruppenorientiert.</p>
            </div>
            <div class="service-card">
                <h3>Kostenloses Hosting</h3>
                <p>Volle Konzentration auf Dein Geschäft. Das Hosting übernehmen wir für Dich – **100% kostenlos im ersten Jahr**.</p>
            </div>
            <div class="service-card">
                <h3>Extrem schnell & günstig</h3>
                <p>Deine neue Website ist oft in wenigen Tagen online, zu einem Preis, der Dein Budget nicht sprengt. **Perfekt für lokale Start-ups** und kleine Läden.</p>
            </div>
        </div>
    </section>

    <section id="kontakt" class="cta-section">
        <h2>Bereit für Deine neue Website?</h2>
        <p>Kontaktiere uns jetzt für ein unverbindliches Erstgespräch. Lass uns Deinen Online-Erfolg starten!</p>
        <a href="mailto:DEINE@EMAILADRESSE.DE?subject=Anfrage%20Website%20HYRA" class="button primary-cta large">Malte von HYRA kontaktieren</a>
    </section>

    <footer>
        <p>&copy; 2025 HYRA Webdesign. Malte aus Hürth.</p>
        <p><a href="#">Impressum</a> | <a href="#">Datenschutz</a></p>
    </footer>

    <script>
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();

                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });
    </script>
</body>
</html>


