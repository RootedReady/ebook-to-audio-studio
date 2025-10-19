# ebook-to-audio-studio  
  
Rooted Ready eBook To Audio — a portable GUI that converts DOCX files into audiobooks using Piper TTS. Designed to run offline with a self-contained folder structure.  
  
## What this repo contains  
  
- app/ebook_to_audio.pyw — the GUI application    
- packs/PACKS_INDEX.sample.json — example index for voice/piper packs    
- zips/ — optional local storage for your ZIP packs (if you keep them in the repo)    
- checksums.txt — SHA256 checksums for your ZIPs (optional, kept for reference)    
- OUTPUT_SUMMARY.txt — notes about what each ZIP contains (optional)    
- README.md — this file    
  
**Note:**    
- On first run, the app creates a “Rooted Ready eBook To Audio” folder structure inside app/. No installer needed.  
  
## Quick Start (Windows)  
  
1) Install Python 3.10+ and pip if not already installed.    
2) Install dependencies:    

pip install customtkinter python-docx simpleaudio

3) Run the GUI:    
- Double-click app/ebook_to_audio.pyw    
- or from terminal:    
  ```  
  python app/ebook_to_audio.pyw  
  ```  

## Using the app  

- Pick your DOCX.    
- Optional: set a cover image (PNG/JPG).    
- Install Piper binaries:    
- Button: “Install Local Piper ZIP…” (choose a ZIP with piper.exe and DLLs), or    
- Button: “Install Piper Windows (x64)” if you provide a pack URL.    
- Install voices:    
- Button: “Install Local Voices ZIP…” (choose your voices ZIP), or    
- Use the “Install … Pack” buttons if you wired URLs.    
- Use “Dry Run (Detect Sections)” to check structure.    
- “Build Audiobook” to generate audio into output_audio/.  

## Folder layout created by the app  

- bin/ — piper.exe and required DLLs    
- voices/ — voice models (.onnx + .onnx.json)    
- output_audio/ — final WAV/MP3 output (depending on your pipeline)    
- config/ — settings, themes, assets    
- logs/ — run/crash logs    
- tmp/, _tmp.wav/, downloads/, preview/ — temporary working folders    

All of the above live under:    
`app/Rooted Ready eBook To Audio/`  

## Voice files  

Place Piper voice models in:    
`app/Rooted Ready eBook To Audio/voices/`  

Each voice requires:    
- model.onnx    
- model.onnx.json    

The GUI will show a health check and flag missing pairs.  

## Optional packs  

If you’re hosting ZIP packs (voices or Piper), keep their names consistent and store SHA256 values in `checksums.txt`. You can point the `PACKS_INDEX` (inside the app script) to your hosting URLs when ready.  

## Git LFS (optional)  

If you need to store large files in this repo (ZIPs, ONNX, WAV), enable Git LFS locally:  

git lfs install
git lfs track ".zip" ".onnx" ".onnx.json" ".wav" "*.mp3"
git add .gitattributes
git commit -m "configure LFS"

  
This is optional if you don’t push large binaries here.  
  
## License  
  
This repository’s code is licensed under the MIT License. See the LICENSE file for details.  
  
The voice packs and other third-party assets included or referenced in this repo carry their own licenses and credits inside their respective ZIP files.

