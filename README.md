
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HYRA Webdesign – Ihr Partner für moderne Websites in Hürth</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&display=swap" rel="stylesheet">
    
    <style>
        /* Farbschema und Variablen */
        :root {
            --primary-color: #2C3E50; /* Dunkles, professionelles Graublau */
            --accent-color: #3498DB; /* Helles Akzentblau für CTA */
            --text-color: #333333;
            --light-gray: #F4F6F8; /* Sehr helles Grau */
            --background-color: #ffffff;
            --font-family: 'Inter', sans-serif;
            --glow-color: rgba(52, 152, 219, 0.4); /* Leuchtendes Blau, leicht transparent */
        }

        /* Basis-Styling und Resets */
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
            scroll-behavior: smooth;
        }

        /* Typografie */
        h1 {
            font-size: 3.5rem;
            font-weight: 800; 
            line-height: 1.1;
            margin-bottom: 0.5em;
        }

        h2 {
            font-size: 2.2rem;
            font-weight: 800;
            margin-bottom: 0.8em;
            text-align: center;
            color: var(--primary-color);
        }

        h3 {
            font-size: 1.25rem;
            font-weight: 600;
            margin-bottom: 0.5em;
            color: var(--primary-color);
        }

        p {
            font-size: 1.05rem;
            color: #555;
            margin-bottom: 1.5em;
        }

        a {
            color: var(--accent-color);
            text-decoration: none;
            transition: color 0.3s;
        }

        a:hover {
            color: var(--primary-color);
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
            z-index: 1000;
        }

        /* LOGO-Styling */
        .logo {
            font-size: 1.6rem;
            font-weight: 800;
            color: var(--primary-color);
            letter-spacing: -2px;
        }
        .logo span {
            color: var(--accent-color); 
            font-size: 1.8rem;
        }

        nav a {
            margin-left: 30px;
            font-size: 1rem;
            font-weight: 600;
            color: var(--text-color);
            padding: 5px 0;
            position: relative;
        }

        /* Underline-Effekt für Navigation */
        nav a:after {
            content: '';
            position: absolute;
            left: 0;
            bottom: 0;
            width: 0;
            height: 2px;
            background-color: var(--accent-color);
            transition: width 0.3s ease;
        }
        nav a:hover:after {
            width: 100%;
        }

        .cta-nav {
            background-color: var(--accent-color);
            color: white !important;
            padding: 8px 18px;
            border-radius: 4px;
            transition: background-color 0.3s, transform 0.2s;
            margin-left: 30px;
            border: none;
        }
        .cta-nav:hover {
            background-color: #2980B9;
            transform: translateY(-1px);
        }
        .cta-nav:after {
            content: none;
        }

        /* Buttons (CTA) */
        .button {
            display: inline-block;
            padding: 15px 35px;
            border-radius: 4px;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: background-color 0.3s, transform 0.2s, box-shadow 0.3s;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }

        .primary-cta {
            background-color: var(--accent-color);
            color: white;
            border: 2px solid var(--accent-color);
        }

        .primary-cta:hover {
            background-color: #2980B9;
            transform: translateY(-2px);
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.2);
        }

        .large {
            font-size: 1.15rem;
        }

        /* Sektionen allgemein */
        section {
            padding: 100px 5%;
        }

        .content-section {
            max-width: 1000px;
            margin: 0 auto;
        }

        /* Hero Sektion */
        .hero {
            min-height: 90vh;
            display: flex;
            align-items: center;
            text-align: left;
            background-color: var(--light-gray);
            padding-top: 150px;
        }

        .hero-content {
            max-width: 800px;
        }

        .hero h1 {
            color: var(--primary-color);
        }

        .hero h2 {
            font-size: 1.8rem;
            font-weight: 400;
            color: #777;
            margin-bottom: 2.5em;
            text-align: left;
        }


        /* Über uns Sektion */
        #ueber-uns h2 {
            text-align: left;
            margin-bottom: 0.5em;
            font-size: 2.5rem;
        }

        .text-block p strong {
            /* Text-Hervorhebung durch strong beibehalten, aber ** entfernt */
            color: var(--primary-color);
        }

        /* Leistungen Sektion (Grid) */
        .services {
            background-color: var(--background-color); 
            text-align: center;
            border-top: 1px solid var(--light-gray);
        }
        
        /* 3 Spalten nebeneinander */
        .service-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr); 
            gap: 40px;
            margin-top: 50px;
        }

        .service-card {
            background-color: var(--light-gray);
            padding: 40px; 
            border-radius: 8px;
            text-align: left;
            transition: background-color 0.3s, box-shadow 0.3s;
            min-height: 250px; 
        }

        /* GLOW-EFFEKT */
        .service-card:hover {
            background-color: #EAECEF;
            box-shadow: 0 0 15px var(--glow-color); 
        }

        /* CTA Sektion (Kontakt) */
        .cta-section {
            text-align: center;
            padding: 120px 5%;
            background-color: var(--primary-color);
            color: white;
        }

        .cta-section h2 {
            color: white;
            font-size: 2.8rem;
        }

        .cta-section p {
            font-size: 1.3rem;
            margin-bottom: 50px;
            color: #EAECEF;
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 30px;
            font-size: 0.9rem;
            border-top: 1px solid var(--light-gray);
            color: #888;
            background-color: var(--light-gray);
        }

        footer a {
            color: #888;
            margin: 0 10px;
        }

        footer a:hover {
            color: var(--primary-color);
        }

        /* Responsivität */
        @media (max-width: 992px) {
            .service-grid {
                grid-template-columns: 1fr; /* Eine Spalte auf kleineren Bildschirmen */
            }
        }
        @media (max-width: 768px) {
            h1 { font-size: 2.5rem; }
            h2 { font-size: 1.8rem; }
            .hero {
                text-align: center;
            }
            .hero h2 {
                text-align: center;
            }
            header {
                flex-direction: column;
                padding-bottom: 10px;
            }
            nav {
                margin-top: 15px;
                display: flex;
                flex-wrap: wrap;
                justify-content: center;
            }
            nav a {
                margin: 5px 10px;
            }
            .cta-nav {
                margin-left: 10px;
            }
            #ueber-uns h2 {
                text-align: center;
            }
            .service-card {
                min-height: auto;
            }
        }
    </style>
