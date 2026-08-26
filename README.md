# Alkatrész importáló

Alkatrészlista egy gyártói oldalról, webshopba tölthető Excel-táblaként — a képekkel együtt.

## ⬇️ Letöltés

### **[Legfrissebb verzió letöltése](https://github.com/D3trah/alkatresz-importalo/releases/latest)**

Töltsd le a `Alkatresz-importalo-Setup-….exe` fájlt, és futtasd. Nem kell hozzá
rendszergazda jelszó, és nem kell hozzá se Python, se Excel, se semmilyen kulcs.

| | |
|---|---|
| **Rendszer** | Windows 10 vagy 11, 64 bites |
| **Letöltés mérete** | kb. 200 MB |
| **Helyigény telepítés után** | kb. 650 MB (ennek a nagy része a beépített böngésző) |
| **Rendszergazda jog** | nem kell — a saját felhasználódhoz telepít |

Frissíteni nem kell: a program magától letölti az új verziót a háttérben, és bezáráskor
telepíti. Ez az **Eszközök → Automatikus frissítés** menüpontban kikapcsolható.

---

## „A Windows megvédte a számítógépét"

Ez meg fog jelenni, és **nem azt jelenti, hogy baj van a fájllal.** A telepítő nincs
digitálisan aláírva — az aláíráshoz évente fizetni kell egy tanúsítványért —, és a Windows
minden aláíratlan, még kevesek által letöltött programnál kiírja ezt.

Így tudod elindítani:

```
   ┌────────────────────────────────────────────┐
   │  A Windows megvédte a számítógépét         │
   │                                            │
   │  A Microsoft Defender SmartScreen          │
   │  megakadályozta egy ismeretlen alkalmazás  │
   │  elindítását…                              │
   │                                            │
   │  ► További információ      ← 1. KATTINTS IDE
   │                                            │
   │                          [ Ne futtassa ]   │
   └────────────────────────────────────────────┘

   majd:

   ┌────────────────────────────────────────────┐
   │  Alkalmazás: Alkatresz-importalo-Setup.exe │
   │  Közzétevő:  Ismeretlen közzétevő          │
   │                                            │
   │           [ Futtatás mindenképp ]  ← 2. EZ
   │                          [ Ne futtassa ]   │
   └────────────────────────────────────────────┘
```

1. Kattints a **További információ** linkre.
2. Kattints a **Futtatás mindenképp** gombra.

Ha a géped **Smart App Control**ja be van kapcsolva (általában csak frissen telepített
Windows 11-en), az akár teljesen meg is tagadhatja a fájlt, „Ismeretlen közzétevő" vagy
„Egy alkalmazásvezérlési szabályzat blokkolta ezt a fájlt" üzenettel. Erre a
„Futtatás mindenképp" nem segít; ilyenkor szólj a fejlesztőnek.

Ellenőrizni is tudod a letöltött fájlt: minden kiadás mellett ott a SHA-256 lenyomata a
[`latest.json`](latest.json)-ban. PowerShellben:

```powershell
Get-FileHash .\Alkatresz-importalo-Setup-0.2.0.exe -Algorithm SHA256
```

---

## Az első indítás

1. Illeszd be egy gép alkatrészlistájának a linkjét.
2. Nézd át a táblázatot — a program megjelöli, amiben nem volt biztos.
3. Mentsd el. Az elkészült fájl a **Dokumentumok\Alkatrészlisták** mappába kerül.

### Amit neked kell elintézned

- **STIHL alkatrészekhez saját SSC (kereskedői) belépés kell.** A program kinyit egy
  böngészőablakot, ahol be tudsz jelentkezni; a jelszavadat sehol nem tárolja el, és a
  belépést nem lehet másik gépről átmásolni. A bejelentkezés néhány óra után lejár, akkor
  a program szól, hogy lépj be újra.
- A **Husqvarna** oldal bejelentkezés nélkül is olvasható, de az **árakat** nem mutatja
  meg névtelen látogatónak — az ároszlop ilyenkor üresen marad.
- Ha a Dokumentumok mappád **OneDrive**-ba van átirányítva, az elkészült táblázatok a
  felhasználói mappádba kerülhetnek a Dokumentumok helyett.

---

## Ez itt csak a letöltés

Ebben a tárolóban nincs forráskód — csak a telepítők és a
[`latest.json`](latest.json), amiből a program megtudja, van-e újabb verzió.
