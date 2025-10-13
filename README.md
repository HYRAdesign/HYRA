<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HYRA Webdesign - Dein lokaler Experte aus Hürth</title>
    <!-- Lade Google Font: Inter für eine minimalistische und moderne Optik -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700;800;900&display=swap" rel="stylesheet">
    <!-- Lade Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        /* Grundschriftart Inter für eine moderne und klare Optik */
        body {
            font-family: 'Inter', sans-serif;
            /* Hintergrund auf rein WEISS gesetzt */
            @apply bg-white text-gray-800; 
        }
        /* Haupt-CTA-Button Stil */
        .btn-cta {
            @apply inline-block px-12 py-4 bg-indigo-600 text-white text-xl font-extrabold rounded-xl shadow-2xl shadow-indigo-500/50
                   transform hover:scale-[1.03] hover:bg-indigo-700
                   transition-all duration-300 ease-in-out
                   focus:ring-4 focus:ring-indigo-500 focus:ring-opacity-70;
        }
        /* Sekundär-Button Stil (für Hero) */
        .btn-secondary {
            @apply inline-block px-12 py-4 bg-white text-indigo-600 text-xl font-extrabold rounded-xl border-2 border-indigo-200 shadow-md
                   transform hover:bg-indigo-50 hover:shadow-xl hover:border-indigo-400
                   transition-all duration-300 ease-in-out;
        }
        /* Stil für Überschriften */
        h1, h2, h3 {
            @apply font-black text-gray-900; 
        }
        /* Basis-Sektionen haben nur horizontalen Abstand, vertikaler Abstand wird individuell per py-* gesetzt */
        section {
            @apply px-4 md:px-12 lg:px-20; 
        }
    </style>
