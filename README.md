# BonConverter - pachete portabile

Acest repository contine **doar executabilele** aplicatiei BonConverter.
Codul sursa este intr-un repository separat, privat.

## Descarcare

Mergi la [Releases](../../releases/latest) si descarca:

| Fisier | Rol |
| --- | --- |
| `BonConverter-<versiune>-portable-x64.exe` | aplicatia completa, fara instalare |
| `BonConverter-<versiune>-portable-x64.exe.sha256` | amprenta SHA-256 a executabilului |
| `CITESTE-MA.txt` | instructiuni de utilizare si de mutare a datelor |

## Cerinte

- Windows 10 sau 11, pe 64 de biti
- un folder in care ai drept de scriere (aplicatia isi creeaza acolo datele)
- internet pentru extragerea AI/OCR, verificarea ANAF/VIES si generarea codului QR

Nu este nevoie de Node.js, npm, Python, Docker, WebView2 sau Electron:
Chromium, Node.js, interfata si backend-ul sunt incluse in executabil.

## Primul start

1. Dublu clic pe executabil. Aplicatia se deschide in propria fereastra.
2. Aplicatia creeaza langa executabil folderul `BonConverter-data`, care
   contine setarile, cheile tale API si documentele incarcate.
3. Deschide **Setari API** si adauga cheile tale (OpenRouter, Google AI
   Studio, NVIDIA, Moondream sau OCR.space). Pachetul **nu contine nicio
   cheie** si nicio setare personala; fara cel putin o cheie, extragerea
   datelor din documente nu functioneaza.

Cheile raman pe calculatorul tau si pleaca doar catre furnizorul AI pe care
il alegi. Aplicatia nu are parola de intrare: cine are acces la calculator
sau la adresa LAN a aplicatiei poate folosi aplicatia si poate inlocui
cheile din Setari API.

## Verificarea descarcarii

In PowerShell, in folderul in care ai salvat fisierul:

```powershell
Get-FileHash .\BonConverter-1.5.2-portable-x64.exe -Algorithm SHA256
```

Valoarea afisata trebuie sa fie identica cu cea din fisierul `.sha256`.
In Git Bash sau Linux:

```bash
sha256sum -c BonConverter-1.5.2-portable-x64.exe.sha256
```

## Mutarea aplicatiei pe alt calculator

Inchide aplicatia, apoi copiaza **executabilul impreuna cu folderul
`BonConverter-data`**. Datele nu sunt criptate pe disc, la fel ca orice
fisier obisnuit din folderul tau.
