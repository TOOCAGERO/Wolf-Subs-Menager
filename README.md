# Wolf-Subs Menager

**Polski** | [English](#english)

Narzędzie Windows do wyciągania napisów z filmów MKV oraz porządkowania plików ASS.
Twórcy aplikacji: **Dierde i TOOCAGERO**.


## Co robi aplikacja

- Wyszukuje napisy w MKV, wybiera obsługiwane angielskie lub polskie ścieżki i wyciąga je do ASS.
- Ręcznie wyciąga wybrane fonty i rozdziały XML, bez instalowania fontów.
- Pozwala dodać gotowe ASS, również zawierające oryginał i tłumaczenie.
- Porządkuje materiał w grupy DIALOG, TS, OP, END i Komentarze.
- Zachowuje rozpoznane powiązania tłumaczeń i kolejność wewnątrz rozpoznanych bloków efektów.
- Przygotowuje angielskie ASS do trybu tłumacza Kainote. Nowe jednojęzyczne polskie ASS sortuje bez automatycznego włączania tego trybu.
- Zapisuje wynik osobno. Nie tłumaczy tekstów i nie generuje efektów.

**Przed sortowaniem zrób kopię zapasową.** Najlepiej pracować na kopii materiału.
Po zapisie sprawdź wynik w Kainote i z obrazem, szczególnie przy złożonych efektach.
Ochrona rozpoznanych struktur nie stanowi gwarancji dla każdego niestandardowego pliku.

## Dwa warianty do pobrania

| Wariant | Dla kogo | Obsługa MKVToolNix |
| --- | --- | --- |
| **Lite** | [Masz już MKVToolNix](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.3/Wolf-Subs-Menager-1.5.3-Lite.exe) | Program szuka go w typowych lokalizacjach. Gdy nie znajdzie, wskażesz folder ręcznie. |
| **Full** | [Nie chcesz osobno instalować MKVToolNix](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.3/Wolf-Subs-Menager-1.5.3-Full.exe) | EXE zawiera potrzebne narzędzia. Przy pierwszym uruchomieniu przygotuje je w wybranym lub domyślnym folderze; kolejne starty wykorzystają zachowane pliki. |
| **Instrukcja PDF** | [Pobierz PDF — polski](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.3/Wolf-Subs-Menager-Guide-PL.pdf) · [Pobierz PDF — angielski](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.3/Wolf-Subs-Menager-Guide-EN.pdf) | Instrukcja krok po kroku z obrazkami, wspólna dla Lite i Full. |


Oba warianty zawierają te same funkcje aplikacji, języki i instrukcje.
Nie wymagają instalatora ani instalacji Pythona. Przy pierwszym starcie zapisują
potrzebne pliki w osobnym folderze. Kolejne starty używają tych samych plików;
brakujące lub uszkodzone składniki są odtwarzane z EXE.
Przygotowanie składników nie jest instalowaniem graficznej aplikacji MKVToolNix.
Full nie pobiera składników z Internetu.

Lite 1.5.3 ma **60,23 MB** do pobrania. Jego przygotowane pliki zajmują dodatkowo
około **59,77 MB**; pobrany EXE pozostaje na dysku. Full ma **129,52 MB** do pobrania,
a jego przygotowane pliki zajmują dodatkowo około **128,95 MB**.

Full korzysta z narzędzi MKVToolNix 103.0 w wydaniu MSYS2 UCRT64. [Odpowiadające źródła,
receptury, patche i informacje o budowaniu](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.0/Wolf-Subs-Menager-1.5.0-Full-Third-Party-Sources.zip) są osobną paczką dla osób zainteresowanych kodem tych składników.
Do zwykłej pracy wystarczy EXE. [Instrukcja użycia zmodyfikowanej biblioteki](LIBRARY-REPLACEMENT.txt).

## Zmiany w 1.5.3

- Lepsze rozpoznanie wielowierszowych plansz TS z tagów i układu. Nazwy Q1/Q10/Q100 nie wyznaczają kategorii. Samo formatowanie, kolor lub pozycja nie zmieniają dialogu w TS.
- Ręczne korekty kart pozostają po zapisie i ponownym otwarciu. Rozpoznane piosenki, drzewka, efekty oraz pary tłumaczeń zachowują swoje relacje i kolejność. Niejednoznaczne przypadki nadal wymagają sprawdzenia.
- Gdy brak obsługiwanych angielskich napisów, program wybiera polskie z metadanych ścieżki. Nazwa pliku nie musi zawierać PL.
- Nowe jednojęzyczne polskie ASS są sortowane bez automatycznego trybu tłumacza. Istniejące pary EN/PL i ich ustawienia pozostają zachowane.
- Rozwijana lista **Fonty i rozdziały**: każdy font osobno, nazwa/MIME/rozmiar, ręczne zaznaczanie i eksport. Rozdziały są osobnym XML. Zapis odbywa się od razu w wybranym miejscu; fonty nie są instalowane.
- Zaktualizowane instrukcje PL i EN z obrazkami, po siedem stron.

## Automatyczna podmiana od 1.5.2

Przycisk **Aktualizuj** pobiera i sprawdza właściwy wariant, zachowuje kopię cofnięcia, zamyka program i uruchamia nowy EXE w dokładnie tym samym miejscu i pod tą samą nazwą. Ustawienia i katalog składników pozostają zachowane. Można anulować przed podmianą; niezapisane napisy i trwająca praca blokują aktualizację. Błąd startu uruchamia próbę przywrócenia poprzedniej wersji.

**Jednorazowe przejście z 1.5.1:** stary przycisk Pobierz tylko pobiera plik. Pobierz 1.5.2, zamknij starą aplikację i ręcznie uruchom nowy EXE w folderze starego programu, pozostawiając tam plik ustawień. Dopiero następne aktualizacje korzystają z automatycznej podmiany.

## Poprawki 1.5.1

W Preferencjach wybierzesz zapis napisów w folderze wyników albo obok każdego źródłowego MKV. Wybór jest zapamiętywany. Importowane ASS nadal korzystają z folderu wyników. Podgląd ma zwijane szczegóły tekstu i kodów ASS, pełne ostrzeżenia oraz stopkę z zapisem poza obszarem tabeli. Wybór języka instrukcji zachowuje ciemne tło.

## Ustawienia i instrukcje

[Instrukcja po polsku (PDF)](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.3/Wolf-Subs-Menager-Guide-PL.pdf) · [Instrukcja po angielsku (PDF)](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.3/Wolf-Subs-Menager-Guide-EN.pdf)

Rozwijane menu Ustawienia otwiera osobne okna: **Instrukcja**, **Aktualizacja**,
**Rozmiar okna**, **Język interfejsu**, dodatkowe preferencje i **O aplikacji**.
Języki interfejsu: polski, angielski, niemiecki i niderlandzki.
Instrukcje PDF są po polsku i angielsku: krótki start, dokładne kroki i obrazy
pokazujące wybór plików, ekstrakcję, sortowanie, podgląd i zapis.
Okna mają większe logo, własny tytuł i dolny przycisk **Zamknij**.

## Aktualizacje bez szukania na stronie

W programie wybierz **Ustawienia → Aktualizacja → Sprawdź aktualizację → Aktualizuj**. Od 1.5.2 następne wydania mogą zastąpić ten sam EXE i uruchomić go ponownie z ustawieniami. Nie trzeba konta GitHub. W 1.5.1 pozostaje jednorazowe ręczne uruchomienie pobranego 1.5.2, opisane wyżej.

## Autorzy i składniki

### MKVToolNix

**MKVToolNix** to zewnętrzny zestaw narzędzi autorstwa i pod opieką
**Moritza Bunkusa (mosu)**, udostępniany na licencji **GNU GPL v2**.
Pozwala między innymi odczytywać informacje o plikach Matroska, wyciągać
ścieżki napisów i inne ścieżki oraz łączyć i dzielić pliki MKV.
Nasza aplikacja korzysta z narzędzi `mkvmerge` i `mkvextract`.

- [Oficjalna strona MKVToolNix](https://mkvtoolnix.download/)
- [Pobierz MKVToolNix dla Windows od autora](https://mkvtoolnix.download/downloads.html#windows)
- [Dokumentacja i opis narzędzi](https://mkvtoolnix.download/docs.html)
- [Źródła MKVToolNix](https://mkvtoolnix.download/source.html)

### Nasza aplikacja i pozostałe składniki

Autorska część aplikacji: Dierde i TOOCAGERO. Twórcy nie zezwalają na jej
modyfikacje ani zmiany funkcjonalności bez ich zgody. To publiczne repozytorium
z wydaniami i dokumentacją; publiczny dostęp nie oznacza otwartej licencji na własny kod aplikacji.

MKVToolNix i pozostałe zewnętrzne składniki zachowują własne licencje i prawa
ich autorów. Informacje o dołączonych wersjach, teksty licencji i wymagane
materiały źródłowe są dołączone do odpowiedniego wydania.

---

## English

**Wolf-Subs Menager** is a Windows tool for extracting text subtitles from MKV
videos and organising ASS subtitles. Created by **Dierde and TOOCAGERO**.


### What it does

- Finds supported English or Polish subtitle tracks in MKV and extracts them to ASS.
- Manually extracts selected fonts and chapter XML without installing fonts.
- Imports existing ASS files, including original/translation pairs.
- Organises records into DIALOG, TS, OP, END and Comments.
- Preserves recognised translation relationships and internal order of recognised effect blocks.
- Prepares English ASS for Kainote translator mode; new monolingual Polish files are sorted without automatically enabling it.
- Saves separate output files. It does not translate text or generate effects.

**Back up your files before sorting and work on copies.** Inspect saved results
in Kainote and against the video, especially for complex effects. Protection of
recognised structures is not a guarantee for every custom subtitle format or effect.

### Choose a download

| Edition | Intended use | MKVToolNix |
| --- | --- | --- |
| **Lite** | [You already have MKVToolNix](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.3/Wolf-Subs-Menager-1.5.3-Lite.exe) | Searches common installation locations; manual folder selection remains available. |
| **Full** | [You do not want to install MKVToolNix separately](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.3/Wolf-Subs-Menager-1.5.3-Full.exe) | Contains the required tools. On first launch it prepares components in a selected or default folder; later launches reuse those files. |
| **PDF guide** | [Download Polish PDF](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.3/Wolf-Subs-Menager-Guide-PL.pdf) · [Download English PDF](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.3/Wolf-Subs-Menager-Guide-EN.pdf) | Illustrated step-by-step guide for both Lite and Full. |


Both editions contain the same application features, languages and guides.
No installer or Python installation is required. The first launch prepares
support files in a separate folder. Later launches reuse them; missing or
damaged components can be restored from the EXE. Full does not download tools.

Lite 1.5.3 is a **60.23 MB** download. Prepared files use about **59.77 MB** of
additional disk space; the downloaded EXE also remains on disk. Full is a
**129.52 MB** download and uses about **128.95 MB** for prepared files.

Full uses MKVToolNix 103.0 from MSYS2 UCRT64. Its [corresponding sources, recipes,
patches and build metadata](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.0/Wolf-Subs-Menager-1.5.0-Full-Third-Party-Sources.zip) are a separate package for developers.
For normal use download the EXE. [Using a compatible modified library](LIBRARY-REPLACEMENT.txt).

### Changes in 1.5.3

- Better recognition of multiline screen cards from tags and layout. Q1/Q10/Q100 names do not define categories. Formatting, colour or positioning alone do not turn dialogue into TS.
- Manual card corrections survive saving and reopening. Recognised songs, trees, effects and translation pairs retain their relationships and internal order. Ambiguous cases still need review.
- Supported Polish tracks are selected when supported English tracks are unavailable, using track metadata without requiring PL in the filename.
- New monolingual Polish ASS files are sorted without automatically enabling translator mode. Existing EN/PL pairs and settings are preserved.
- Expand **Fonts and chapters** to select and extract individual fonts with filename/MIME/size. Chapters are separate XML. Items are saved immediately to the selected output location; fonts are not installed.
- Updated illustrated Polish and English guides, seven pages each.

### Automatic replacement from 1.5.2

**Update** downloads and verifies the matching edition, retains a rollback copy, closes the application and restarts the new EXE at exactly the same path and filename. Settings and the component folder are retained. Cancellation is available before replacement; ongoing work and unsaved subtitles block updating. A failed startup triggers an attempt to restore the previous version.

**One-time transition from 1.5.1:** its old Download button only downloads a file. Download 1.5.2, close the old application and manually start the new EXE in the old application's folder with the settings file kept there. Subsequent updates can replace it automatically.

### Changes in 1.5.1

Preferences remember whether MKV subtitles go to the output folder or beside each source MKV. Imported ASS files continue using the output folder. Preview provides collapsible full-text and ASS-code details, complete warnings and a save footer outside the table area. Guide language choices retain their dark background.

### Interface, guides and updates

[Polish guide (PDF)](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.3/Wolf-Subs-Menager-Guide-PL.pdf) · [English guide (PDF)](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.3/Wolf-Subs-Menager-Guide-EN.pdf)

The Settings menu opens separate windows for the guide, updates, window
size, interface language, other preferences and About. Interface languages:
Polish, English, German and Dutch. Illustrated PDF guides: Polish and English.
Helper windows have a larger logo, their own title and a bottom **Close** button.

Choose **Settings → Update → Check for updates → Update**. From 1.5.2, subsequent releases can replace the same EXE and restart it with your settings. No GitHub account is required. Version 1.5.1 requires the one-time manual launch of downloaded 1.5.2 described above.

### Authors and third-party components

#### MKVToolNix

**MKVToolNix** is an external tool suite authored and maintained by
**Moritz Bunkus (mosu)** and distributed under **GNU GPL v2**.
Its features include inspecting Matroska files, extracting subtitle and other
tracks, and merging or splitting MKV files. Our application uses the
`mkvmerge` and `mkvextract` tools.

- [Official MKVToolNix website](https://mkvtoolnix.download/)
- [Download MKVToolNix for Windows from the author](https://mkvtoolnix.download/downloads.html#windows)
- [Tool documentation](https://mkvtoolnix.download/docs.html)
- [MKVToolNix source code](https://mkvtoolnix.download/source.html)

#### Our application and other components

The application's own work is by Dierde and TOOCAGERO. The authors do not permit
modifications to their own part or its functionality without their consent.
This is a public distribution/documentation repository, not an open-source
licence grant for the application's own code.

MKVToolNix and other third-party components retain their own licences and
authors' rights. Version notices, licence texts and required source materials
accompany the relevant release.
