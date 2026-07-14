# AzureReleaseTool

Tool desktop per la generazione automatica dei log di rilascio su **Azure DevOps**, sviluppato per FiberCop/WSD Pega.

---

## 📥 Installazione — Guida passo passo

> ✅ **Nessuna installazione richiesta.** Bastano due file `.exe` nella stessa cartella.

### Passo 1 — Scarica i file

Vai alla pagina **[Releases → Latest](https://github.com/mattiamonza/azureReleaseTool-distribution/releases/latest)** e scarica:

| File | Descrizione |
|------|-------------|
| `launcher.exe` | **Avviatore principale** — è il file da usare ogni volta |
| `AzureReleaseTool.exe` | Applicazione vera e propria |

### Passo 2 — Crea una cartella dedicata

Crea una cartella a tua scelta, ad esempio:
```
C:\Tools\AzureReleaseTool\
```
o anche sul Desktop o in Documenti — la posizione non ha importanza.

### Passo 3 — Metti entrambi i file nella stessa cartella

```
C:\Tools\AzureReleaseTool\
├── launcher.exe      ← scaricato dalla pagina Releases
└── AzureReleaseTool.exe     ← scaricato dalla pagina Releases
```

> ⚠️ **Importante**: i due file devono trovarsi **nella stessa cartella**. Se li separi, il launcher non trova l'applicazione.

### Passo 4 — Avvia l'applicazione

Fai **doppio click su `launcher.exe`**.

L'applicazione si apre. Hai finito.

---

## ▶️ Come avviare l'applicazione

Usa **sempre `launcher.exe`**, non `AzureReleaseTool.exe` direttamente.

Ad ogni avvio il launcher:
1. Controlla se è disponibile una versione più recente
2. Se sì, scarica e installa automaticamente `AzureReleaseTool.exe`
3. Avvia l'applicazione

> Se avvii `AzureReleaseTool.exe` direttamente, l'applicazione funziona ma **non riceverai aggiornamenti automatici**.

---

## 🔄 Aggiornamenti automatici

Gli aggiornamenti avvengono **in modo completamente automatico** ad ogni avvio del launcher:

- Non devi fare nulla
- Il launcher scarica il nuovo `AzureReleaseTool.exe`, ne verifica l'integrità (SHA256) e lo sostituisce
- Una copia di backup del vecchio eseguibile viene mantenuta (file `.bak` nella stessa cartella)

### ⚠️ Nota sul launcher stesso

Il `launcher.exe` **non si auto-aggiorna**: aggiorna solo `AzureReleaseTool.exe`.

Se ricevi comunicazione di una nuova versione del launcher, dovrai scaricare manualmente il nuovo `launcher.exe` dalla pagina Releases e sostituire quello esistente nella tua cartella. Questo evento è raro.

---

## ✅ Verifica integrità file (opzionale)

Per verificare che il file scaricato sia autentico, apri **PowerShell** nella cartella di installazione ed esegui:

```powershell
Get-FileHash .\AzureReleaseTool.exe -Algorithm SHA256
```

Confronta il risultato con il campo `sha256` nel file [version.json](./version.json).

---

## 📦 Versione corrente

| Campo | Valore |
|-------|--------|
| Versione | `1.0.2` |
| SHA256 AzureReleaseTool.exe | `7717447359667bc4ef18f1245fe61c8cb6cf661786666d02201cff7bbe4c303e` |
| Data rilascio | 2026-07-14 |

---

## 🗂️ Dove vengono salvati i dati

L'applicazione salva automaticamente configurazione, credenziali e log in:

```
%LOCALAPPDATA%\AzureReleaseTool\
├── settings.json      # impostazioni applicazione
├── credentials.json   # credenziali cifrate (Windows DPAPI)
├── logs\              # log giornalieri con rotazione automatica
├── cache\             # file temporanei durante aggiornamenti
└── download\          # file scaricati
```

Puoi aprire questa cartella digitando `%LOCALAPPDATA%\AzureReleaseTool` nella barra degli indirizzi di Esplora File.

---

## ❓ Supporto

Per segnalazioni o richieste contatta il team di sviluppo interno.
