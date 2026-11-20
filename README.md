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
| **Lite** | [Masz już MKVToolNix](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.5/Wolf-Subs-Menager-1.5.5-Lite.exe) | Program szuka go w typowych lokalizacjach. Gdy nie znajdzie, wskażesz folder ręcznie. |
| **Full** | [Nie chcesz osobno instalować MKVToolNix](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.5/Wolf-Subs-Menager-1.5.5-Full.exe) | EXE zawiera potrzebne narzędzia. Przy pierwszym uruchomieniu przygotuje je w wybranym lub domyślnym folderze; kolejne starty wykorzystają zachowane pliki. |
| **Instrukcja PDF** | [Pobierz PDF — polski](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.5/Wolf-Subs-Menager-Guide-PL.pdf) · [Pobierz PDF — angielski](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.5/Wolf-Subs-Menager-Guide-EN.pdf) | Instrukcja krok po kroku z obrazkami, wspólna dla Lite i Full. |


Oba warianty zawierają te same funkcje aplikacji, języki i instrukcje.
Nie wymagają instalatora ani instalacji Pythona. Przy pierwszym starcie zapisują
potrzebne pliki w osobnym folderze. Kolejne starty używają tych samych plików;
brakujące lub uszkodzone składniki są odtwarzane z EXE.
Przygotowanie składników nie jest instalowaniem graficznej aplikacji MKVToolNix.
Full nie pobiera składników z Internetu.

Lite 1.5.5 ma **60,26 MB** do pobrania. Jego przygotowane pliki zajmują dodatkowo
około **59,79 MB**; pobrany EXE pozostaje na dysku. Full ma **129,54 MB** do pobrania,
a jego przygotowane pliki zajmują dodatkowo około **128,98 MB**.

Full korzysta z narzędzi MKVToolNix 103.0 w wydaniu MSYS2 UCRT64. [Odpowiadające źródła,
receptury, patche i informacje o budowaniu](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.0/Wolf-Subs-Menager-1.5.0-Full-Third-Party-Sources.zip) są osobną paczką dla osób zainteresowanych kodem tych składników.
Do zwykłej pracy wystarczy EXE. [Instrukcja użycia zmodyfikowanej biblioteki](LIBRARY-REPLACEMENT.txt).

## Poprawki 1.5.5

- **Każdy rzeczywisty tag ASS w zwykłym Dialogue poza wyjątkami oznacza TS.** Wyjątki to wyłącznie `\an1`-`\an9`, `\b0`/`\b1` i `\i0`/`\i1`. Tekstowe łamanie `\N` samo nie daje TS.
- Ruch, clip/iclip, kolor, font, rozmiar, obrys, cień, transformacje, zanikanie i pozostałe tagi spoza wyjątków wystarczą bez drugiego efektu. Także u/s/r i b400 dają TS. Default ani nazwy Q nie blokują analizy.
- Ręczne wybory, OP/END, karaoke i rozpoznane struktury pozostają chronione. Oryginał i tłumaczenie, dzielone linie, całe efekty/drzewka i wewnętrzna kolejność pozostają razem; dodatkowe niezależne PL nie jest wciągane do cudzej pary. Sama segregacja nie przepisuje tekstu, tagów ani warstw.
- **Starsze zapisane kategorie pozostają zachowane z ostrzeżeniem.** Dawny format nie rozróżniał ręcznej decyzji od automatu. Aby świadomie przeliczyć wybrane linie/blok lub styl nową regułą, wybierz **Automatycznie**. Nie wykonujemy cichej migracji dawnych DIALOG. Nowy zapis rozróżnia automat i ręczny wybór; ręczne decyzje pozostają po ponownym otwarciu.
- Naprawiono reset źródła efektu oraz oddzielenie oryginału Dialogue TL od drzewka TS. Reset obejmuje całą rozpoznaną jednostkę i od razu pokazuje przeliczony wynik. Instrukcje PL/EN opisują nową regułę i Automatycznie.
- Kontrola: 279 testów zaliczonych, 2 pominięte przez ograniczenia Windows; 18 niezależnych przypadków i 13 dostępnych rzeczywistych ASS. To testy integralności i działania, bez wizualnej kontroli każdej sceny w Kainote. Pracuj na kopii i sprawdź wynik z obrazem.

## Poprawki 1.5.4

- **Sam aktywny tag ASS `\pos(x,y)` wystarcza do TS.** Także `{\pos(100,200)}{\an7}`. Nie wymagamy wzorca planszy, fontu ani dodatkowych wierszy; nazwy Q1/Q100 nie decydują.
- Pierwszeństwo mają ręczne korekty oraz rozpoznane OP/END i całe powiązane bloki. Samo i/b/u/s/an8 bez pos nie zmienia dialogu w TS. Sama reguła pos nie przepisuje tekstu, tagów, stylów ani warstw. Tłumaczenie rozbite na części pozostaje całością, także przy różnych stylach i przerwach.
- Starsze zapisane DIALOG z pos jest ponownie oceniane. Format reguły 0/1 nie rozróżniał ręcznych decyzji od automatu, więc dawne świadome wyjątki trzeba sprawdzić; nowe ręczne korekty pozostają po zapisie i ponownym otwarciu.
- Kopie aktualizatora i pliki przygotowania trafiają do osobnego, nieeksponowanego folderu na tym samym woluminie. Po zakończeniu pozostaje ten sam główny EXE pod tą samą nazwą, z ustawieniami i składnikami.
- Przy przejściu ze starego 1.5.3 jego stary pomocnik może chwilowo utworzyć kopię obok EXE; nowa wersja archiwizuje wyłącznie potwierdzone pliki własnej sesji. Wymaga to uruchomienia nowego kodu — awaria przed jego startem pozostaje obsługiwana przez stary pomocnik. Nie usuwa się cudzych plików ani dawnych kopii znalezionych po nazwie.
- Zachowane: PL bez automatycznego TL, pary EN/PL, fonty, rozdziały XML, Lite/Full, cztery języki i instrukcje PL/EN.

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

