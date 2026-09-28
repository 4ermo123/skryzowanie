# Projekt: Inteligentne Skrzyżowanie w Tinkercad (Arduino Uno)

Projekt przedstawia prosty i czytelny system sterowania 4-kierunkowym skrzyżowaniem przy użyciu mikrokontrolera **Arduino Uno** oraz diod LED (po jednej parze czerwonej i zielonej na każdy kierunek) w środowisku **Tinkercad**.

---

## 🛠️ Spis komponentów

* **1x Arduino Uno R3**
* **4x Dioda LED – kolor czerwony**
* **4x Dioda LED – kolor zielony**
* **8x Rezystor 220 Ω** (po jednym dla każdej diody)
* **Przewody połączeniowe**

---

## 🔌 Schemat podłączeń (Piny Arduino)

Wszystkie katody (krótkie nóżki) diod są połączone do wspólnej masy (**GND**). Długie nóżki (anody) podłączone są przez rezystory 220 Ω do następujących pinów cyfrowych:

* **Kierunek 1:**
* Światło Czerwone $\rightarrow$ **Pin 2** (`RED_1`)
* Światło Zielone $\rightarrow$ **Pin 6** (`GREEN_1`)


* **Kierunek 2:**
* Światło Czerwone $\rightarrow$ **Pin 3** (`RED_2`)
* Światło Zielone $\rightarrow$ **Pin 7** (`GREEN_2`)


* **Kierunek 3:**
* Światło Czerwone $\rightarrow$ **Pin 4** (`RED_3`)
* Światło Zielone $\rightarrow$ **Pin 8** (`GREEN_3`)


* **Kierunek 4:**
* Światło Czerwone $\rightarrow$ **Pin 5** (`RED_4`)
* Światło Zielone $\rightarrow$ **Pin 9** (`GREEN_4`)



---

## ⏱️ Zasada działania i logika czasowa

Program wykonuje cykliczną pętlę zgodnie z następującym algorytmem dla każdego z 4 kierunków po kolei (zgodnie z ruchem wskazówek zegara):

1. **Start układu:** Na samym początku wszystkie światła świecą na czerwono przez **3 sekundy**.
2. **Sekwencja dla każdego kierunku:**
* Czerwone światło danego kierunku gaśnie.
* Następuje **1 sekunda** przerwy (wszystkie inne kierunki nadal świecą na czerwono).
* Zielone światło danego kierunku zapala się na **5 sekund**.
* Zielone gaśnie, a układ wraca do stanu, w którym **wszystkie kierunki świecą na czerwono przez 3 sekundy**.


3. Cykl płynnie powtarza się od nowa dla kolejnych kierunków (1 $\rightarrow$ 2 $\rightarrow$ 3 $\rightarrow$ 4).

---

## 🚀 Jak uruchomić w Tinkercad?

1. Otwórz projekt w [Tinkercad Circuits](https://www.tinkercad.com/circuits?utm_source=gemini).
2. Dodaj na obszar roboczy **Arduino Uno**.
3. Rozmieść 4 diody czerwone i 4 zielone, podłączając je zgodnie z powyższym opisem pinów i pamiętając o rezystorach 220 Ω zabezpieczających diody.
4. Kliknij przycisk **Kod** w prawym górnym rogu, wybierz opcję **Tekst** i wklej przygotowany kod programu.
5. Kliknij **Rozpocznij symulację** (`Start Simulation`), aby zobaczyć, jak skrzyżowanie poprawnie zmienia światła.