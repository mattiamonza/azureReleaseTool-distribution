# AzureReleaseTool

Tool desktop per la generazione automatica dei log di rilascio su **Azure DevOps**, sviluppato per FiberCop/WSD Pega.

---

## 📥 Installazione

1. Vai alla pagina [**Releases**](https://github.com/mattiamonza/azureReleaseTool-distribution/releases/latest)
2. Scarica:
   - `launcher.exe` — avviatore principale (usato ogni volta)
   - `AzureTool.exe` — applicazione (aggiornata automaticamente dal launcher)
3. Metti entrambi i file nella **stessa cartella**

> Non è richiesta nessuna installazione aggiuntiva.

---

## ▶️ Avvio

Fai **doppio click su `launcher.exe`**.

Il launcher:
1. Controlla se è disponibile una versione più recente
2. Se sì, scarica e verifica automaticamente `AzureTool.exe` (SHA256)
3. Avvia l'applicazione

> ⚠️ Avvia sempre `launcher.exe`, non `AzureTool.exe` direttamente, per ricevere gli aggiornamenti automatici.

---

## 🔄 Aggiornamenti automatici

Il launcher controlla gli aggiornamenti ad ogni avvio confrontando la versione locale con il [manifest pubblico](https://raw.githubusercontent.com/mattiamonza/azureReleaseTool-distribution/main/version.json).

Se è disponibile una nuova versione:
- Viene scaricata automaticamente in background
- Il checksum SHA256 viene verificato prima dell'installazione
- Una copia di backup del vecchio eseguibile viene mantenuta (`.bak`)

Non è necessaria nessuna azione manuale.

---

## ✅ Verifica integrità file

Per verificare manualmente l'integrità di `AzureTool.exe` prima dell'avvio:

```powershell
# PowerShell
Get-FileHash .\AzureTool.exe -Algorithm SHA256
```

Confronta il risultato con il campo `sha256` nel file [version.json](./version.json) della release corrispondente.

---

## 📦 Versione corrente

| Campo | Valore |
|-------|--------|
| Versione | `0.2.0` |
| SHA256 AzureTool.exe | `ce0ab82aea2e18dc23c28010f96b86ddb8d6f978cda6a4ee9d1f751ab329cefc` |
| Data rilascio | 2026-07-07 |

---

## 🗂️ Dati applicazione

I file di configurazione e i log vengono salvati in:

```
%LOCALAPPDATA%\AzureTool\
├── settings.json     # impostazioni applicazione
├── credentials.json  # credenziali cifrate (DPAPI)
├── logs\             # log giornalieri
├── cache\            # download temporanei
└── download\         # file scaricati
```

---

## ❓ Supporto

Per segnalazioni o richieste contatta il team di sviluppo interno.
