---
layout: post
title: "sqrtInvert"
categories: post
published: true
---

<h1>Szybka odwrotność pierwiastka kwadratowego</h1>
 
2 grudnia światło dzienne ujżała gra tytułem <i>Quake III: Arena</i>. Odrazu po wydaniu zawładnęła ona umysłami graczy, wchodząc jednocześnie do kanonu
pozycji obowiązkowych gier komputerowych. Przez wielu uznawana za kamień milowy rozgrywek elektronicznych, utrzymana w mrocznym klimacie, strzelanka, stawiała
głównie na rozgrywkę w trybie multiplayer. Pozbawiony fabuły tryb single player polegał na rozgrywce z botami - przeciwnikami sterowanymi przez komputer.

Co istotne to właśnie w niej pierwszy raz zastosowano algorytm określany mianem Szybkiej odwrotności pierwiastka kwadratowego.
Uzasadnieniem wykorzystania go jest oszczędność sprzętowa. Obliczanie odwrotnych pierwiastków kwadratowych, opierające się na dzieleniu zmiennoprzecinkowym,
kosztuje czas procesora. Odwrotne pierwiastki kwadratowe są używane w grafice gier wideo przy normalizacji wektorów, z których korzysta wiele współczesnych technik programowania gier.
Zoptymalizowanie czasu przeprowadzania tych obliczeń wydaje się mieć kolosalne znaczenie w tak szybkiej oraz graficznej grze.

Poniżej zamieszczam tytułowy algortm zapisany w kodzie C++
![pic1](/assets/sqrtInvrt.jpg)
Jest on oryginalny względem kodu źródłowego gry - wraz z komentarzami włącznie.

Rewolucyjny pod względem dokładności przybliżenia oraz szybkości algorytm liczy takie równanie:
$$ 1/\sqrt{x} $$
W pierwszych dwóch linijkach kodu dostrzegamy inicjalizacje zmiennych typu liczby zmiennoprzecinkowej. Jako daną wejściową otrzymujemy
liczbę zmiennoprzecinkową - zmienna <b>number</b> - którą po podzieleniu przez 2 zachowuje się do ponownego wykorzystania.

<h2>Nie taki diabeł straszny</h2>

Trzecia linia w kodzie prezentuje jawne rzutowanie typów w iście oldschoolowym stylu czerpiącym jeszcze z języka C.
W istocie rzeczy mamy tutaj dwie konwersje zawarte w jednej linicje. Ja - dla uproszczenia  - rozbiłem to sobie w ten sposób:
![pic2](/assets/cast.jpg)
W pierwszej linii tworzę wskaźnik typu long iwsk. Zachodzi pierwsza konwersja na wskaźnik typu long, z referencji zawierającej adres przechowanej wcześniej liczby typu float.
Jest to dopuszczalne, ponieważ nieograniczone jawne rzutowanie typów pozwala konwertować dowolny wskaźnik na dowolny inny typ wskaźnika, niezależnie od typów, na które wskazują.
W drugiej linijce ustawiony już na pobraną, podzieloną, liczbę wskaźnik typu long int konwertuję na typ long. W ten oto sposób udało mi się zmienić typ zmiennej, z liczby zmiennoprzecinkowej na całkowitą, w całkiem przyzwoitym czasie. To wszystko dzięki wskaźnikom.

<h2>WTF?</h2>

Jak głosi znane powszechnie porzekadło - diabeł tkwi w szczegółach. W czwartej linijce przedstawionego wcześniej kodu widzimy ukrytą magie tego algorytmu.
Szybkość algorytmu bierze się z przesunięcia skonwertowanej wcześniej na liczbę całkowitą liczby o jeden bit w prawo, a następnie odjęcia jej od nazywanej magiczną liczbą stałej, tutaj pojawiającej się w zapisie heksadecymalnym.
W powszechnych źródłach nie można doszukać się szczegółowych informacji na temat tego, jak została ona wyznaczona.
Następnie zachodzi spowrotem konwersja, na drodze jawnego rzutowania, do postaci liczby zmiennoprzecinkowej - linia 5. Na koniec wynik otrzymany na drodze wcześniejszych obliczeń
poddany zostaje pierwszej iteracji metody Newtona dla uzyskania zadowalającego przybliżenia. Te z kolei wydaje się być więcej niż zadowalające.
Dla potwierdzenia wyniki które otrzymałem, licząc $$ 1/\sqrt{x}  $$ dla x = 0,15625:
InvSqrt = 2,52549
Kalkulator naukowy CASIO = 2,52982

Źródła:
https://pl.wikipedia.org/wiki/Szybka_odwrotność_pierwiastka_kwadratowego