</head>
<body>

    <header>
        <div class="logo"><span>H</span>YRA</div>
        <nav>
            <a href="#ueber-uns">Über uns</a>
            <a href="#leistungen">Leistungen</a>
            <a href="#kontakt" class="cta-nav">Projekt starten</a>
        </nav>
    </header>

    <section id="hero" class="hero">
        <div class="hero-content">
            <h1>Lokale Präsenz. Digitale Stärke.</h1>
            <h2>Die Webdesign-Agentur für lokale Businesses in Hürth. Extrem schnell und budgetfreundlich.</h2>
            <p>HYRA liefert minimalistische und moderne Websites, die speziell für Friseure, kleine Läden und Dienstleister entwickelt wurden, um sofort mehr Kunden zu gewinnen.</p>
            <a href="#kontakt" class="button primary-cta large">Kostenlose Erstberatung</a>
        </div>
    </section>

    <section id="ueber-uns" class="content-section">
        <h2>HYRA. Ihr lokaler Webdesign-Partner.</h2>
        <div class="text-block">
            <p>Wir von HYRA Webdesign aus Hürth haben es uns zur Aufgabe gemacht, lokalen Unternehmen den Einstieg in die digitale Welt so effizient wie möglich zu gestalten – **professionell, unkompliziert und zu fairen Konditionen.**</p>
            <p>Wir verstehen die Bedürfnisse von lokalen Dienstleistern. Bei uns erhalten Sie nicht nur eine Website, sondern eine maßgeschneiderte digitale Lösung, die Ihre Besucher überzeugt und in zahlende Kunden verwandelt. Setzen Sie auf Qualität und Geschwindigkeit.</p>
        </div>
    </section>

    <section id="leistungen" class="content-section services">
        <h2>Was HYRA Ihnen garantiert.</h2>
        <div class="service-grid">
            
            <div class="service-card">
                <h3>Super Custom Design</h3>
                <p>Keine Templates. Wir entwickeln jede Website von Grund auf neu – minimalistisch, modern und 100% auf Ihre lokale Marke abgestimmt. Einzigartig und professionell.</p>
            </div>
            
            <div class="service-card">
                <h3>Kostenloses Hosting (Immer)</h3>
                <p>Volle Leistung ohne Mehrkosten. Wir übernehmen das Hosting **dauerhaft kostenlos** für Sie. So fallen keine laufenden Kosten für den Webspace an.</p>
            </div>
            
            <div class="service-card">
                <h3>Extrem schnell & günstig</h3>
                <p>Dank unserer optimierten Prozesse ist Ihre professionelle Website in kürzester Zeit online. Qualität muss kein Vermögen kosten – wir sind Ihr günstiger Partner.</p>
            </div>

        </div>
    </section>

    <section id="kontakt" class="cta-section">
        <h2>Starten Sie jetzt Ihre Sichtbarkeit.</h2>
        <p>Kontaktieren Sie uns unverbindlich. Wir freuen uns darauf, Ihr lokales Geschäft digital zu stärken!</p>
        <a href="mailto:DEINE@EMAILADRESSE.DE?subject=Anfrage%20Website%20HYRA%20Webdesign" class="button primary-cta large">Kontakt zu HYRA aufnehmen</a>
    </section>

    <footer>
        <p>&copy; 2025 HYRA Webdesign | Ihr Partner in Hürth.</p>
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
