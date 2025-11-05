<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kinder Tipptrainer – 10-Finger Methode</title>
    <style>
        /* --- Allgemeine Stile (Unverändert) --- */
        body {
            font-family: 'Comic Sans MS', sans-serif;
            background: #f2f8ff;
            color: #333;
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        header {
            background: #4da6ff;
            color: white;
            width: 100%;
            text-align: center;
            padding: 15px 0;
            font-size: 1.8em;
            font-weight: bold;
        }
        .lesson-container {
            display: none;
            flex-direction: column;
            align-items: center;
            margin-top: 20px;
            width: 90%;
            max-width: 800px;
        }
        .visible {
            display: flex;
        }
        .text-display {
            background: white;
            padding: 15px;
            border-radius: 10px;
            box-shadow: 0 2px 6px rgba(0,0,0,0.2);
            width: 100%;
            text-align: left;
            font-size: 1.4em;
            min-height: 60px;
            word-wrap: break-word;
            line-height: 1.5;
        }
        .correct { color: green; }
        .incorrect { color: red; background-color: #ffdddd; }
        .current { background-color: yellow; border-radius: 2px; }

        textarea {
            width: 100%;
            height: 120px;
            margin-top: 10px;
            font-size: 1.3em;
            border-radius: 10px;
            border: 2px solid #4da6ff;
            padding: 10px;
            resize: none;
            font-family: monospace;
        }
        .info-panel {
            display: flex;
            justify-content: space-between;
            width: 100%;
            margin-top: 10px;
            font-size: 1.1em;
            font-weight: bold;
        }
        .progress {
            margin-top: 20px;
            width: 100%;
            height: 25px;
            background: #d9d9d9;
            border-radius: 10px;
            overflow: hidden;
            text-align: center;
            line-height: 25px;
            color: #333;
            font-weight: bold;
            position: relative;
        }
        .progress-bar {
            height: 100%;
            background: #4da6ff;
            width: 0%;
            transition: width 0.5s ease;
            position: absolute;
            top: 0;
            left: 0;
            border-radius: 10px;
        }
        .progress-text {
            position: relative;
            z-index: 1;
        }
        .buttons {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }
        button {
            background: #4da6ff;
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 10px;
            font-size: 1.1em;
            cursor: pointer;
            transition: 0.2s;
            box-shadow: 0 4px #3b8ae0;
        }
        button:disabled {
            background: #ccc;
            box-shadow: 0 4px #999;
            cursor: not-allowed;
        }
        .lesson-list {
            list-style: none;
            padding: 0;
            width: 90%;
            max-width: 800px;
            margin-top: 20px;
        }
        .lesson-item {
            background: #fff;
            padding: 15px;
            margin-bottom: 10px;
            border-radius: 10px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            display: flex;
            justify-content: space-between;
            align-items: center;
            cursor: pointer;
            border-left: 5px solid #ccc;
        }
        .lesson-item.unlocked { border-left-color: #4da6ff; }
        .lesson-item.completed { border-left-color: green; }

        /* --- STIL für das Tastatur-Bild (für die Lektionsansicht) --- */
        .keyboard-image {
            width: 100%; 
            max-width: 700px; 
            height: auto;
            margin-top: 30px; 
            border: none; 
            box-shadow: none; 
        }
    </style>
</head>
<body>
    <header>Kinder Tipptrainer – 10-Finger Methode</header>

    <div id="lesson-selection" class="lesson-container visible">
        <h2>Wähle deine Lektion:</h2>
        <ul class="lesson-list" id="lessonList">
            </ul>
    </div>

    <div id="typing-area" class="lesson-container">
        <h2 id="lessonTitle"></h2>
        <div class="text-display" id="displayText"></div>
        <textarea id="typingInput" placeholder="Tippe den Text hier..." autofocus></textarea>
        <div class="info-panel">
            <span>Genauigkeit: <strong id="accuracyDisplay">0%</strong></span>
            <span>Fehler: <strong id="errorCount">0</strong></span>
            <span>WPM: <strong id="wpmDisplay">0</strong></span>
        </div>
        <div class="progress">
            <div class="progress-bar" id="progressBar"></div>
            <div class="progress-text" id="progressText">0%</div>
        </div>
        <div class="buttons">
            <button id="backBtn">Zurück zur Auswahl</button>
            <button id="resetBtn">Zurücksetzen</button>
            <button id="nextLessonBtn" disabled>Nächste Lektion</button>
        </div>
        <img 
            src="https://www.tippenakademie.de/app/source/public/images/intro/keyboard-colors-new3.png" 
            alt="Farbige Tastatur zur 10-Finger-Methode" 
            class="keyboard-image"
        >
    </div>

    <script>
        // --- Lektionsdaten (JETZT 10 Lektionen) ---
        const lessons = [
            { title: 'Lektion 1: Grundtasten (Mitte)', text: 'asdf jklö asdf jklö fjdksl fjdksl', difficulty: 'Leicht' },
            { title: 'Lektion 2: E und I', text: 'drei eier fiel ein Lied lies sie', difficulty: 'Leicht' },
            { title: 'Lektion 3: U und R', text: 'ruhe turm ruf und du nur rute', difficulty: 'Mittel' },
            { title: 'Lektion 4: T und Z', text: 'zwei tanz Zeit satz jetzt zum Netz', difficulty: 'Mittel' },
            { title: 'Lektion 5: G und H', text: 'gehe hoch Haus geht gern hast du', difficulty: 'Mittel' },
            { title: 'Lektion 6: B und N', text: 'bin ganz bunt bene nimm nahm nach', difficulty: 'Mittel' },
            { title: 'Lektion 7: W und O', text: 'wo was wolke oft Sonne oben Ort', difficulty: 'Schwer' },
            { title: 'Lektion 8: Satzzeichen', text: 'Er fragt: "Wer bist du?" Ich antworte: "Ich bin\'s!"', difficulty: 'Schwer' },
            { title: 'Lektion 9: Zahlen & Groß', text: 'Heute ist der 1. Mai 2025. Wir brauchen 10 Stühle.', difficulty: 'Experte' },
            { title: 'Lektion 10: Letzte Prüfung', text: 'Ein Fuchs geht im Wald spazieren. Plötzlich hört er ein Geräusch. Er versteckt sich schnell hinter einem Baum. Das ist das Ende der Geschichte.', difficulty: 'Meister' },
        ];

        // --- DOM-Elemente & Zustandsvariablen (Unverändert) ---
        const lessonSelection = document.getElementById('lesson-selection');
        const typingArea = document.getElementById('typing-area');
        const lessonList = document.getElementById('lessonList');
        const lessonTitle = document.getElementById('lessonTitle');
        const displayText = document.getElementById('displayText');
        const typingInput = document.getElementById('typingInput');
        const progressBar = document.getElementById('progressBar');
        const progressText = document.getElementById('progressText');
        const accuracyDisplay = document.getElementById('accuracyDisplay');
        const errorCountDisplay = document.getElementById('errorCount');
        const wpmDisplay = document.getElementById('wpmDisplay');
        const resetBtn = document.getElementById('resetBtn');
        const nextLessonBtn = document.getElementById('nextLessonBtn');
        const backBtn = document.getElementById('backBtn');

        let currentLessonIndex = 0;
        let lessonText = '';
        let startTime = null;
        let totalTypedChars = 0;
        let totalErrors = 0;
        let typingInProgress = false;
        let lessonProgress = loadProgress();

        const ACCURACY_THRESHOLD = 90;

        // --- Hauptfunktionen (Unverändert) ---

        function loadProgress() {
            const progress = localStorage.getItem('typingTrainerProgress');
            if (progress) {
                return JSON.parse(progress);
            }
            // Erstellt den Startfortschritt für 10 Lektionen
            return lessons.map((_, index) => ({
                unlocked: index === 0,
                completed: false,
                accuracy: 0
            }));
        }

        function saveProgress() {
            localStorage.setItem('typingTrainerProgress', JSON.stringify(lessonProgress));
            renderLessonList();
        }

        function showLessonSelection() {
            typingArea.classList.remove('visible');
            lessonSelection.classList.add('visible');
            typingInput.value = '';
            typingInProgress = false;
            startTime = null;
        }

        function startLesson(index) {
            currentLessonIndex = index;
            lessonText = lessons[index].text;

            lessonTitle.textContent = lessons[index].title;
            displayText.innerHTML = formatText(lessonText, '');
            typingInput.value = '';
            typingInput.focus();
            
            progressBar.style.width = '0%';
            progressText.textContent = '0%';
            accuracyDisplay.textContent = '0%';
            errorCountDisplay.textContent = '0';
            nextLessonBtn.disabled = true;

            totalTypedChars = 0;
            totalErrors = 0;
            startTime = null;
            typingInProgress = false;

            lessonSelection.classList.remove('visible');
            typingArea.classList.add('visible');
        }

        function renderLessonList() {
            lessonList.innerHTML = '';
            lessons.forEach((lesson, index) => {
                const item = document.createElement('li');
                const progressItem = lessonProgress[index];
                
                let statusClass = '';
                let statusText = '';
                let statusIcon = '';

                if (progressItem.completed) {
                    statusClass = 'completed';
                    statusText = `Abgeschlossen (${progressItem.accuracy}%) 🎉`;
                    statusIcon = '✅';
                } else if (progressItem.unlocked) {
                    statusClass = 'unlocked';
                    statusText = `Fortschritt: ${progressItem.accuracy}%`;
                    statusIcon = '🔓';
                } else {
                    statusClass = 'locked';
                    statusText = 'Gesperrt';
                    statusIcon = '🔒';
                }

                item.classList.add('lesson-item', statusClass);
                item.innerHTML = `
                    <span>${statusIcon} ${lesson.title} (${lesson.difficulty})</span>
                    <span style="font-size:0.9em;">${statusText}</span>
                `;
                
                if (progressItem.unlocked) {
                    item.addEventListener('click', () => startLesson(index));
                }

                lessonList.appendChild(item);
            });
        }

        function formatText(original, typed) {
            let output = '';
            for (let i = 0; i < original.length; i++) {
                const char = original[i];
                let spanClass = '';

                if (i < typed.length) {
                    if (typed[i] === char) {
                        spanClass = 'correct';
                    } else {
                        spanClass = 'incorrect';
                    }
                }

                if (i === typed.length) {
                    spanClass += ' current';
                }

                output += `<span class="${spanClass}">${char === ' ' ? '•' : char}</span>`;
            }
            return output;
        }

        function calculateStats() {
            const typed = typingInput.value;
            const original = lessonText;
            let correctChars = 0;
            let currentErrors = 0;

            for (let i = 0; i < typed.length; i++) {
                if (i < original.length) {
                    if (typed[i] === original[i]) {
                        correctChars++;
                    } else {
                        currentErrors++;
                    }
                }
            }
            
            totalTypedChars = typed.length; 
            totalErrors = currentErrors; 

            const accuracy = original.length > 0 
                ? Math.floor((correctChars / original.length) * 100) 
                : 100;

            const progress = Math.min(Math.floor((typed.length / original.length) * 100), 100);

            let wpm = 0;
            if (startTime && typed.length > 0) {
                const elapsedMinutes = (Date.now() - startTime) / 60000;
                // WPM = (Anzahl korrekte Zeichen / 5) / (Verstrichene Minuten)
                wpm = Math.floor((correctChars / 5) / elapsedMinutes); 
            }
            
            displayText.innerHTML = formatText(original, typed);
            progressBar.style.width = `${progress}%`;
            progressText.textContent = `${progress}%`;
            accuracyDisplay.textContent = `${accuracy}%`;
            errorCountDisplay.textContent = totalErrors;
            wpmDisplay.textContent = wpm;

            if (typed.length >= original.length) {
                typingInput.disabled = true;
                typingInProgress = false;

                const finalAccuracy = Math.floor((correctChars / original.length) * 100);
                
                lessonProgress[currentLessonIndex].accuracy = finalAccuracy;
                if (finalAccuracy >= ACCURACY_THRESHOLD) {
                    lessonProgress[currentLessonIndex].completed = true;
                    if (currentLessonIndex + 1 < lessons.length) {
                        lessonProgress[currentLessonIndex + 1].unlocked = true;
                    }
                    nextLessonBtn.disabled = false;
                    alert(`Super! Lektion ${currentLessonIndex + 1} abgeschlossen mit ${finalAccuracy}% Genauigkeit!`);
                } else {
                    alert(`Leider nur ${finalAccuracy}% Genauigkeit. Du brauchst ${ACCURACY_THRESHOLD}% oder mehr.`);
                    nextLessonBtn.disabled = true;
                }
                saveProgress();
            }
        }

        // --- Event Listener (Unverändert) ---

        typingInput.addEventListener('input', () => {
            if (!typingInProgress && typingInput.value.length > 0) {
                typingInProgress = true;
                startTime = Date.now();
            }
            calculateStats();
        });

        resetBtn.addEventListener('click', () => {
            startLesson(currentLessonIndex);
            typingInput.disabled = false;
        });

        nextLessonBtn.addEventListener('click', () => {
            if (currentLessonIndex + 1 < lessons.length) {
                startLesson(currentLessonIndex + 1);
                typingInput.disabled = false;
            } else {
                alert('Glückwunsch! Du hast alle Lektionen abgeschlossen!');
                showLessonSelection();
            }
        });

        backBtn.addEventListener('click', showLessonSelection);

        // --- Start der Anwendung ---
        renderLessonList();
        showLessonSelection(); 

    </script>
</body>
</html>
