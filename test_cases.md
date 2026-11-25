# Task Manager - Testovací případy

## 1. Účel testování

Cílem testování je ověřit správnou funkčnost programu
Task Manager, včetně jeho reakcí na platné a neplatné vstupy
a hraniční případy.

## 2. Testovací případy - hlavni_menu()

### TC01: POZITIVNÍ - Výběr platné možnosti z hlavního menu

**Popis:** Ověření, že hlavní menu správně reaguje
na výběr platných možností 1 až 4.

**Vstupní podmínky:** Program je spuštěný,
zobrazuje hlavní menu a seznam úkolů je prázdný.

**Kroky testu:**

1. Zadejte možnost 1.
2. Zadejte název úkolu "Nakoupit".
3. Zadejte popis úkolu "Ovoce a zeleninu".
4. Po návratu do hlavního menu zadejte možnost 2.
5. Po návratu do hlavního menu zadejte možnost 3.
6. Zadejte číslo úkolu 1.
7. Po návratu do hlavního menu zadejte možnost 4.

**Očekávaný výsledek:**

- Volba 1 spustí funkci pridat_ukol().
- Volba 2 spustí funkci zobrazit_ukoly().
- Volba 3 spustí funkci odstranit_ukol().
- Po dokončení každé z těchto funkcí se zobrazí
  hlavní menu.
- Volba 4 korektně ukončí program.

**Skutečný výsledek:** Program správně spustil jednotlivé
funkce při výběru možností 1, 2 a 3. Po jejich dokončení
se vrátil do hlavního menu. Po zadání možnosti 4
byl program ukončen.

**Stav:** PASS

**Poznámky:** Test ověřuje správnou navigaci
v hlavním menu a propojení jednotlivých funkcí.


### TC02: Negativní - Zadání neplatné možnosti v hlavním menu


**Popis:** Ověření, že program správně reaguje
na zadání neplatných možností v hlavním menu.

**Vstupní podmínky:** Program je spuštěný
a zobrazuje hlavní menu.

**Kroky testu:**

1. Zadejte text "abc" a potvrďte klávesou Enter.
2. Zkontrolujte reakci programu.
3. Zadejte desetinné číslo "2.5".
4. Zkontrolujte reakci programu.
5. Zadejte pouze mezery a stiskněte Enter.
6. Zkontrolujte reakci programu.


**Očekávaný výsledek:**

- Program při každém neplatném vstupu zobrazí
  hlášku "Neplatná volba. Zkuste to znovu."
- Program nespustí žádnou z nabízených funkcí.
- Program se neukončí.
- Program znovu zobrazí hlavní menu a umožní
  zadání další možnosti.

**Skutečný výsledek:** Program správně nespustil jednotlivé
funkce při zadání hodnot: abc, 2.5 a prázdných mezer. Program zobrazuje hlášku "Neplatná volba. Zkuste to znovu." Umožňuje zadání další možnosti. 

**Stav:** PASS

**Poznámky:** Test ověřuje odolnost programu
vůči neplatným uživatelským vstupům.

### TC03: Hraniční - Výběr hraničních hodnot v hlavním menu

**Popis:** Ověření správného chování programu při zadání hodnot těsně mimo hranice povolených možností

**Vstupní podmínky:** Program je spuštěný, zobrazuje
hlavní menu a seznam úkolů je prázdný.

**Kroky testu:**

1. Zadejte hodnotu 0 a zkontrolujte reakci programu.
2. Zadejte hodnotu 5 a zkontrolujte reakci programu.


**Očekávaný výsledek:**

- Při zadání hodnoty 0 program zobrazí hlášku
  "Neplatná volba. Zkuste to znovu."
- Při zadání hodnoty 5 program zobrazí stejnou hlášku.


**Skutečný výsledek:** Program při zadání hodnot 0 a 5 zobrazil hlášku: "Neplatná volba. Zkuste to znovu."

**Stav:** PASS

**Poznámky:** Test využívá metodu analýzy hraničních
hodnot.

## 3. Testovací případy - pridat_ukol()

### TC04: Pozitivní - Přidání úkolu s platnými údaji

**Popis:** Ověření, že program umožňuje přidat nový úkol
s platným názvem a popisem do seznamu úkolů.

**Vstupní podmínky:** Program je spuštěný, zobrazuje
hlavní menu a seznam obsahuje jeden úkol:
"Nakoupit - Ovoce a zeleninu".

**Kroky testu:**

1. Zadejte možnost 1 v hlavním menu.
2. Zadejte název úkolu "Uklidit".
3. Zadejte popis úkolu "Vytřít podlahu".
4. Zkontrolujte reakci programu.
5. V hlavním menu zadejte možnost 2.
6. Zkontrolujte obsah seznamu úkolů.

**Očekávaný výsledek:**

- Program umožní zadání názvu a popisu úkolu.
- Program zobrazí hlášku "Úkol 'Uklidit' byl přidán."
- Program se vrátí do hlavního menu.
- Seznam obsahuje dva úkoly:
  1. Nakoupit - Ovoce a zeleninu
  2. Uklidit - Vytřít podlahu
