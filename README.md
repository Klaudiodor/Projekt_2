# Projekt 2 Informatyka Geodezyjna - wtyczka do programu QGIS

## Wymagania systemowe
- Python (wersja **3.12**)
- Program geodezyjny QGIS (wersja **minimum 3.0.0**)
- System operacyjny **Windows 11**

## Funkcjonalność wtyczki
Wtyczka pythonowa dla programu QGIS pozwala na następujące działania:

1. **Liczenie różnicy wysokości pomiędzy dwoma punktami:**  
Ta funkcjonalność jest dostępna jedynie w przypadku wybrania dokładnie 2 punktów z listy pokazanej przez wtyczkę i zatwierdzeniu wybory przyciskiem **OK**. Program wyciągnie wartość atrybutu *'wysokosc'* lub *'h_plevrf20'* z wybranych dwóch punktów z aktywnej warstwy i obliczy ich różnicę. Co oznacza, że aby wtyczka mogła poprawnie obliczyć różnicę wysokości należy upewnić się sprawdzając tabelę atrybutów aktywnej warstwy czy punkty posiadają atrybut o nazwie **wysokosc** lub **h_plevrf20**. Wyniki obliczeń są podawane w metrach **[m]** z dokładnością do 2 miejsc po przecinku.

2. **Liczenie pola powierzchni pomiędzy 3 lub więcej punktami:**  
Aby obliczyć pole powierzchni należy w programie wybrać minimum 3 punkty z aktywnej warstwy. Na podstawie wyznaczonych punktów program używając metody Gaussa wyznaczy pole powierzchni pomiędzy nimi. Wynik jest domyślnie podawany w metrach kwadratowych **[m2]**, używając listy znajdującej się nad punktami w programie można również wybrać aby wynik został podawy w arach **[a]** bądź też w hektarach **[ha]**. Wyniki te są podawane z dokładnością do 2 miejsc po przecinku.

## Jak użyć wtyczki
Aby wtyczka poprawnie działała należy wykonać następujące czynności:

1. Sklonować repozytorium na maszynę z zainstalowanym programem QGIS
2. Umieścić pliki z sklonowanego repozytorium do folderu z wtyczkami programu QGIS, najprawdopodobniej będzie to *C:\Users\xxx\AppData\Roaming\QGIS\QGIS3\profiles\default\python\plugins* pod postacią nowego folderu, np. *projekt_2*.
3. W programie QGIS należy kliknąć w zakładkę **Wtyczki**/**Zarządzanie Wtyczkami**/**Zainstalowane** i wybrać wtyczkę z nazwą stworzonego folderu gdzie został umieszczony kod sklonowany z repozytorium.
4. Po zainstalowaniu wtyczki należy wczytać plik z współrzędnymi, na których chcemy wykonać operację (należy upewnić się czy punkty w stworzonej warstwie posiadają atrybut **wysokosc** lub **h_plevrf20** - można to sprawdzić klikając prawym przyciskiem myszy na aktywną warstwę i wybierając opcję **Otwórz tabelę atrybutów**).
5. Po wczytaniu danych można uruchomić wtyczkę klikając **Wtyczki**/**Nazwa_wtyczki**
6. Po wyświetleniu się okna wtyczki należy wybrać punkty z listy i zatwierdzić wybór używając przycisku **OK**, lub anulować działanie używając przycisku **Anuluj**.
7. W zależności od ilości wybranych punktów program wykona odpowiednia działania opisane w rozdziale [Funkcjonalność wtyczki](#funkcjonalność-wtyczki), zamknie okno dialogowe programu i wyświetli monit z wynikami, lub też powiadomieniami/błędami.

## Przykładowe pliki
Przykładowe pliki, z których można skorzystać znajdują się w folderze [agencje_zatrudnienia](agencje_zatrudnienia) pod postacią pliku [.shx](agencje_zatrudnienia/agencje_zatrudnienia.shx), którego można nanieść na projekt w QGIS.
