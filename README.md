### 📘 SAV Animation Ops

---

#### 🔹 Introduzione
SAV Animation Ops è un addon per Blender pensato per semplificare e automatizzare le operazioni ripetitive tipiche della produzione animata. Permette di gestire rapidamente la risoluzione delle strip nella NLA, commutare tra rig e proxy dei personaggi, e linkare asset da altre scene in modo ordinato e coerente.

È ideale per pipeline strutturate, dove più artisti lavorano su diverse sequenze e shot, garantendo uniformità e risparmio di tempo.

---

#### 🧩 Moduli Principali

##### 1. 🛒 Strips Resolution
Questo modulo consente di passare velocemente tra versioni ad alta e bassa risoluzione delle strip nella Non Linear Animation (NLA), utile per ottimizzare performance durante l'animazione o il playback.

- **Pannello:** `SAV Strips Resolution`
- **Funzioni:**
  - `Update Tags`: Analizza le strip presenti nella NLA e assegna tag personalizzati (HIGH o LOW) in base alla loro natura o nome.
  - `All Strips HighRes`: imposta tutte le strip taggate su `HIGH`, utile in fase di review finale.
  - `All Strips LowRes`: forza tutte le strip in `LOW`, ideale per lavorare in realtime.
  - `Toggle Resolution On Selected`: cambia risoluzione solo sulle strip selezionate nella NLA.
- **Guida ai colori:**
  - 🟧 Arancione: Strip ad alta risoluzione (modello completo, texture, shape keys attive, ecc.)
  - 🟪 Viola: Strip a bassa risoluzione (modello semplificato o senza dettagli inutili per l'animatore)

🔍 *Consiglio:* Assicurati che ogni asset abbia versioni HIGH/LOW ben definite nei file di partenza per sfruttare appieno il sistema.

---

##### 2. 🚗 Proxy Switcher
Permette di passare al volo tra proxy e rig per ciascun personaggio. Il proxy è una versione leggera del rig, utile per l'animazione veloce o il blocking.

- **Pannello:** `SAV Proxy Switcher`
- **Parametri globali:**
  - `Animation Layers`:
    - `Update`: aggiorna i layer di animazione per riflettere le modifiche recenti (es. aggiunta controlli o nuove ossa).
    - `Keep`: conserva i layer correnti così come sono.
  - `All Rigs`: converte tutti i personaggi attivi in scena al loro Rig completo.
  - `All Proxy`: sostituisce tutti i rig con la loro versione Proxy.
- **Per personaggio:**
  - Ogni asset viene riconosciuto dal nome (es. "Gom Rafilotto") e mostra due pulsanti:
    - `Switch to Proxy`: passa alla versione leggera
    - `Switch to Rig`: torna alla versione completa per la finalizzazione

📌 *Nota:* Il sistema gestisce correttamente le librerie linkate, mantenendo i riferimenti originali.

---

##### 3. 📦 MAD Linking
Modulo pensato per velocizzare il processo di linking tra collezioni comuni (es. Personaggi, Props, Set) da una scena madre.

- **Accesso:**
  - Click destro su oggetto o collezione → `MAD Tools > MAD Linking`
- **Opzioni disponibili:**
  - `Link Object > [CHR_sho001, PRP_sho001, SET_sho001]`
  - `Link Collection > [CHR_sho001, PRP_sho001, SET_sho001]`
- **Funzionalità:**
  - Semplifica la condivisione degli asset tra file, mantenendo organizzazione e coerenza tra shot.
  - Evita duplicazioni e favorisce la centralizzazione delle risorse.

🧠 *Pro tip:* Se il tuo progetto segue uno standard di nomi, il modulo rileva automaticamente le collezioni corrette da linkare.

---

##### 4. 📚 Gestione Shot e Sequenze
L’addon sfrutta il naming convention delle scene per identificare correttamente le risorse da utilizzare.

- Esempi:
  - `SAV_seq007_edit`: scena di montaggio o controllo
  - `SAV_seq007_sho003`: shot animabile derivato dalla sequenza principale

Questo naming permette all’addon di adattarsi dinamicamente al contesto, assegnando le collezioni e personaggi corretti a seconda del nome dello shot attivo.

🔄 *Workflow consigliato:* Lavora sempre con nomi coerenti per facilitare il riconoscimento automatico da parte dei moduli di Proxy e Linking.

---

#### 🛠️ Note Finali
- Tutti i moduli sono **non distruttivi**: puoi sempre tornare allo stato precedente.
- L’addon è compatibile con asset linkati e collezioni istanziate.
- La modularità consente aggiornamenti futuri o l’integrazione con altri strumenti pipeline.
