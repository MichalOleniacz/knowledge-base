# Topologia przekazywania zetonu

Technologia, w ktorej dostep do medium transmisyjnego jest realizowany poprzez przekazanie zetonu.

<b>Zeton</b> to sekwencja bitow z informacja kontrolna.

W sieci jest tylko jeden zeton i tylko urzadzenie obecnie posiadajace zeton moze nadawac dane.

Host wysylajacy dane usuwa zeton z pierscienia i zaczyna transmisje. Wyslane dane trafiaja do adresata, ktory wysyla komunikat zwrotny o otrzymaniu danych.

Po weryfikacji komputer wysylajacy dane tworzy nowy token i wysyla go do sieci.

Ta moedota stosowana jest w sieciach o Topologi Pierscienia

[[Topologia Pierscienia ( Ring )]]

![[topologia-pierscienia.png]]