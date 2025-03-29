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
  - Pulizia delle cache Triton e TorchInductor
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

---

## Autori & Supporto
- Repo GitHub: `coming soon...`
- Contatti: `karma3u + chatgpt = install wizard`

> Made with ❤ using LLM + batch magic  
> by **Karm3u** and **ChatGPT**

