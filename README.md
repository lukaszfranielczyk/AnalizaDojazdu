# Analiza Czasu Przejazdu: Tarnowskie Góry → Katowice

## Problem
Głównym powodem zainteresowania tą trasą jest to że mieszkam w Tarnowskich Górach, a studiuję w Katowicach. 
Przez pierwszy rok studiów zauważyłem że do Katowic i z powrotem można wyodrębnić pięć tras, które w zależności od pory dnia, znacznie różniły się czasem przejazdu.
Moim celem w tej analizie było określenie tego jak mniej więcej zmieniają się te czasy przejazdu, od czego zależą i kiedy najlepiej zaplanować dojazd i powrót z Katowic.

## Dane
Skrypt zbierający dane został napisany w języku Python - dzielił się on na dwa główne moduły:
- zbieranie czasu przejazdu z Google Maps API
- zbieranie informacji o pogodzie z OpenWeather API
Skrypt działał na mikrokomputerze Raspberry PI przez cały lipiec 2025 roku, zbierając dane co 5 minut, co dało mi ponad 44,5 tysiąca rekordów. 

## Metody
Na początku musiałem sprawdzić co tak właściwie udało mi się zebrać. 
Zaimportowałem wszystkie pliki do Pandas i sprawdziłem czy nie niespodziewanych wartości oraz czy dane są kompletne. 
Następnie przyszła pora na czyszczenie. 
Przekonwertowałem typy danych w miejscach które tego wymagały, połączyłem tabele poprzez wspólny klucz Measurement_Id oraz zapisałem do nowego, czystego pliku. 
Następnie przyszła pora na analizę. 
Oparłem ją na pięciu pytaniach badawczych, do każdego formułując hipotezę którą następnie weryfikowałem.
Jedną z nich było "kierunek A (do Katowic) jest wolniejszy rano, kierunek B (do Tarnowskich Gór) wolniejszy po południu", co udało się potwierdzić w trakcie analizy.

## Wyniki
Przede wszystkim, ze wszystkich pięciu tras które dobrałem do analizy, trasy przez Siemianowice Śląskie oraz Pyrzowice konsekwentnie wykazywały najdłuższe czasy przejazdu, niezależnie od pory dnia ani dnia tygodnia.
Najgorszymi możliwymi godzinami na wyjazd do oraz powrót z Katowic okazały się godziny 15:00 oraz 16:00, wykazując największe opóźnienia. 
Jak się także okazało, trasa z Katowic do Tarnowskich Gór w ciągu dnia jest widocznie szybsza niż ta w drugim kierunku, wykazując dłuższy czas przejazdu jedynie w godzinach szczytu, od 15:00 do 16:00.
Weekendy wykazują znacznie niższy średni czas przejazdu niż dni robocze, zachowując przy tym bardzo niskie odchylenia od średniej. 

## Rekomendacje
Jeśli zależy nam na zminimalizowaniu czasu spędzonego na dojeździe, kluczowym będzie ominięcie godzin 6:00 - 9:00, oraz 15:00 - 16:00. W kierunku Katowic prawie zawsze najlepszym wyborem będzie trasa przez Piekary Śląskie, wykazująca najmniejszy średni czas przejazdu. W kierunku Tarnowskich Gór warto rozważyć dwie trasy: Przez Bytom (przez większość dnia) oraz przez Gliwice (to trasa prowadząca przez autostradę, często szybsza w godzinach szczytu).

## Czego się nauczyłem
Wykorzystanie samodzielnie zebranych danych oraz takich z którymi mam realną styczność na co dzień daje ciekawą możliwość "zajrzenia" w to jakie procesy i zależności w nich występują.
Narzędzia które wykorzystałem - python, pandas, seaborn - pozwoliły mi na szybką i szczegółową analizę tego zbioru. 
W przypadku chęci rozwoju tego projektu, myślę że warto byłoby rozszerzyć próbę badawczą o kolejne miesiące, zwłaszcza te poza sezonem wakacyjnym. 