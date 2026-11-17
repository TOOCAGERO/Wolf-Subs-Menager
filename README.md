# Wolf-Subs Menager

**Polski** | [English](#english)

Narzędzie Windows do wyciągania napisów z filmów MKV oraz porządkowania plików ASS.
Twórcy aplikacji: **Dierde i TOOCAGERO**.

> **Nowe wydanie jest w przygotowaniu.** Gotowe pliki i instrukcje PDF pojawią się
> w [Releases](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases) po zakończeniu testów.
> Opis poniżej przedstawia docelowy układ tego wydania, a nie listę funkcji już opublikowanej paczki.

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
| **Lite** | Masz już MKVToolNix | Program szuka go w typowych lokalizacjach. Gdy nie znajdzie, wskażesz folder ręcznie. |
| **Full** | Nie chcesz osobno instalować MKVToolNix | EXE zawiera potrzebne narzędzia. Przy pierwszym uruchomieniu przygotuje je w wybranym lub domyślnym folderze; kolejne starty wykorzystają zachowane pliki. |

Oba warianty mają oferować te same funkcje aplikacji, języki i instrukcje.
Przygotowanie składników nie jest instalowaniem graficznej aplikacji MKVToolNix.
Wariant Full nie będzie musiał pobierać składników z Internetu.
Dokładne rozmiary i wyniki pomiarów startu podamy przy gotowym wydaniu.

## Ustawienia i instrukcje

Rozwijane menu Ustawienia ma otwierać osobne okna: **Instrukcja**, **Aktualizacja**,
**Rozmiar okna**, **Język interfejsu**, dodatkowe preferencje i **O aplikacji**.
Planowane języki interfejsu: polski, angielski, niemiecki i niderlandzki.
Instrukcje PDF będą po polsku i angielsku: krótki start, dokładne kroki i obrazy
pokazujące wybór plików, ekstrakcję, sortowanie, podgląd i zapis.

## Aktualizacje bez szukania na stronie

Po wydaniu wersji z tą funkcją wystarczy otworzyć w programie
**Ustawienia → Aktualizacja → Sprawdź aktualizację**. Gdy będzie nowe wydanie,
przycisk **Pobierz** pozwoli przejść do pobrania właściwego pliku z tego repozytorium.
Nie trzeba będzie za każdym razem samodzielnie zaglądać na GitHuba ani mieć konta.
Pobranie nowej wersji nie oznacza automatycznego uruchomienia ani podmiany programu.

## Autorzy i składniki

Autorska część aplikacji: Dierde i TOOCAGERO. Twórcy nie zezwalają na jej
modyfikacje ani zmiany funkcjonalności bez ich zgody. To publiczne repozytorium
z wydaniami i dokumentacją; publiczny dostęp nie oznacza otwartej licencji na własny kod aplikacji.

MKVToolNix i pozostałe zewnętrzne składniki zachowują własne licencje i prawa
ich autorów. Informacje o dołączonych wersjach, teksty licencji i wymagane
materiały źródłowe zostaną udostępnione wraz z odpowiednimi wydaniami.

---

## English

**Wolf-Subs Menager** is a Windows tool for extracting text subtitles from MKV
videos and organising ASS subtitles. Created by **Dierde and TOOCAGERO**.

> **The new release is being prepared.** Downloads and PDF guides will appear
> in [Releases](https://github.com/TOOCAGERO/Wolf-Subs-Menager/releases) after testing.
> The sections below describe the intended release, not an already published package.

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
| **Lite** | You already have MKVToolNix | Searches common installation locations; manual folder selection remains available. |
| **Full** | You do not want to install MKVToolNix separately | Contains the required tools. On first launch it prepares components in a selected or default folder; later launches reuse those files. |

Both editions are intended to offer the same application features, languages
and guides. Full will not need to download its components. Exact download sizes
and startup measurements will be listed with the completed release.

### Interface, guides and updates

The Settings menu will open separate windows for the guide, updates, window
size, interface language, other preferences and About. Interface languages:
Polish, English, German and Dutch. Illustrated PDF guides: Polish and English.

After a version with update support has been released, open
**Settings → Update → Check for updates**. When a newer version is available,
**Download** will lead to the matching release asset. A GitHub account is not
required. Downloading does not automatically execute or replace the application.

### Authors and third-party components

The application's own work is by Dierde and TOOCAGERO. The authors do not permit
modifications to their own part or its functionality without their consent.
This is a public distribution/documentation repository, not an open-source
licence grant for the application's own code.

MKVToolNix and other third-party components retain their own licences and
authors' rights. Version notices, licence texts and required source materials
will accompany the relevant releases.
