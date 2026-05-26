# Home Assistant Retro TUI


## Funksjoner

- 🎨 **Retro interface** 
- 🏠 **Områdebasert filtrering** - organiser enheter etter områder i ditt hjem
- 🔍 **Søk i sanntid** - søk etter entities eller navn
- ⭐ **Favoritter** - lagre og raskt få tilgang til viktige enheter
- 💡 **Full kontroll** - toggl lyskilder, brytere, automasjoner, scripts, climate-enheter og mer
- 📊 **Direkte innstillinger** - juster brightness, temperaturer, farger, kilder osv.
- 🔌 **WebSocket-tilkobling** - få sanntidsoppdateringer fra Home Assistant

## Installasjon

### Mac

#### Forutsetninger
- Python 3.9 eller høyere
- `pip` (pakkebehandler)

#### Trinn-for-trinn

1. **Klone eller last ned prosjektet:**
   ```bash
   cd ~/ha-tui
   ```

2. **Opprett virtuelt miljø:**
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```

3. **Installer avhengigheter:**
   ```bash
   pip install requests websocket-client
   ```

4. **Rediger konfigurationen:**
   ```bash
   nano Retro-UI-py
   ```
   Endre disse linjene:
   ```python
   HA_URL = "http://your-ha-ip:8123"  # Bytt til din HA-URL
   TOKEN = "your-long-lived-token"     # Lag token i HA (Profil → Long-lived access tokens)
   ```

5. **Kjør programmet:**
   ```bash
   .venv/bin/python Retro-UI-py
   ```

### Windows

#### Forutsetninger
- Python 3.9 eller høyere fra [python.org](https://www.python.org/downloads/)
- Git Bash eller PowerShell

#### Trinn-for-trinn

1. **Last ned eller klone prosjektet** til en mappe

2. **Åpne PowerShell** og naviger til mappen:
   ```powershell
   cd C:\Path\To\ha-tui
   ```

3. **Opprett virtuelt miljø:**
   ```powershell
   python -m venv .venv
   .venv\Scripts\Activate.ps1
   ```
   
   *Hvis du får en feilmelding om execution policy, kjør:*
   ```powershell
   Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
   ```

4. **Installer avhengigheter:**
   ```powershell
   pip install requests websocket-client
   ```

5. **Rediger konfigurationen:**
   - Åpne `Retro-UI-py` med en tekstbehandler (f.eks. Notepad++)
   - Endre:
     ```python
     HA_URL = "http://din-ha-ip:8123"
     TOKEN = "Din-long-lived-token"
     ```

6. **Kjør programmet:**
   ```powershell
   .venv\Scripts\python.exe Retro-UI-py
   ```

### Linux (Ubuntu/Debian)

#### Forutsetninger
- Python 3.9 eller høyere
- `pip`

#### Trinn-for-trinn

1. **Installer Python og pip:**
   ```bash
   sudo apt update
   sudo apt install python3 python3-pip python3-venv
   ```

2. **Klone eller last ned prosjektet:**
   ```bash
   cd ~/ha-tui
   ```

3. **Opprett virtuelt miljø:**
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```

4. **Installer avhengigheter:**
   ```bash
   pip install requests websocket-client
   ```

5. **Rediger konfigurationen:**
   ```bash
   nano Retro-UI-py
   ```
   Endre:
   ```python
   HA_URL = "http://your-ha-ip:8123"
   TOKEN = "your-long-lived-token"
   ```

6. **Kjør programmet:**
   ```bash
   .venv/bin/python Retro-UI-py
   ```

## Førstegangs oppsett

### Få Long-Lived Access Token fra Home Assistant

1. Åpne Home Assistant i nettleser
2. Klikk på ditt profilbilde (nederst i venstremeny), trykk sikkerhet og generer token nederst på siden
3. Kopier tokenet og limk inn i `Retro-UI-py`

### Konfigureringsfilen

Første gang du kjører programmet, opprettes en konfigfil i `~/.ha_dos_tui.conf`. Her lagres:
- Favoritter
- Tema-valg
- Logg-modus
- Siste visningstype

## Brukerveiledning

### Navigasjon

| Tast | Handling |
|------|----------|
| **Tab** | Gå til neste panel (Areas → Domener → Enheter → Detaljer) |
| **Shift+Tab** | Gå til forrige panel |
| **↑/↓** | Navigerer opp/ned i valgt panel |
| **←/→** | Navigerer venstre/høyre (for meny) |
| **Enter** | Velg enhet eller utfør handling |
| **Space** | Toggle enhet (på/av) |

### Kommandoer

| Tast | Handling |
|------|----------|
| **s** | Åpne søk |
| **f** | Legg til/fjern favoritt |
| **d** eller **F2** | Bytt til favorites-visning |
| **c** | Nullstill søk |
| **l** | Åpne full logg |
| **m** | Åpne meny (Tema, Visning, Logg, Scripts, Automations) |
| **t** | Rediger tittel |
| **r** | Manuell refresh av enheter |
| **q** eller **F10** | Avslutt |



<img width="1171" height="699" alt="Skjermbilde 2026-05-26 kl  13 22 38" src="https://github.com/user-attachments/assets/6f7c7d8e-da30-4f30-9bdb-8989c72f7c76" />
<img width="1169" height="703" alt="Skjermbilde 2026-05-26 kl  13 30 30" src="https://github.com/user-attachments/assets/0b64751c-54eb-4081-81a1-416ac11a15dc" />
<img width="1168" height="698" alt="Skjermbilde 2026-05-26 kl  13 29 45" src="https://github.com/user-attachments/assets/48d35aed-1b32-4331-9a0f-f1f2cb3a9a5b" />
<img width="1170" height="701" alt="Skjermbilde 2026-05-26 kl  13 29 35" src="https://github.com/user-attachments/assets/9e5e8561-6aad-4ce0-aaa6-640445019fb9" />
<img width="1174" height="701" alt="Skjermbilde 2026-05-26 kl  13 29 23" src="https://github.com/user-attachments/assets/1634c058-d374-4ffa-a303-fbd9fcfb9194" />
<img width="1168" height="703" alt="Skjermbilde 2026-05-26 kl  13 28 39" src="https://github.com/user-attachments/assets/8bc31c5e-c4a6-4d8f-825e-f8d59518e8d3" />
<img width="1169" height="701" alt="Skjermbilde 2026-05-26 kl  13 28 30" src="https://github.com/user-attachments/assets/a5b76a8f-3434-4f8e-bcbd-2fee37047c3c" />