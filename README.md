# Úvod do projektu
Na vašem analytickém oddělení nezávislé společnosti, která se zabývá životní úrovní občanů, jste se dohodli, že se pokusíte odpovědět na pár definovaných výzkumných otázek, které adresují dostupnost základních potravin široké veřejnosti. Kolegové již vydefinovali základní otázky, na které se pokusí odpovědět a poskytnout tuto informaci tiskovému oddělení. Toto oddělení bude výsledky prezentovat na následující konferenci zaměřené na tuto oblast.

Potřebují k tomu od vás připravit robustní datové podklady, ve kterých bude možné vidět porovnání dostupnosti potravin na základě průměrných příjmů za určité časové období.

Jako dodatečný materiál připravte i tabulku s HDP, GINI koeficientem a populací dalších evropských států ve stejném období, jako primární přehled pro ČR.

## Datové sady, které je možné použít pro získání vhodného datového podkladu

## Primární tabulky:
czechia_payroll – Informace o mzdách v různých odvětvích za několikaleté období. Datová sada pochází z Portálu otevřených dat ČR.
czechia_payroll_calculation – Číselník kalkulací v tabulce mezd.
czechia_payroll_industry_branch – Číselník odvětví v tabulce mezd.
czechia_payroll_unit – Číselník jednotek hodnot v tabulce mezd.
czechia_payroll_value_type – Číselník typů hodnot v tabulce mezd.
czechia_price – Informace o cenách vybraných potravin za několikaleté období. Datová sada pochází z Portálu otevřených dat ČR.
czechia_price_category – Číselník kategorií potravin, které se vyskytují v našem přehledu.
Číselníky sdílených informací o ČR:

czechia_region – Číselník krajů České republiky dle normy CZ-NUTS 2.
czechia_district – Číselník okresů České republiky dle normy LAU.

## Dodatečné tabulky:
countries - Všemožné informace o zemích na světě, například hlavní město, měna, národní jídlo nebo průměrná výška populace.
economies - HDP, GINI, daňová zátěž, atd. pro daný stát a rok.

# Výzkumné otázky
## 1. Rostou v průběhu let mzdy ve všech odvětvích, nebo v některých klesají?
--> TODO ještě jednou projít po datech dodělání, dokomentovat.
Vycházíme z dat v tabulce t_petr_musil_project_SQL_primary_final, kde jsou dostupná data za roky 2006 až 2018 - společné roky.
Pokud posuzujeme růst nominální výše mezd/platů mezi roky 2006 a 2018, došlo za celé období k růstu ve všech odvětvích.
Meziroční přírůstky jsou ve většině let ve všech odvětvích kladné, ale zároveň platí, že většina odvětví v daném období
zaznamenalo alespoň jeden meziroční pokles nominální výše mezd/platů, výjimku tvořila Doprava a skladování s jedním meziročním 
přírůstkem rovným nule, dále Ostatní činnosti, Zdravotní a sociální péče a Zpracovatelský průmysl, v nichž meziročně mzdy rostly každý rok.
## 2. Kolik je možné si koupit litrů mléka a kilogramů chleba za první a poslední srovnatelné období v dostupných datech cen a mezd?
--> TODO překontrolovat SQL vs. popis po datech dodělání, dokomentovat.
Na tuto otázku se nedá na základě dostupných dat obecně odpovědět - nelze určit celkovou průměrnou mzdu za všechna odvětví. Data za počet zaměstnanců
jsou dostupná v prvním a posledním sledovaném odbobí jen za vybraná odvětví - v roce 2006 pro devět (navíc různými způsoby výpočtu dle - fyzicky, přepočtením) a v roce 2018 pro deset z 19.
Nelze proto vypočítat celkovou průměrnou mzdu v Česku pomocí váženého průměru. Posuzovat tedy lze pouze vývoj za jednotlivá odvětví.
Protože cena chleba vzrostla mezi lety 2006 a 2018 z 16.12 Kč na 24.24, tedy o 50.37 %, pak odvětví, v nichž docházelo k pomalejšímu
růstu průměrných mezd (např. Administrativní a podpůrné činnosti, Činnosti v oblasti nemovitostí, Ostatní činnosti, Peněžnictví, Těžba) si pracovníci 
mohli pořídit v roce 2018 méně nebo stejně jednotek chleba. Ve zbývajících odvětvích naopak více. Cena mléka pak vzrostla mezi sledovanými lety z 14.44 Kč na 19.82 Kč, což byl růst o 37.26 %.
Proto si jednotek mléka mohli pořídit v roce 2018 více než na začátku sledovaného období pracovníci ze všech odvětví, vyjma Peněžnictví a pojišťovnictví.
## 3. Která kategorie potravin zdražuje nejpomaleji (je u ní nejnižší percentuální meziroční nárůst)?
--> TODO
## 4. Existuje rok, ve kterém byl meziroční nárůst cen potravin výrazně vyšší než růst mezd (větší než 10 %)?
-->  TODO
## 5. Má výška HDP vliv na změny ve mzdách a cenách potravin? Neboli, pokud HDP vzroste výrazněji v jednom roce, projeví se to na cenách potravin či mzdách ve stejném nebo násdujícím roce výraznějším růstem?

# Výstup projektu
Pomozte kolegům s daným úkolem. Výstupem by měly být dvě tabulky v databázi, ze kterých se požadovaná data dají získat. Tabulky 
pojmenujte t_{jmeno}_{prijmeni}_project_SQL_primary_final (pro data mezd a cen potravin za Českou republiku sjednocených na totožné 
porovnatelné období – společné roky) a t_{jmeno}_{prijmeni}_project_SQL_secondary_final (pro dodatečná data o dalších evropských státech).

Dále připravte sadu SQL, které z vámi připravených tabulek získají datový podklad k odpovězení na vytyčené výzkumné otázky. Pozor, 
otázky/hypotézy mohou vaše výstupy podporovat i vyvracet! Záleží na tom, co říkají data.

Na svém GitHub účtu vytvořte repozitář (může být soukromý), kam uložíte všechny informace k projektu – hlavně SQL skript generující 
výslednou tabulku, popis mezivýsledků (průvodní listinu) a informace o výstupních datech (například kde chybí hodnoty apod.).