# ComfyUI-Installer-GUI-Italian
Windows ComfyUI-Installer-GUI-Italian
# ComfyUI Installer GUI - Standard & Pro

🇬🇧 English version available here: [ComfyUI-Installer-GUI](https://github.com/Karmabu/ComfyUI-Installer-GUI)

Questa GUI consente di installare **ComfyUI** in due modalità differenti:

## Modalità disponibili

### ✅ Comfy Standard
- Richiede:
  - Python 3.12.9
  - CUDA Toolkit 12.4
- Azioni eseguite:
  - Clonazione del repository ComfyUI
  - Creazione di ambiente virtuale **esterno** alla cartella ComfyUI
  - Installazione di:
    - PyTorch 2.6.0 con supporto CUDA 12.4
    - Requirements da `requirements.txt`
    - onnxruntime-gpu, wheel, setuptools, packaging, ninja
    - accelerate, diffusers, transformers
    - Generazione di:
    - `Run_Comfyui.bat`
    - `Activate_Venv.bat`
    - `Update_Comfy.bat`
  - Clonazione automatica dei nodi:
    - ComfyUI-Manager
    - ComfyUI-Crystools

### 🔑 Comfy Pro
(Triton 3.2.0 per Python 3.12 & SageAttention - compilazione inclusa)
- Richiede:
  - Python 3.12.9
  - CUDA Toolkit 12.4
- Azioni eseguite:
  - Tutto quanto previsto dalla versione **Standard**
  - Installazione aggiuntiva di:
    - Triton 3.2.0 per Python 3.12
    - SageAttention (con compilazione automatica)
  - Verifiche avanzate:
    - Presenza Visual Studio Build Tools 2022
    - Presenza e configurazione `cl.exe` nel PATH
    - Ambiente di compilazione correttamente configurato per moduli nativi

## Funzionalità della GUI
- ☑ Selezione fra **Comfy Standard** e **Comfy Pro** (mutualmente esclusivi)
- 📂 Caricamento JSON personalizzato
- 📃 Visualizzazione informativa (caricata da `info_comfyui_versions.json`)
- 🔍 Pulsante "Verifica Requisiti" con:
  - Controllo Python/CUDA installati
  - Verifica VS Build Tools e `cl.exe`
  - Output dettagliato nella console (tema scuro con testo verde)
- ▶ Pulsante "Esegui Installazione" che:
  - Esegue ogni comando del JSON in sequenza
  - Logga risultati in tempo reale nell'interfaccia

## File supportati

### `prerequisites_check.json` (TEST)
- Caricato all'avvio della GUI
- Descrive e verifica:
  - Modalità Standard: Python 3.12.9 + CUDA 12.4
  - Modalità Pro: include controlli su VS Build Tools e compilatore C++

### `install_standard.json` (INSTALLAZIONE STANDARD)
- Contiene:
  - Comandi per clonazione, installazione pacchetti, creazione batch file

### `install_full_comfyui.json` (INSTALLAZIONE PRO)
- Contiene:
  - Tutto lo script completo
  - Inclusa installazione di Triton, SageAttention e pulizia cache

## Architettura & Design
- Architettura **batch-driven**: la GUI genera ed esegue script reali
- Nessuna necessità di privilegi amministrativi
- **Personalizzabile** tramite JSON
- Funziona **offline** (eccetto git e pip)

---![italiano](https://github.com/user-attachments/assets/210395f9-1b94-4b37-b9fa-f46922695bed)

# Guida per Principianti - Installazione di ComfyUI Installer GUI

Benvenuto! Questa guida ti accompagnerà passo passo nell'installazione di tutti i prerequisiti necessari per eseguire **ComfyUI Installer GUI**, sia in modalità Standard che Pro.

---

## ✅ Cosa Devi Installare

| Requisito                        | Versione | Modalità | Descrizione |
|----------------------------------|----------|-----------|-------------|
| Python                           | 3.12.9   | Tutte     | Necessario per eseguire ComfyUI e creare ambienti virtuali |
| Git                              | Ultima   | Tutte     | Necessario per clonare il repository ComfyUI da GitHub |
| CUDA Toolkit                     | 12.4     | Tutte     | Necessario per sfruttare la GPU (solo per schede NVIDIA) |
| Visual Studio Community 2022     | Ultima   | Solo Pro  | Necessario per compilare SageAttention e Triton |

---

## 1. Installa Python 3.12.9

- Visita: https://www.python.org/downloads/release/python-3129/
- Scarica il **Windows Installer (64-bit)**
- Avvia l'installer:
  - ✅ Spunta "Add Python to PATH"
  - ✅ Clicca su "Install Now"

### Verifica l'installazione:
Apri il **Prompt dei Comandi** e digita:
```
python --version
```
Dovresti vedere:
```
Python 3.12.9
```

---

## 2. Installa Git

- Vai su: https://git-scm.com/download/win
- Scarica e installa Git per Windows
- Lascia tutte le opzioni predefinite durante l'installazione

### Verifica l'installazione:
Apri il **Prompt dei Comandi** e digita:
```
git --version
```
Dovresti vedere qualcosa come:
```
git version 2.xx.x.windows.1
```

---

## 3. Installa CUDA Toolkit 12.4

- Visita: https://developer.nvidia.com/cuda-downloads
- Seleziona:
  - Sistema Operativo: **Windows**
  - Versione: **12.4**
  - Architettura: **x86_64**
  - Tipo di Installer: **Network Installer** o **Local Installer**
- Completa l'installazione e riavvia il PC

### Verifica l'installazione:
Apri il **Prompt dei Comandi** e digita:
```
nvcc --version
```
Dovresti vedere qualcosa come:
```
Cuda compilation tools, release 12.4, V...
```

---

## 4. Installa Visual Studio Community 2022 (solo Pro)

- Visita: https://visualstudio.microsoft.com/it/vs/community/
- Clicca su **"Scarica"**
- Durante l'installazione:
  - ✅ Seleziona **Sviluppo desktop con C++**
  - ✅ (Facoltativo) Seleziona anche "Sviluppo Python"
- Completa l'installazione e riavvia il PC

### Verifica la presenza del compilatore cl.exe:
Apri il **Prompt dei Comandi** e digita:
```
where cl.exe
```
Se è tutto corretto, vedrai un percorso come:
```
C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Tools\MSVC\<version>\bin\Hostx64\x64\cl.exe
```

---

## Tutto Pronto!
Una volta completati questi passaggi, puoi avviare la **ComfyUI Installer GUI** e procedere all'installazione in modalità **Standard** o **Pro**.

Hai bisogno di aiuto? Visita il nostro [GitHub repository](https://github.com/Karmabu/ComfyUI-Installer-GUI)

## Autori & Supporto
- Repo GitHub: `coming soon...`
- Contatti: `karma3u + chatgpt = install wizard`

> Made with ❤ using LLM + batch magic  
> by **Karm3u** and **ChatGPT**