- Původní úkol zůstane nezměněný.

**Skutečný výsledek:** rogram zobrazil potvrzení
o přidání úkolu a vrátil se do hlavního menu.
V seznamu se objevil nový úkol "Uklidit - Vytřít podlahu".
Původní úkol zůstal nezměněný.

**Stav:** PASS

**Poznámky:** Test ověřuje správné ukládání nových
úkolů a zachování již uložených úkolů.

### TC05: Negativní - Přidání úkolu s neplatnými údaji

**Popis:** Ověření, že program neumožní přidat úkol
s prázdným názvem nebo popisem.

**Vstupní podmínky:** Program je spuštěný, zobrazuje
hlavní menu a seznam úkolů je prázdný.

**Kroky testu:**

1. Zadejte možnost 1 v hlavním menu.
2. Ponechte název prázdný a zadejte popis
   "Vytřít podlahu".
3. Zkontrolujte reakci programu.
4. Zadejte název "Uklidit" a ponechte popis prázdný.
5. Zkontrolujte reakci programu.
6. Ponechte název i popis prázdný.
7. Zkontrolujte reakci programu.
8. Zadejte platný název "Uklidit".
9. Zadejte platný popis "Vytřít podlahu".
10. Po návratu do hlavního menu zadejte možnost 2.
11. Zkontrolujte obsah seznamu úkolů.

**Očekávaný výsledek:**

- Program při každém neplatném zadání zobrazí
  hlášku "Název ani popis nesmí být prázdný."
- Program neuloží žádný neplatný úkol.
- Program umožní opakované zadání názvu a popisu.
- Seznam obsahuje pouze jeden úkol:
  "Uklidit - Vytřít podlahu".

**Skutečný výsledek:** Program nepřidal úkol pokud ybl zadán pouze název, pouze popis, nebo nebyl zadán ani název ani popis. Program zobrazuje hlášku "Název ani popis nesmí být prázdný." Umožňuje zadání další možnosti. Seznam obsahuje pouze jeden úkol. 

**Stav:** PASS

**Poznámky:** Test ověřuje validaci vstupních údajů
a ochranu před uložením neúplných úkolů.

### TC06: Hraniční - Přidání prvního úkolu s minimální délkou údajů

**Popis:** Ověření, že program umožní přidat první úkol
do prázdného seznamu, pokud název a popis obsahují
pouze jeden znak.

**Vstupní podmínky:** Program je spuštěný, zobrazuje
hlavní menu a seznam úkolů je prázdný.

**Kroky testu:**

1. Zadejte možnost 1 v hlavním menu.
2. Zadejte název úkolu "A".
3. Zadejte popis úkolu "B".
4. Zkontrolujte reakci programu.
5. V hlavním menu zadejte možnost 2.
6. Zkontrolujte obsah seznamu úkolů.

**Očekávaný výsledek:**

- Program přijme název a popis o délce jednoho znaku.
- Program zobrazí hlášku "Úkol 'A' byl přidán."
- Program se vrátí do hlavního menu.
- Seznam obsahuje právě jeden úkol:
  1. A - B

**Skutečný výsledek:** V seznamu úkolů s eobjevil úkol s názvem A a popisem B. 

**Stav:** PASS

**Poznámky:** Test ověřuje minimální povolenou délku
vstupních údajů a přidání prvního úkolu do prázdného
seznamu.

## 4. Testovací případy - zobrazit_ukoly()

### TC07: Pozitivní - Zobrazení všech uložených úkolů

**Popis:** Ověření, že program správně zobrazí všechny
uložené úkoly včetně jejich číslování, názvů a popisů.

**Vstupní podmínky:** Program je spuštěný, zobrazuje
hlavní menu a seznam obsahuje tři úkoly:

1. Nakoupit - Ovoce a zeleninu
2. Uklidit - Vytřít podlahu
3. Uvařit - Oběd a večeři

**Kroky testu:**

1. Zadejte možnost 2 v hlavním menu.
2. Zkontrolujte počet zobrazených úkolů.
3. Zkontrolujte číslování a pořadí úkolů.
4. Zkontrolujte názvy a popisy jednotlivých úkolů.
5. Ověřte návrat do hlavního menu.
6. Znovu zadejte možnost 2 a ověřte, že se seznam
   nezměnil.

**Očekávaný výsledek:**

- Program zobrazí nadpis "Seznam úkolů:".
- Program zobrazí všechny tři uložené úkoly.
- Číslování začíná číslem 1 a pokračuje postupně.
- Názvy, popisy a pořadí odpovídají uloženým údajům.
- Program se vrátí do hlavního menu.
- Opakované zobrazení seznamu nezmění jeho obsah.

**Skutečný výsledek:** Program zobrazil všechny tři úkoly
ve správném pořadí, včetně jejich názvů, popisů a číslování.
Program se vrátil do hlavního menu. Při opakovaném
zobrazení seznamu se jeho obsah nezměnil.


**Stav:** PASS

**Poznámky:** Test ověřuje správné zobrazení všech
uložených údajů, jejich číslování a pořadí.

