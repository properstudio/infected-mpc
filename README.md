# Infected by ProperStyle 1.0.0

A Virus TI / Snow emulation as an instrument plugin for 64-bit Akai MPC standalone hardware.
Free software (GPL-3.0). Polish version below / wersja polska niżej.

---

## English

### What it is
Infected runs the original Virus TI firmware on gearmulator's DSP56300 emulator, inside your MPC, with no computer
attached. It adds its own pages for the MPC's touch screen:

- **MAIN**: bank, sound and the most used controls.
- **BROWSE**: factory and user banks, sound lists, favourites (star a sound, find it under FAVS).
- **LOOP**: a loop recorder that freezes the synth to audio in step with your sequence (the emulator stops, CPU is
  freed). A bounce or resample of a frozen loop lands exactly on the grid.
- **OSC, FILTER, ENV, LFO, FX 1, FX 2, MIX, ARP**: the sound parameters.
- **ARP EDIT**: the Virus user arpeggiator pattern, 32 steps with velocity and length.
- **SETUP**: emulation model (Snow / TI2), buffer, load meters, about.

### Requirements
- A standalone MPC with a 64-bit processor (such as MPC Key 37 G2, Live III, XL). Tested on an MPC Key 37 G2.
  MPCs with a 32-bit processor cannot run it.
- **Your own Virus TI firmware file.** It is not included and cannot be. It comes with Access' official Virus TI OS
  installer; you need a copy you are entitled to use.
- A USB drive or SD card for the MPC, or SSH access to the MPC (developer mode) if you prefer to copy over the network.

### Installation

The download contains the folder **`ProperStyle - VST - Infected`**. It goes into a folder called
**`VST2 Plugins`** at the top of a drive the MPC uses (USB drive, SD card or internal drive). Create `VST2 Plugins`
if it is not there.

**Option A: copy with a card or USB drive (no developer mode needed)**
1. Switch the MPC off and put its drive or SD card into your computer.
2. Copy the whole `ProperStyle - VST - Infected` folder into `VST2 Plugins` on that drive.
3. Copy your firmware file (`.bin`, any name) into
   `VST2 Plugins/ProperStyle - VST - Infected/Content/roms/`.
4. Optional: copy your Virus banks (`.mid` or `.syx` with single dumps) into `.../Content/banks/`.
5. Put the drive back into the MPC and switch it on.

**Option B: copy over the network with SSH (developer mode)**
1. Turn on developer mode on the MPC and note its IP address.
2. From your computer, copy the folder, for example:
   ```
   scp -r "ProperStyle - VST - Infected" "root@<MPC IP>:/media/<drive name>/VST2 Plugins/"
   ```
   then the firmware into `.../Content/roms/` the same way.
3. Restart the MPC (or the MPC application) so it finds the plugin.

**First start**
- Add Infected to a track as a plugin instrument (it is listed under ProperStyle). Booting the firmware takes a few
  seconds. "No ROM" on the screen means the firmware file is missing from `Content/roms`.
- Start with the Snow model. If the sound crackles, raise **Buffer** or lower **DSP Clock** on SETUP.
- The Infected tile in the MPC's Sounds > INSTRUMENTS browser appears after a restart. If tapping it does not load
  the plugin, open `Presets/0000-Default.xpl` in a text editor and replace `%payload-path%` with the path of your
  `VST2 Plugins` folder on the MPC, for example `/media/AKAI USB/VST2 Plugins`.

**Updating**: copy the new `ProperStyle - VST - Infected` folder over the old one. Your firmware, banks and
favourites (`Content/favorites.txt`) stay as long as you do not delete `Content`.

### Known limits
- Single mode only (no multi mode); edits cannot be saved back into a bank yet.
- The live sound reaches the MPC about 20 ms late (buffer plus emulation); frozen loops are on the grid.
- Each emulated DSP needs a core of its own: TI2 mode is heavier than Snow. Watch EMU LOAD and DROPOUTS.

### Support the project
Infected is free and will stay free. If you like it, you can buy me a coffee: **https://ko-fi.com/properstyle**
(the QR code on the SETUP page leads there). Donations are voluntary and do not unlock anything.

### Legal
- Infected is free software under the GNU General Public License, version 3 (`Content/LICENSE.txt`). It comes
  with **no warranty**; you use it at your own risk.
