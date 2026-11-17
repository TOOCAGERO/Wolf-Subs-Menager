# Wolf-Subs Menager

**Polski** | [English](#english)

Narzędzie Windows do wyciągania napisów z filmów MKV oraz porządkowania plików ASS.
Twórcy aplikacji: **Dierde i TOOCAGERO**.

> **Wydanie 1.5.0 Lite i Full jest dostępne.** [Pobierz program i instrukcje PDF](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/tag/v1.5.0).
> **Full** zawiera potrzebne narzędzia — nie wymaga osobnego instalowania MKVToolNix.
> **Lite** jest mniejszy i korzysta z MKVToolNix, który już masz.

## Co robi aplikacja

- Wyszukuje ścieżki napisów w MKV, ułatwia wybór angielskich i wyciąga obsługiwane napisy tekstowe.
- Pozwala dodać gotowe ASS, również zawierające oryginał i tłumaczenie.
- Porządkuje materiał w grupy DIALOG, TS, OP, END i Komentarze.
- Zachowuje rozpoznane powiązania tłumaczeń i kolejność wewnątrz rozpoznanych bloków efektów.
- W wynikowym ASS zapisuje metadane włączające tryb tłumacza i obie kolumny w Kainote.
- Zapisuje wynik osobno. Nie tłumaczy tekstów i nie generuje efektów.

**Przed sortowaniem zrób kopię zapasową.** Najlepiej pracować na kopii materiału.
Po zapisie sprawdź wynik w Kainote i z obrazem, szczególnie przy złożonych efektach.
Ochrona rozpoznanych struktur nie stanowi gwarancji dla każdego niestandardowego pliku.

## Dwa warianty do pobrania

| Wariant | Dla kogo | Obsługa MKVToolNix |
| --- | --- | --- |
| **Lite — dostępny** | Masz już MKVToolNix | Program szuka go w typowych lokalizacjach. Gdy nie znajdzie, wskażesz folder ręcznie. |
| **Full — dostępny** | Nie chcesz osobno instalować MKVToolNix | EXE zawiera potrzebne narzędzia. Przy pierwszym uruchomieniu przygotuje je w wybranym lub domyślnym folderze; kolejne starty wykorzystają zachowane pliki. |

Oba warianty zawierają te same funkcje aplikacji, języki i instrukcje.
Nie wymagają instalatora ani instalacji Pythona. Przy pierwszym starcie zapisują
potrzebne pliki w osobnym folderze. Kolejne starty używają tych samych plików;
brakujące lub uszkodzone składniki są odtwarzane z EXE.
Przygotowanie składników nie jest instalowaniem graficznej aplikacji MKVToolNix.
Full nie pobiera składników z Internetu.

Lite 1.5.0 ma **60,03 MB** do pobrania. Jego przygotowane pliki zajmują dodatkowo
około **59,57 MB**; pobrany EXE pozostaje na dysku. Full ma **129,31 MB** do pobrania,
a jego przygotowane pliki zajmują dodatkowo około **128,75 MB**.

Full korzysta z narzędzi MKVToolNix 103.0 w wydaniu MSYS2 UCRT64. [Odpowiadające źródła,
receptury, patche i informacje o budowaniu](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.0/Wolf-Subs-Menager-1.5.0-Full-Third-Party-Sources.zip) są osobną paczką dla osób zainteresowanych kodem tych składników.
Do zwykłej pracy wystarczy EXE. [Instrukcja użycia zmodyfikowanej biblioteki](LIBRARY-REPLACEMENT.txt).

## Ustawienia i instrukcje

Rozwijane menu Ustawienia otwiera osobne okna: **Instrukcja**, **Aktualizacja**,
**Rozmiar okna**, **Język interfejsu**, dodatkowe preferencje i **O aplikacji**.
Języki interfejsu: polski, angielski, niemiecki i niderlandzki.
Instrukcje PDF są po polsku i angielsku: krótki start, dokładne kroki i obrazy
pokazujące wybór plików, ekstrakcję, sortowanie, podgląd i zapis.
Okna mają większe logo, własny tytuł i dolny przycisk **Zamknij**.

## Aktualizacje bez szukania na stronie

Od wersji 1.5.0 wystarczy otworzyć w programie
**Ustawienia → Aktualizacja → Sprawdź aktualizację**. Gdy będzie nowe wydanie,
przycisk **Pobierz** pozwoli przejść do pobrania właściwego pliku z tego repozytorium.
Nie trzeba będzie za każdym razem samodzielnie zaglądać na GitHuba ani mieć konta.
Pobranie nowej wersji nie oznacza automatycznego uruchomienia ani podmiany programu.

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

> **Version 1.5.0 Lite and Full are available.** [Download the application and PDF guides](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/tag/v1.5.0).
> **Full** includes the tools and requires no separate MKVToolNix installation.
> **Lite** is smaller and uses MKVToolNix you already have.

### What it does

- Finds subtitle tracks in MKV videos and extracts supported text subtitle formats.
- Imports existing ASS files, including original/translation pairs.
- Organises records into DIALOG, TS, OP, END and Comments.
- Preserves recognised translation relationships and internal order of recognised effect blocks.
- Writes ASS metadata enabling Kainote translator mode and both text columns.
- Saves separate output files. It does not translate text or generate effects.

**Back up your files before sorting and work on copies.** Inspect saved results
in Kainote and against the video, especially for complex effects. Protection of
recognised structures is not a guarantee for every custom subtitle format or effect.

### Choose a download

| Edition | Intended use | MKVToolNix |
| --- | --- | --- |
| **Lite — available** | You already have MKVToolNix | Searches common installation locations; manual folder selection remains available. |
| **Full — available** | You do not want to install MKVToolNix separately | Contains the required tools. On first launch it prepares components in a selected or default folder; later launches reuse those files. |

Both editions contain the same application features, languages and guides.
No installer or Python installation is required. The first launch prepares
support files in a separate folder. Later launches reuse them; missing or
damaged components can be restored from the EXE. Full does not download tools.

Lite 1.5.0 is a **60.03 MB** download. Prepared files use about **59.57 MB** of
additional disk space; the downloaded EXE also remains on disk. Full is a
**129.31 MB** download and uses about **128.75 MB** for prepared files.

Full uses MKVToolNix 103.0 from MSYS2 UCRT64. Its [corresponding sources, recipes,
patches and build metadata](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases/download/v1.5.0/Wolf-Subs-Menager-1.5.0-Full-Third-Party-Sources.zip) are a separate package for developers.
For normal use download the EXE. [Using a compatible modified library](LIBRARY-REPLACEMENT.txt).

### Interface, guides and updates

The Settings menu opens separate windows for the guide, updates, window
size, interface language, other preferences and About. Interface languages:
Polish, English, German and Dutch. Illustrated PDF guides: Polish and English.
Helper windows have a larger logo, their own title and a bottom **Close** button.

Starting with version 1.5.0, open
**Settings → Update → Check for updates**. When a newer version is available,
**Download** will lead to the matching release asset. A GitHub account is not
required. Downloading does not automatically execute or replace the application.

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
