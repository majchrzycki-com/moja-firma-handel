# Wynik kontrolny: agent rozliczenia kampanii

Liczby poniżej policzono niezależnie z plików w katalogu `dane-cwiczeniowe/`. Jeśli agent oddaje inne wartości, procedura nie działa poprawnie w Waszym narzędziu.

## Sprawdź wynik na danych kontrolnych

Liczby policzyliśmy niezależnie z tych samych plików. Kwoty w złotych.

| Kampania | Zamówienia | Zwroty | Przychód netto | Marża po wszystkim | Marża % | ROAS |
|---|---|---|---|---|---|---|
| KMP-01 wyszukiwarka | 140 | 4 | 23 639,34 | 5 095,46 | 22,2% | 3,48 |
| KMP-02 strefa promocji marketplace | 310 | 50 | 79 133,66 | 827,93 | 1,3% | 22,61 |
| KMP-03 media społecznościowe | 60 | 4 | 9 718,78 | −275,68 | −3,0% | 1,87 |
| KMP-04 porównywarka | 95 | 5 | 30 741,50 | 4 504,65 | 15,4% | 7,50 |
| KMP-05 newsletter | 70 | 3 | 8 197,98 | 3 274,39 | 41,9% | 13,66 |
| bez kampanii | 340 | 22 | 72 941,94 | 21 729,16 | 31,8% | — |

| Kampania | Zwroty netto | Koszt towaru po zwrotach | Prowizje | Płatności | Wysyłka | Obsługa zwrotów | Reklama |
|---|---|---|---|---|---|---|---|
| KMP-01 | 686,19 | 9 955,00 | 0,00 | 349,19 | 681,50 | 72,00 | 6 800,00 |
| KMP-02 | 15 999,42 | 43 170,00 | 10 706,31 | 0,00 | 4 030,00 | 900,00 | 3 500,00 |
| KMP-03 | 389,43 | 3 827,00 | 0,00 | 143,53 | 362,50 | 72,00 | 5 200,00 |
| KMP-04 | 1 543,92 | 19 150,00 | 0,00 | 453,93 | 899,00 | 90,00 | 4 100,00 |
| KMP-05 | 384,14 | 3 547,00 | 0,00 | 120,95 | 217,50 | 54,00 | 600,00 |
| bez kampanii | 4 604,10 | 37 370,00 | 5 032,28 | 527,90 | 3 282,50 | 396,00 | 0,00 |

Prawidłowe oznaczenia: KMP-02 „rekord przychodu, słaba marża” (największy przychód i ROAS, a z 79 tysięcy przychodu zostaje 827,93 zł), KMP-03 „na minusie”, KMP-05 „do wzmocnienia”. Przy KMP-02 agent powinien wskazać zwroty (15 999,42 zł) i prowizje (10 706,31 zł) oraz kosiarkę elektryczną 40 cm: 25 z 50 zwrotów tej kampanii i 11 212,50 zł zwróconej wartości.

Jeśli KMP-02 wychodzi z marżą kilku tysięcy złotych, agent prawdopodobnie pominął część zwrotów z maja albo nie połączył ich po numerze zamówienia.

## Krok z rzeczywistością

Pod koniec maja przychodzą jeszcze dwie kosiarki z kampanii marketplace, obie uszkodzone w transporcie i niezdatne do ponownej sprzedaży. Dopisz w `zwroty.xlsx` dwa wiersze (towar nie wraca, więc koszt towaru, który wrócił, wynosi zero):

```text
Z-00150 | 2026-05-22 | marketplace | OGR-KOS-40 | 448.50 | 0 | 18 | uszkodzenie w transporcie
Z-00155 | 2026-05-23 | marketplace | OGR-KOS-40 | 448.50 | 0 | 18 | uszkodzenie w transporcie
```

Załącz poprawiony plik w nowej rozmowie i zadaj to samo pytanie. Dla KMP-02 powinieneś zobaczyć 52 zwroty, zwroty netto 16 896,42 zł, obsługę zwrotów 936,00 zł, niezmieniony koszt towaru po zwrotach 43 170,00 zł i marżę **−105,07 zł (−0,2%)**. ROAS zostaje 22,61, bo panel reklamowy zwrotów nie widzi. Kampania powinna dostać oba oznaczenia: „rekord przychodu, słaba marża” i „na minusie”. Pozostałe wiersze tabeli się nie zmieniają.

Dwie paczki zamieniły rekordową kampanię w stratną. Tego nie pokaże żaden wskaźnik liczony przed zamknięciem okna zwrotów.