</head>
<body>

    <!-- Header / Navigation -->
    <header class="bg-white shadow-lg py-4 sticky top-0 z-10">
        <nav class="container mx-auto flex justify-between items-center px-4">
            <a href="#" class="text-3xl font-black text-indigo-700 tracking-widest">HYRA</a> <!-- Markenname -->
            <ul class="hidden md:flex space-x-8 font-semibold">
                <li><a href="#home" class="text-gray-700 hover:text-indigo-600 transition duration-300">Start</a></li>
                <li><a href="#about" class="text-gray-700 hover:text-indigo-600 transition duration-300">Über uns</a></li>
                <li><a href="#services" class="text-gray-700 hover:text-indigo-600 transition duration-300">Vorteile</a></li>
                <li><a href="#contact" class="text-gray-700 hover:text-indigo-600 transition duration-300">Kontakt</a></li>
            </ul>
            <!-- Mobile Menu Button -->
            <button class="md:hidden text-gray-700 hover:text-indigo-600 focus:outline-none" aria-label="Menü öffnen">
                <svg class="w-7 h-7" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path></svg>
            </button>
        </nav>
    </header>

    <!-- Mobile Menu Overlay -->
    <div id="mobile-menu" class="hidden fixed inset-0 bg-white z-50 p-6 md:hidden">
        <div class="flex justify-end">
            <button class="text-gray-700 hover:text-indigo-600 focus:outline-none" aria-label="Menü schließen">
                <svg class="w-7 h-7" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path></svg>
            </button>
        </div>
        <ul class="flex flex-col items-center space-y-10 mt-16 font-semibold">
            <li><a href="#home" class="text-gray-800 text-3xl hover:text-indigo-600 transition duration-300" onclick="document.getElementById('mobile-menu').classList.add('hidden')">Start</a></li>
            <li><a href="#about" class="text-gray-800 text-3xl hover:text-indigo-600 transition duration-300" onclick="document.getElementById('mobile-menu').classList.add('hidden')">Über uns</a></li>
            <li><a href="#services" class="text-gray-800 text-3xl hover:text-indigo-600 transition duration-300" onclick="document.getElementById('mobile-menu').classList.add('hidden')">Vorteile</a></li>
            <li><a href="#contact" class="text-gray-800 text-3xl hover:text-indigo-600 transition duration-300" onclick="document.getElementById('mobile-menu').classList.add('hidden')">Kontakt</a></li>
        </ul>
    </div>

    <!-- Hero Section (Content Block 1) - Full-width und hellblau -->
    <section id="home" class="text-center bg-indigo-50 py-32 md:py-40">
        <div class="container mx-auto px-4">
            <!-- H1 ist jetzt sehr groß: text-7xl auf Mobile, text-9xl auf Desktop -->
            <h1 class="text-7xl md:text-9xl mb-6 leading-tight max-w-5xl mx-auto">
                Digital. <br class="hidden md:inline">
                <span class="text-indigo-600">Erfolgreich.</span>
            </h1>
            <p class="text-xl md:text-3xl mb-12 max-w-3xl mx-auto text-gray-600 font-normal">
                Wir bauen maßgeschneiderte, moderne Websites für Ihr Business – ohne Kompromisse bei Design oder Geschwindigkeit.
            </p>
            <div class="flex flex-col sm:flex-row justify-center space-y-4 sm:space-y-0 sm:space-x-8">
                <a href="#contact" class="btn-cta">Jetzt unverbindlich anfragen</a>
                <a href="#services" class="btn-secondary">Unsere Vorteile entdecken</a>
            </div>
        </div>
    </section>

    <!-- Wer ist HYRA? (About) Section - Hellgrau, full-width, großer vertikaler Abstand, zentrierter Text -->
    <section id="about" class="bg-gray-100 mt-12 py-40">
        <div class="container mx-auto px-4 max-w-4xl">
            <h2 class="text-3xl md:text-5xl mb-12 text-center">👋 Wer ist HYRA? Unsere Philosophie.</h2>
            <div class="text-xl leading-relaxed space-y-8 text-gray-700 text-center">
                <p>
                    HYRA ist Ihr Spezialist für modernes Webdesign aus <span class="font-bold text-gray-900">Hürth</span>. Gegründet von Malte, liegt unsere Mission darin, lokale Unternehmen – genau wie Ihres – mit einer beeindruckenden Online-Präsenz auszustatten.
                </p>
                <p>
                    Wir wissen, dass Ihr Fokus auf Ihrem Handwerk liegt, nicht auf der Technik. Deshalb bieten wir einen minimalistischen, schnellen und direkten Service. Sie müssen sich um nichts kümmern.
                </p>
                <p>
                    HYRA verzichtet auf komplizierte Pakete und versteckte Kosten. Wir bieten Ihnen eine Super Custom Website, die perfekt zu Ihrem lokalen Business passt und Ihnen neue Kunden bringt.
                </p>
            </div>
        </div>
    </section>

    <!-- Was ich mache (Value Proposition) Section - Weiß, full-width -->
    <section id="services" class="bg-white mt-12 py-32">
        <div class="container mx-auto text-center">
            <h2 class="text-3xl md:text-5xl mb-16">Ihre unschlagbaren Vorteile mit HYRA Webdesign</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-10">

                <!-- Vorteil 1: Custom Design -->
                <div class="bg-white p-8 rounded-2xl shadow-xl hover:shadow-2xl hover:shadow-indigo-200 transform hover:-translate-y-2 transition duration-500 ease-in-out border-t-8 border-indigo-600">
                    <div class="text-5xl text-indigo-600 mb-4">🎨</div>
                    <h3 class="text-xl font-extrabold mb-3 text-gray-900">100% Custom Design</h3>
                    <p class="text-gray-600">
                        Keine Templates, keine Standardlösungen. Ihre Website ist ein einzigartiges Unikat, perfekt zugeschnitten auf Ihr Business und Ihre Zielgruppe.
                    </p>
                </div>

                <!-- Vorteil 2: Kostenloses Hosting -->
                <div class="bg-white p-8 rounded-2xl shadow-xl hover:shadow-2xl hover:shadow-indigo-200 transform hover:-translate-y-2 transition duration-500 ease-in-out border-t-8 border-indigo-600">
                    <div class="text-5xl text-indigo-600 mb-4">🚀</div>
                    <h3 class="text-xl font-extrabold mb-3 text-gray-900">Kostenloses Hosting</h3>
                    <p class="text-gray-600">
                        Keine Sorgen um Serverkosten. Wir bieten Ihnen das Hosting für das erste Jahr kostenlos an. Ihre Seite ist immer online und extrem schnell.
                    </p>
                </div>

                <!-- Vorteil 3: Geschwindigkeit -->
                <div class="bg-white p-8 rounded-2xl shadow-xl hover:shadow-2xl hover:shadow-indigo-200 transform hover:-translate-y-2 transition duration-500 ease-in-out border-t-8 border-indigo-600">
                    <div class="text-5xl text-indigo-600 mb-4">⏱️</div>
                    <h3 class="text-xl font-extrabold mb-3 text-gray-900">Extrem schnelle Umsetzung</h3>
                    <p class="text-gray-600">
                        Wir arbeiten effizient. Wir bringen Ihre neue, moderne Website in Rekordzeit online, damit Sie sofort davon profitieren können.
                    </p>
                </div>

                <!-- Vorteil 4: Günstige Preise -->
                <div class="bg-white p-8 rounded-2xl shadow-xl hover:shadow-2xl hover:shadow-indigo-200 transform hover:-translate-y-2 transition duration-500 ease-in-out border-t-8 border-indigo-600">
                    <div class="text-5xl text-indigo-600 mb-4">💸</div>
                    <h3 class="text-xl font-extrabold mb-3 text-gray-900">Fair & Günstig</h3>
                    <p class="text-gray-600">
                        Professionelles Webdesign muss nicht das Budget sprengen. Top-Qualität zu fairen und transparenten Preisen für lokale Geschäfte.
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- Call-to-Action / Kontakt Section - Voller Indigo-Kasten -->
    <section id="contact" class="bg-indigo-600 text-white mt-12 py-36">
        <div class="container mx-auto px-4 text-center">
            <h2 class="text-3xl md:text-5xl mb-12">Jetzt Ihr lokales Business online bringen.</h2>
            <p class="text-xl mb-14 max-w-2xl mx-auto text-indigo-100">
                Lassen Sie uns unverbindlich über Ihr Projekt sprechen. Schreiben Sie uns, und wir legen sofort los.
            </p>
            <!-- Kontaktformular, Hintergrund ist hier weiß, damit es sich abhebt -->
            <div class="max-w-xl mx-auto bg-white p-8 md:p-10 rounded-2xl shadow-3xl border border-indigo-100 text-gray-800">
                <form action="#" method="POST" class="space-y-6 text-left">
                    <div>
                        <label for="name" class="block text-sm font-semibold text-gray-700">Ihr Name / Name Ihres Business</label>
                        <input type="text" id="name" name="name" class="mt-1 block w-full px-4 py-3 border border-gray-300 rounded-lg shadow-inner focus:ring-indigo-500 focus:border-indigo-500" placeholder="Ihr Friseursalon, Ihr Laden, ..." required>
                    </div>
                    <div>
                        <label for="email" class="block text-sm font-semibold text-gray-700">Ihre E-Mail</label>
                        <input type="email" id="email" name="email" class="mt-1 block w-full px-4 py-3 border border-gray-300 rounded-lg shadow-inner focus:ring-indigo-500 focus:border-indigo-500" placeholder="kontakt@ihrefirma.de" required>
                    </div>
                    <div>
                        <label for="message" class="block text-sm font-semibold text-gray-700">Ihr Vorhaben (Kurzinfo)</label>
                        <textarea id="message" name="message" rows="4" class="mt-1 block w-full px-4 py-3 border border-gray-300 rounded-lg shadow-inner focus:ring-indigo-500 focus:border-indigo-500" placeholder="Ich brauche eine Website für meinen neuen Blumenladen in Hürth." required></textarea>
                    </div>
                    <!-- Dies ist der gewünschte Kontakt-Button -->
                    <button type="submit" class="w-full btn-cta">Nachricht an HYRA senden</button>
                </form>
            </div>
            <p class="mt-8 text-sm text-indigo-100">
                Oder schreiben Sie uns direkt: <a href="mailto:maltenow2@gmail.com" class="underline hover:text-white transition duration-300 font-semibold">maltenow2@gmail.com</a>
            </p>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-800 text-white py-10 px-4 mt-12">
        <div class="container mx-auto text-center md:flex md:justify-between md:items-center">
            <p class="mb-4 md:mb-0 text-sm">&copy; 2025 HYRA Webdesign. Malte, Webdesigner aus Hürth.</p>
            <ul class="flex justify-center space-x-6 text-sm">
                <li><a href="#" class="hover:text-indigo-400 transition duration-300">Impressum</a></li>
                <li><a href="#" class="hover:text-indigo-400 transition duration-300">Datenschutz</a></li>
            </ul>
        </div>
    </footer>

    <script>
        // JavaScript für das mobile Menü
        const mobileMenuButton = document.querySelector('header button[aria-label="Menü öffnen"]');
        const mobileMenu = document.getElementById('mobile-menu');
        const closeMobileMenuButton = mobileMenu.querySelector('button[aria-label="Menü schließen"]');

        mobileMenuButton.addEventListener('click', () => {
            mobileMenu.classList.remove('hidden');
        });

        closeMobileMenuButton.addEventListener('click', () => {
            mobileMenu.classList.add('hidden');
        });

        // Schließen des mobilen Menüs beim Klicken auf einen Link
        const mobileMenuLinks = mobileMenu.querySelectorAll('a');
        mobileMenuLinks.forEach(link => {
            link.addEventListener('click', () => {
                mobileMenu.classList.add('hidden');
            });
        });
    </script>

</body>
</html>


