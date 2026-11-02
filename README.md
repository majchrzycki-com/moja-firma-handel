# moja-firma-handel

**Agent rozliczenia kampanii dla polskiej firmy: handel wielokanałowy.** Liczy marżę każdej kampanii po zwrotach, prowizjach, płatnościach, wysyłce i reklamie, zestawia ją z ROAS z panelu reklamowego i wskazuje, co wzmocnić, co ograniczyć i co sprawdzić.

Pakiet branżowy paczki [moja-firma](https://github.com/majchrzycki-com/moja-firma). Procedura w formacie [Agent Skills](https://agentskills.io/specification) (`SKILL.md`) działa w Anthropic Claude, OpenAI ChatGPT i OpenAI Codex, Microsoft 365 Copilot, Google Gemini oraz OpenClaw.

## Czego agent nie zrobi

Nie wyłączy kampanii i nie przesunie budżetu. Budżetem reklamowym i wyłączaniem kampanii zarządza marketing, a o kampanii bez marży, która ma „budować zasięg”, decyduje zarząd. Agent kładzie na stół rachunek, który pozwala tę decyzję podjąć na liczbach.

> — *Strefa promocji ma ROAS dwadzieścia dwa. Dokładamy budżet?*
> — *A zwroty już doszły?*
> *(Doszło czternaście z pięćdziesięciu.)*

Ślepa automatyzacja szkodzi tu najbardziej przez kalendarz. Zwroty z kwietnia spływają przez cały maj. Gdyby agent rozliczył kampanię marketplace 5 maja, zobaczyłby 14 z 50 zwrotów i marżę 4 055,20 zł (5,3%). Po zamknięciu okna zwrotów zostaje z tego 827,93 zł. Reguła, która 5 maja automatycznie dołożyłaby budżet „rentownej” kampanii, dołożyłaby go do kampanii, która niemal nic nie zarobiła.

Drugi warunek brzegowy dotyczy danych. Jeśli w Waszym eksporcie zamówienia nie mają oznaczenia kampanii, a ten sam produkt nosi inny indeks w każdym kanale, agent policzy marżę starannie, ale na złych przypisaniach. Najpierw jedno oznaczenie kampanii w zamówieniu i jeden indeks produktu, potem agent.

## Wypróbuj na danych ćwiczeniowych

W katalogu [`dane-cwiczeniowe/`](dane-cwiczeniowe/) są fikcyjne dane firmy: `kampanie.csv`, `kampanie.xlsx`, `zamowienia.csv`, `zamowienia.xlsx`, `zwroty.csv`, `zwroty.xlsx`. Pliki XLSX i CSV mają tę samą treść.

1. Zainstaluj procedurę `rozliczenie-kampanii` (niżej).
2. Dodaj pliki ćwiczeniowe do wiedzy agenta albo załącz je do rozmowy.
3. Napisz:

```text
Rozlicz kampanie z kwietnia 2026 według instrukcji projektu. Licz kodem na załączonych plikach.
```

4. Porównaj odpowiedź z [WYNIK-KONTROLNY.md](WYNIK-KONTROLNY.md). Jest tam też „krok z rzeczywistością”: jedna zmiana w danych i wynik, który agent powinien po niej pokazać.

## Instalacja

### Anthropic Claude Code

```text
/plugin marketplace add majchrzycki-com/moja-firma
/plugin install moja-firma-handel@moja-firma
```

### Pozostałe narzędzia

```bash
node scripts/build.mjs
```

Skrypt tworzy `dist/skills/` dla Anthropic Claude, OpenAI Codex, Google Gemini, OpenClaw i Microsoft 365 Copilot Cowork oraz `dist/instrukcje/` z tekstem do wklejenia w agencie Microsoft 365 Copilot Agent Builder albo w projekcie OpenAI ChatGPT. Szczegóły instalacji w każdym narzędziu: [README rdzenia moja-firma](https://github.com/majchrzycki-com/moja-firma#instalacja).

## Ten sam agent krok po kroku

- [Agent rozliczenia kampanii w Anthropic Claude](https://majchrzycki.com/blog/agent-kampanii-w-claude-krok-po-kroku?utm_source=github&utm_medium=referral&utm_campaign=moja-firma&utm_content=rozliczenie-kampanii)
- [Agent rozliczenia kampanii w Microsoft 365 Copilot](https://majchrzycki.com/blog/agent-kampanii-w-microsoft-365-copilot-krok-po-kroku?utm_source=github&utm_medium=referral&utm_campaign=moja-firma&utm_content=rozliczenie-kampanii)
- [Agent rozliczenia kampanii w OpenAI ChatGPT](https://majchrzycki.com/blog/agent-kampanii-w-chatgpt-krok-po-kroku?utm_source=github&utm_medium=referral&utm_campaign=moja-firma&utm_content=rozliczenie-kampanii)
- [Agent rozliczenia kampanii w Google Gemini](https://majchrzycki.com/blog/agent-kampanii-w-gemini-krok-po-kroku?utm_source=github&utm_medium=referral&utm_campaign=moja-firma&utm_content=rozliczenie-kampanii)

Gdzie ten agent mieści się w całej firmie i jakich jeszcze agentów potrzebuje handel wielokanałowy: [darmowy poradnik branżowy](https://majchrzycki.com/transformacja-agenci-ai/handel-wielokanalowy?utm_source=github&utm_medium=referral&utm_campaign=moja-firma&utm_content=rozliczenie-kampanii#pobierz).

## Na własnych danych

Zacznij od procedury `kontrola-danych` z rdzenia moja-firma na eksporcie z Waszego programu. Jeśli kolumny nazywają się inaczej, agent pokaże przypisanie i poprosi o potwierdzenie. Pierwszy tydzień puść agenta obok normalnej pracy jednej osoby i porównuj wyniki.

Procedura nie jest poradą prawną, podatkową ani handlową. Wynik sprawdza osoba, która za niego odpowiada.

## Licencja

[MIT](LICENSE), dla procedur, skryptów i danych ćwiczeniowych.

Autor: [Krzysztof Majchrzycki](https://majchrzycki.com/o-mnie?utm_source=github&utm_medium=referral&utm_campaign=moja-firma&utm_content=rozliczenie-kampanii), wdrożenia AI w polskich firmach.

---

**English:** moja-firma-handel is an industry pack of the open [moja-firma](https://github.com/majchrzycki-com/moja-firma) Agent Skills for Polish SMBs. It contains one `SKILL.md` procedure (in Polish), fictional practice data and expected results. MIT licence.
