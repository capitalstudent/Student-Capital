# Student-Capital
Pianifica la tua sessione senza ansia, ottimizza la gestione del tempo ed evita lo stress da prestazione. Trova risorse libere, scarica dispense gratis, calcola il tuo budget da fuori sede, verifica l'accesso alle borse di studio del tuo ateneo e confrontati in totale anonimato con il nostro Tutor AI per migliorare il tuo metodo di studio.
[gemini-code-1789169369940.js](https://github.com/user-attachments/files/32134192/gemini-code-1789169369940.js)
// 1. Funzione Dispense
        function richiediDispensa() {
            const val = document.getElementById('materiaInput').value;
            if(val.trim() !== '') {
                document.getElementById('dispensaStatus').style.display = 'block';
            } else {
                alert('Inserisci il nome di una materia!');
            }
        }

        // 2. Funzione Calcolo Budget
        function calcolaBudget() {
            const budget = parseFloat(document.getElementById('budgetInput').value);
            if (!isNaN(budget) && budget > 0) {
                document.getElementById('affittoVal').innerText = (budget * 0.50).toFixed(0);
                document.getElementById('spesaVal').innerText = (budget * 0.30).toFixed(0);
                document.getElementById('risparmioVal').innerText = (budget * 0.20).toFixed(0);
                document.getElementById('calculatorResult').style.display = 'block';
            } else {
                alert('Inserisci una cifra valida.');
            }
        }

        // 3. Funzione Reindirizzamento Agevolazioni
        function vaiAdAgevolazioni() {
            const url = document.getElementById('uniSelect').value;
            if (url === 'custom') {
                alert('Invia una segnalazione alla community per aggiungere la tua università!');
            } else if (url !== '') {
                window.open(url, '_blank');
            } else {
                alert('Seleziona un ateneo dalla lista!');
            }
        }

        // 4. Simulazione Chat IA Psicologia
        function inviaMessaggioChat() {
            const input = document.getElementById('userInputChat');
            const chatBox = document.getElementById('chatBox');
            const text = input.value.trim();

            if (text !== '') {
                chatBox.innerHTML += `<div class="chat-msg user"><strong>Tu:</strong> ${text}</div>`;
                input.value = '';
                chatBox.scrollTop = chatBox.scrollHeight;

                setTimeout(() => {
                    chatBox.innerHTML += `<div class="chat-msg bot"><strong>Student AI:</strong> Ricordati che un voto non definisce il tuo valore. Prenditi un momento per staccare, fai una camminata e affronta le cose un passo alla volta. Se hai bisogno di organizzare lo studio, sono qui!</div>`;
                    chatBox.scrollTop = chatBox.scrollHeight;
                }, 1000);
            }
        }

        // 5. Analisi e Correzione Routine con AI
        function analizzaRoutine() {
            const input = document.getElementById('routineInput').value.trim();
            const feedbackBox = document.getElementById('aiFeedback');
            const feedbackText = document.getElementById('feedbackText');

            if (input === '') {
                alert('Inserisci una descrizione della tua routine per ricevere l\'analisi.');
                return;
            }

            // Simulazione di analisi intelligente basata sul testo
            let risposta = "1. **Struttura delle pause:** Assicurati di non superare mai i 90 minuti continuativi senza fare 10 minuti di stacco completo.<br>";
            risposta += "2. **Metodo attivo:** Evita la semplice rilettura o la sottolineatura passiva. Sostituiscile con mappe concettuali o la creazione di domande a risposta chiusa.<br>";
            risposta += "3. **Fine giornata:** Dedica gli ultimi 20 minuti del pomeriggio unicamente al ripasso veloce dei concetti visti il giorno precedente.";

            feedbackText.innerHTML = risposta;
            feedbackBox.style.display = 'block';
        }
