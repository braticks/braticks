# Lietuvos oro pavojus (LT72) – Home Assistant

Neoficiali Home Assistant integracija, kuri skaito [LT72](https://lt72.lt/) skelbiamas oro pavojaus būsenas pagal Lietuvos apskritis. Ši šaka skirta atskiros HACS saugyklos paruošimui.

## Funkcijos
- Apskrities pasirinkimas diegiant integraciją per UI.
- Apskrities keitimas vėliau per **Configure**.
- Vienas sensorius „Oro pavojus – <apskritis>“.
- Būsenos: **Raudona**, **Geltona**, **Geltona po raudonos**, **Balta**, **Nepaskelbta**.
- Pranešimo laikas, šaltinis, apskritis ir rekomendacija atributuose.
- Tikrinama kas 60 sekundžių.

## Diegimas
Šioje šakoje yra paruoštas atskiro HACS projekto turinys. Atskiroje saugykloje failai turi būti jos šaknyje.

1. Sukurkite atskirą GitHub saugyklą, pavyzdžiui, `braticks/lt72-air-alert`, ir perkelkite šios šakos failus į naujos saugyklos `main`.
2. HACS → Custom repositories → naujos saugyklos adresas → **Integration** → Download.
3. Perkraukite Home Assistant.
4. Settings → Devices & services → Add integration → **Lietuvos oro pavojus (LT72)**.
5. Pasirinkite apskritį. Norėdami pakeisti: Integrations → Lietuvos oro pavojus → Configure.

Kol nėra atskiros saugyklos, galima kopijuoti `custom_components/lt72_air_alert` rankiniu būdu į Home Assistant `config/custom_components/`.

## Duomenys ir saugumas
**Duomenys:** oficiali [LT72](https://lt72.lt/) svetainė. Integracija skaito viešą tituliniame puslapyje rodomą aktyvių pavojų suvestinę; viešos garantuotos API nenaudoja. Jeigu tinklalapio struktūra pasikeis arba jis bus nepasiekiamas, sensorius taps `unavailable`.

**Nepaskelbta** reiškia, kad tinklalapyje nėra įrašo apie pasirinktą apskritį, o ne tai, kad saugu. **Balta** rodo aiškiai LT72 paskelbtą pavojaus atšaukimą. Kitų sričių perspėjimai neturi būti laikomi pasirinktos apskrities perspėjimais.

Tai nėra oficiali perspėjimo sistema. **Nenaudokite kaip vienintelio pavojaus signalizavimo kanalo.** Vadovaukitės LT-Alert, sirenomis, atsakingų institucijų pranešimais. Pavojaus metu laikykitės [LT72 rekomendacijų](https://lt72.lt/rekomendacijos-oro-pavojaus-atveju/).
