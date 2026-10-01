# 🍻 Kumple: Łap co Twoje

Prosta gra przeglądarkowa o kumplach. Wybierasz postać, łapiesz rzeczy, które ją cieszą, i unikasz tych, które jej szkodzą. Masz 3 życia i 45 sekund, a z każdą sekundą robi się szybciej.

Cała gra to jeden plik `index.html`. Nie trzeba niczego instalować ani budować.

## Jak zagrać

- **Na komputerze:** otwórz `index.html` w przeglądarce.
- **Na telefonie:** wrzuć grę na hosting, np. GitHub Pages (Settings → Pages → gałąź `main`, folder `/ (root)`), i wyślij link na grupę.

**Sterowanie:** strzałki, A/D, myszka albo przeciąganie palcem po ekranie.

## Postacie

| Kumpel | Kim jest | Łapie ✅ | Unika ❌ |
|---|---|---|---|
| 👷 **SW** | Strabag ma we krwi, fanatyk Austrii | kask ze Strabagu, 🇦🇹, Alpy, precel | budowa w plecy, Niemcy zamiast Austrii, urlop |
| 🏗️ **Piotrek** | Haruje w Austrii, dom stawia w Jabłonce | cegły, wypłata w ojro, więźba | faktury, deszcz w Jabłonce, fachowiec, który nie dojechał |
| 🧐 **Marcin** | Kontroler jakości kiełbas w Kabanosie | kabanosy, boczek | sanepid, brokuł w kiełbasie, skarpeta w farszu |
| 😤 **Paweł** | Zawsze gotów na kłótnię z Mateuszem | argumenty, liczby, schabowy | tofu, ścieżki rowerowe, krzyczący Mateusz |
| ✊ **Mateusz** | Lewak pełną gębą | rower, tofu, mleko sojowe, protesty | SUV, argumenty Pawła, schabowy |
| 🪓 **Tomek** | Za dnia drwal, nocą szef fabryki na Słowacji | drewno, a w nocy linia produkcyjna i kontrakty | niedźwiedź, osy, a w nocy awarie i drzemka na zmianie |
| 👨‍💻 **Dominik** | Programista z Krakowa, twórca gry | kawa, zielone testy, Smok Wawelski, obwarzanek | błąd na produkcji, smog, zebranie, które mogło być mailem |

U Tomka w połowie gry zapada noc i zaczyna się nocna zmiana na Słowacji. Wtedy zmieniają się też przedmioty, które spadają.

## Mechaniki

### 🎁 Boosty
Świecące na złoto przedmioty pojawiają się rzadko i są niespodzianką, bo nie widać ich w menu. Każdy kumpel ma dwa swoje.

| Kumpel | Boosty |
|---|---|
| Marcin | 💰 Premia od Kojsa (x2 punkty) · 🍺 Piwko z braćmi (+1 życie) |
| SW | 🏆 Awans w Strabagu (x2) · 🎿 Weekend w Alpach (+1 życie) |
| Piotrek | 🏦 Kredyt przyznany (+100 pkt) · 👷 Fachowiec przyszedł na czas (szerszy chwyt) |
| Paweł | 📺 Zaproszenie do telewizji (x2) · 🤝 Mateusz przyznał rację (tarcza) |
| Mateusz | 🗳️ Wygrane wybory (x2) · 🤝 Paweł przyznał rację (tarcza) |
| Tomek | ☕ Podwójne espresso (spowolnienie) · 😴 Drzemka 15 minut (+1 życie) |
| Dominik | 💸 Podwyżka (x2) · 🤖 Kod pisze się sam (spowolnienie) |

- **x2 punkty, spowolnienie i szerszy chwyt** działają przez 7 sekund.
- **Tarcza** chroni przed jednym złym trafieniem.
- Można mieć **najwyżej 5 żyć**.

### 🔥 Kombo
Każde 5 dobrych rzeczy złapanych pod rząd podnosi mnożnik punktów o 1, maksymalnie do x4. Przy kolejnych progach pojawiają się okrzyki, np. „Kojs patrzy z podziwem!” albo „Mateusz i Paweł się zgadzają!”. Złe trafienie zeruje serię.

### ✈️ Wizyty kumpli
Co kilkanaście sekund przez planszę przelatuje inny kumpel i coś zrzuca.

**📚 Wykład Mateusza:** pierwszym gościem w każdej grze (u każdego oprócz samego Mateusza) jest Mateusz, który tłumaczy zawiłości Olgi Tokarczuk. Zrzuca książki, a każda złapana to −10 pkt. Nie zabiera życia ani nie przerywa kombo. Kto wysłucha choć jednego wykładu, na koniec dostaje tytuł honorowy **Lewak Gry**.

Pozostali goście:
- **pomaga:** SW rozdaje kaski, Marcin przemyca kabanosy, Dominik stawia kawę;
- **szkodzi:** Piotrek rzuca cegłami, Tomek zrzuca kłody;
- **rywale:** u Mateusza Paweł zasypuje go argumentami;
- **bracia** (Marcin, Dominik i Paweł) zawsze sobie pomagają.

### 🏆 Tytuły, wyniki i chwalenie się
- Na koniec gry kumpel dostaje tytuł zależny od wyniku, od „Stażysty od parówek” do „Kiełbasianego Boga”.
- Wynik zapisujesz pod swoim imieniem w **tabeli top 10**. Jest zapisywana w przeglądarce, więc każdy widzi tylko swoje wyniki na swoim urządzeniu.
- Przycisk **📣 Pochwal się** otwiera na telefonie systemowe udostępnianie, a na komputerze kopiuje wynik do schowka.

## Technicznie

- Czysty HTML, CSS i JavaScript na `<canvas>`, bez bibliotek i bez budowania.
- Dźwięki są generowane w przeglądarce (Web Audio API), bez plików audio. Przycisk 🔊/🔇 pozwala je wyciszyć.
- Układ dopasowuje się do telefonów. Sprawdzony w Chrome na rozmiarach ekranów m.in. iPhone SE, Redmi i Xiaomi, w pionie i w poziomie.
- Tabela wyników i ustawienia są zapisywane w `localStorage`.

### Jak dodać kumpla
W `index.html` dopisz obiekt do tablicy `CHARS` (pola: `id`, `name`, `face`, `desc`, `good`, `bad`, `boosts`, `quips`, `titles`). Potem dodaj mu tekst porażki w `deathLines` i wizytę w `VISITS`.