- It is a modified version of **gearmulator** by The Usual Suspects (https://github.com/dsp56300/gearmulator) and
  uses dsp56300, AsmJit, libresample and inMusic's MPC Plugin SDK; full credits in `Content/CREDITS.txt`.
- The complete source code of this release is published next to it (`infected-mpc-source-1.0.0.zip`), as the
  GPL requires.
- **No firmware is included or distributed.** The Virus firmware is Access Music's copyrighted work; supply your
  own copy.
- Infected is **not made, endorsed or supported** by Access Music, Akai Professional / inMusic or Kemper, and has
  nothing to do with the band Infected Mushroom. Virus, Access, Akai and MPC are trademarks of their owners and are
  named here only to describe compatibility.

---

## Polski

### Co to jest
Infected uruchamia oryginalny firmware Virusa TI na emulatorze DSP56300 z projektu gearmulator, bezpośrednio na
MPC, bez komputera. Ma własne strony na ekran dotykowy MPC:

- **MAIN**: bank, brzmienie i najczęściej używane parametry.
- **BROWSE**: banki fabryczne i własne, listy brzmień, ulubione (gwiazdka przy brzmieniu, lista pod FAVS).
- **LOOP**: looper, który zamraża syntezator do audio równo z sekwencją (emulator się zatrzymuje, procesor
  odpoczywa). Zgranie lub resampling zamrożonej pętli trafia dokładnie w siatkę.
- **OSC, FILTER, ENV, LFO, FX 1, FX 2, MIX, ARP**: parametry brzmienia.
- **ARP EDIT**: własny wzór arpeggiatora Virusa, 32 kroki z velocity i długością.
- **SETUP**: model emulacji (Snow / TI2), bufor, wskaźniki obciążenia, informacje.

### Wymagania
- MPC standalone z 64-bitowym procesorem (np. MPC Key 37 G2, Live III, XL). Testowane na MPC Key 37 G2.
  MPC z 32-bitowym procesorem go nie uruchomią.
- **Własny plik firmware Virusa TI.** Nie ma go w paczce i nie może być. Pochodzi z oficjalnego instalatora
  systemu Virus TI od Access; potrzebujesz kopii, do której masz prawo.
- Pendrive lub karta SD do MPC albo dostęp SSH do MPC (tryb deweloperski), jeśli wolisz kopiować przez sieć.

### Instalacja

W paczce jest folder **`ProperStyle - VST - Infected`**. Trafia on do folderu **`VST2 Plugins`** w głównym katalogu
dysku, którego używa MPC (pendrive, karta SD albo dysk wewnętrzny). Jeśli `VST2 Plugins` nie istnieje, utwórz go.

**Sposób A: kopiowanie przez kartę lub pendrive (bez trybu deweloperskiego)**
1. Wyłącz MPC i podłącz jego dysk albo kartę SD do komputera.
2. Skopiuj cały folder `ProperStyle - VST - Infected` do `VST2 Plugins` na tym dysku.
3. Skopiuj swój plik firmware (`.bin`, nazwa dowolna) do
   `VST2 Plugins/ProperStyle - VST - Infected/Content/roms/`.
4. Opcjonalnie: wrzuć swoje banki Virusa (`.mid` albo `.syx` z single dumpami) do `.../Content/banks/`.
5. Włóż dysk z powrotem do MPC i włącz je.

**Sposób B: kopiowanie przez sieć po SSH (tryb deweloperski)**
1. Włącz na MPC tryb deweloperski i sprawdź jego adres IP.
2. Z komputera skopiuj folder, na przykład:
   ```
   scp -r "ProperStyle - VST - Infected" "root@<IP MPC>:/media/<nazwa dysku>/VST2 Plugins/"
   ```
   a potem tak samo firmware do `.../Content/roms/`.
3. Zrestartuj MPC (albo aplikację MPC), żeby znalazło wtyczkę.

**Pierwsze uruchomienie**
- Dodaj Infected do ścieżki jako instrument wtyczkowy (jest pod ProperStyle). Start firmware trwa kilka sekund.
  Napis „No ROM” oznacza brak pliku firmware w `Content/roms`.
- Zacznij od modelu Snow. Jeśli dźwięk trzeszczy, zwiększ **Buffer** albo zmniejsz **DSP Clock** na SETUP.
- Kafelek Infected w przeglądarce Sounds > INSTRUMENTS pojawia się po restarcie. Jeśli dotknięcie go nie wczytuje
  wtyczki, otwórz `Presets/0000-Default.xpl` w edytorze tekstu i zamień `%payload-path%` na ścieżkę do folderu
  `VST2 Plugins` na MPC, na przykład `/media/AKAI USB/VST2 Plugins`.

**Aktualizacja**: skopiuj nowy folder `ProperStyle - VST - Infected` na stary. Firmware, banki i ulubione
(`Content/favorites.txt`) zostają, dopóki nie usuniesz folderu `Content`.

### Ograniczenia
- Tylko tryb single (bez multi); zmian nie da się jeszcze zapisać z powrotem do banku.
- Dźwięk na żywo dociera do MPC około 20 ms później (bufor plus emulacja); zamrożone pętle są na siatce.
- Każdy emulowany DSP potrzebuje osobnego rdzenia: tryb TI2 obciąża bardziej niż Snow. Obserwuj EMU LOAD
  i DROPOUTS.

### Wsparcie
Infected jest darmowy i taki zostanie. Jeśli Ci się podoba, możesz postawić mi kawę:
**https://ko-fi.com/properstyle** (prowadzi tam kod QR na stronie SETUP). Wpłaty są dobrowolne i niczego
nie odblokowują.

### Informacje prawne
- Infected jest wolnym oprogramowaniem na licencji GNU General Public License w wersji 3 (`Content/LICENSE.txt`).
  Jest dostarczany **bez żadnej gwarancji**; używasz go na własną odpowiedzialność.
- Jest zmodyfikowaną wersją **gearmulatora** autorstwa The Usual Suspects (https://github.com/dsp56300/gearmulator)
  i korzysta z dsp56300, AsmJit, libresample oraz MPC Plugin SDK od inMusic; pełna lista w `Content/CREDITS.txt`.
- Pełny kod źródłowy tego wydania jest opublikowany obok niego (`infected-mpc-source-1.0.0.zip`), jak wymaga GPL.
- **Paczka nie zawiera i nie rozpowszechnia firmware.** Firmware Virusa jest utworem chronionym prawem autorskim
  Access Music; używaj własnej kopii.
- Infected **nie jest tworzony, popierany ani wspierany** przez Access Music, Akai Professional / inMusic ani
  Kemper i nie ma nic wspólnego z zespołem Infected Mushroom. Virus, Access, Akai i MPC są znakami towarowymi
  swoich właścicieli i występują tu wyłącznie w celu opisania zgodności.