[Instrukcja po polsku (PDF)](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.5/Wolf-Subs-Menager-Guide-PL.pdf) · [Instrukcja po angielsku (PDF)](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.5/Wolf-Subs-Menager-Guide-EN.pdf)

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
| **Lite** | [You already have MKVToolNix](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.5/Wolf-Subs-Menager-1.5.5-Lite.exe) | Searches common installation locations; manual folder selection remains available. |
| **Full** | [You do not want to install MKVToolNix separately](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.5/Wolf-Subs-Menager-1.5.5-Full.exe) | Contains the required tools. On first launch it prepares components in a selected or default folder; later launches reuse those files. |
| **PDF guide** | [Download Polish PDF](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.5/Wolf-Subs-Menager-Guide-PL.pdf) · [Download English PDF](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.5/Wolf-Subs-Menager-Guide-EN.pdf) | Illustrated step-by-step guide for both Lite and Full. |


Both editions contain the same application features, languages and guides.
No installer or Python installation is required. The first launch prepares
support files in a separate folder. Later launches reuse them; missing or
damaged components can be restored from the EXE. Full does not download tools.

Lite 1.5.5 is a **60.26 MB** download. Prepared files use about **59.79 MB** of
additional disk space; the downloaded EXE also remains on disk. Full is a
**129.54 MB** download and uses about **128.98 MB** for prepared files.

Full uses MKVToolNix 103.0 from MSYS2 UCRT64. Its [corresponding sources, recipes,
patches and build metadata](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.0/Wolf-Subs-Menager-1.5.0-Full-Third-Party-Sources.zip) are a separate package for developers.
For normal use download the EXE. [Using a compatible modified library](LIBRARY-REPLACEMENT.txt).

### Fixes in 1.5.5

- **Any real ASS tag in ordinary Dialogue outside the exceptions means TS.** The only exceptions are `\an1`-`\an9`, `\b0`/`\b1` and `\i0`/`\i1`. A `\N` text line break alone does not mean TS.
- Movement, clip/iclip, colour, font, size, border, shadow, transforms, fading and other non-exempt tags need no second effect. This includes u/s/r and b400. Default and Q style names do not block analysis.
- Manual choices, OP/END, karaoke and recognised structures remain protected. Originals and translations, split lines, complete effects/trees and internal order stay together; independent additional Polish lines are not absorbed into another pair. Classification itself does not rewrite text, tags or layers.
- **Older saved categories are preserved with a warning.** The old format did not distinguish manual choices from automatic results. Choose **Automatic** for selected lines/a block or a style to deliberately reanalyse them with the new rule. There is no silent migration of older DIALOG. New output distinguishes automatic results from manual choices, which survive reopening.
- Fixed effect-source reset and detachment of a Dialogue TL original from its TS tree. Reset covers the complete recognised unit and immediately displays the recalculated result. PL/EN guides explain the new rule and Automatic.
- Validation: 279 tests passed, 2 Windows-environment skips; 18 independent cases and 13 available real ASS samples. These are integrity and functionality checks, not visual verification of every Kainote scene. Work on a copy and check the rendered result.

### Fixes in 1.5.4

- **An active ASS `\pos(x,y)` tag alone is sufficient for TS**, including `{\pos(100,200)}{\an7}`. No screen-card pattern, font or multiple rows are required; Q1/Q100 names do not decide.
- Manual choices, recognised OP/END and complete related blocks retain priority. Formatting i/b/u/s/an8 without pos does not turn dialogue into TS. The pos rule does not rewrite text, tags, styles or layers. Split translations stay together, including different styles and gaps between parts.
- Older saved DIALOG with pos is re-evaluated. Rule format 0/1 did not distinguish manual choices from automatic results, so previous deliberate exceptions need review; new manual choices survive saving and reopening.
- Update recovery and preparation files use a separate, non-exposed folder on the same volume. The same main EXE path and filename, settings and component folder are retained.
- On the first transition from 1.5.3 its old helper may briefly create a sibling copy; the new version archives only confirmed files belonging to that update session. This requires the new code to start; a crash before that point still uses the old helper's recovery behaviour. Foreign files and unrelated older backups are not removed.
- Preserved: Polish without automatic TL, EN/PL pairs, fonts, chapter XML, Lite/Full, four UI languages and PL/EN guides.

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

[Polish guide (PDF)](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.5/Wolf-Subs-Menager-Guide-PL.pdf) · [English guide (PDF)](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.5/Wolf-Subs-Menager-Guide-EN.pdf)

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