### TC08: Negativní - Zobrazení prázdného seznamu úkolů

**Popis:** Ověření, že program správně reaguje
na požadavek zobrazení úkolů, pokud je seznam prázdný.

**Vstupní podmínky:** Program je spuštěný, zobrazuje
hlavní menu a seznam úkolů je prázdný.

**Kroky testu:**

1. Zadejte možnost 2 v hlavním menu.
2. Zkontrolujte reakci programu.
3. Ověřte návrat do hlavního menu.
4. Opakovaně zadejte možnost 2.
5. Zkontrolujte reakci programu.

**Očekávaný výsledek:**

- Program zobrazí hlášku "Seznam úkolů je prázdný."
- Program nezobrazí žádné úkoly.
- Program se vrátí do hlavního menu.
- Při opakovaném zobrazení program reaguje stejně.

**Skutečný výsledek:** Program nezobrazil žádné úkoly
a zobrazil hlášku "Seznam úkolů je prázdný."
Program se vrátil do hlavního menu.
Při opakovaném zobrazení reagoval stejně.

**Stav:** PASS

**Poznámky:** Test ověřuje správné zpracování
prázdného seznamu a stabilitu programu.


## 5. Testovací případy - odstranit_ukol()

### TC09: Pozitivní - Odstranění úkolu ze seznamu

**Popis:** Ověření, že program správně odstraní
vybraný úkol ze seznamu a zachová ostatní úkoly.

**Vstupní podmínky:** Program je spuštěný, zobrazuje
hlavní menu a seznam obsahuje tři úkoly:

1. Nakoupit - Ovoce a zeleninu
2. Uklidit - Vytřít podlahu
3. Uvařit - Oběd a večeři

**Kroky testu:**

1. Zadejte možnost 3 v hlavním menu.
2. Zkontrolujte zobrazení seznamu úkolů.
3. Zadejte číslo úkolu 2.
4. Zkontrolujte reakci programu.
5. Po návratu do hlavního menu zadejte možnost 2.
6. Zkontrolujte obsah a číslování seznamu úkolů.

**Očekávaný výsledek:**

- Program zobrazí seznam úkolů a výzvu k zadání
  čísla úkolu, který má být odstraněn.
- Program odstraní úkol "Uklidit".
- Program zobrazí hlášku "Úkol 'Uklidit' byl odstraněn."
- Program se vrátí do hlavního menu.
- Seznam obsahuje pouze dva úkoly:
  1. Nakoupit - Ovoce a zeleninu
  2. Uvařit - Oběd a večeři
- Ostatní úkoly zůstanou obsahově nezměněné.
- Číslování úkolů je aktualizováno.

**Skutečný výsledek:** Úkol 2 byl odstraněn. Ostatní úkoly zůstaly a byly přečíslovány. 

**Stav:** PASS

**Poznámky:** Test ověřuje správné odstranění
vybraného úkolu, zachování ostatních úkolů
a jejich správné přečíslování.

### TC10: Negativní - Odstranění úkolu při neplatném vstupu

**Popis:** Ověření, že program správně reaguje
na neplatné vstupní údaje při odstraňování úkolů
a na pokus o odstranění úkolu z prázdného seznamu.

**Vstupní podmínky:** Program je spuštěný, zobrazuje
hlavní menu a seznam úkolů je prázdný.

**Kroky testu:**

1. Zadejte možnost 3 v hlavním menu.
2. Zkontrolujte reakci programu.
3. Přidejte do seznamu dva úkoly:
   - Nakoupit - Ovoce a zeleninu
   - Uklidit - Vytřít podlahu
4. Zadejte možnost 3 a následně text "abc".
5. Zkontrolujte reakci programu.
6. Opakujte kroky 4 a 5 postupně pro následující hodnoty:
   - Desetinné číslo 2.5
   - Prázdný vstup
   - Číslo 0
   - Číslo 100
7. V hlavním menu zadejte možnost 2.
8. Zkontrolujte obsah seznamu úkolů.

**Očekávaný výsledek:**

- Při pokusu o odstranění úkolu z prázdného seznamu
  program zobrazí hlášku "Seznam úkolů je prázdný."
- Při zadání textu, desetinného čísla, prázdného
  vstupu program zobrazí hlášku
  "Musíte zadat celé číslo."
- Při zadání čísla mimo povolený rozsah program
  zobrazí hlášku "Neplatné číslo úkolu."
- Po každém neplatném zadání se program vrátí
  do hlavního menu.
- Seznam obsahuje oba původní úkoly.

**Skutečný výsledek:** Program správně reagoval na neplatné
vstupy a zobrazil odpovídající chybové hlášky:
"Seznam úkolů je prázdný.", "Musíte zadat celé číslo."
a "Neplatné číslo úkolu." Program se vždy vrátil
do hlavního menu a oba původní úkoly zůstaly zachovány.

**Stav:** PASS

**Poznámky:** Test ověřuje validaci vstupních údajů,
stabilitu programu a ochranu před neoprávněným
odstraněním úkolu.
