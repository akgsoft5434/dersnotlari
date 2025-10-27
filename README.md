# 📘 Dart'ta Listeler (List)

Bu dokümanda **Dart dilinde listeler** konusunu **temelden ileri düzeye kadar** örneklerle öğreneceksin.  
Listeler, birden fazla veriyi tek bir değişkende tutmamızı sağlar. Flutter ve Dart projelerinde çok sık kullanılır.

---

## 🎯 1. Liste (List) Nedir?

**Liste (List)**, birden fazla değeri **tek bir değişkende** saklamamızı sağlar.

Diğer dillerdeki karşılıkları:
- Python → `list`
- Java → `ArrayList`
- C# → `List<T>`
- JavaScript → `Array`


## 📦 2. Liste Oluşturma Yöntemleri

### 🧱 a) Dinamik Liste (Değişken Uzunluklu)
```dart
void main() {
  List isimler = ['Ali', 'Ayşe', 'Mehmet'];
  print(isimler); // [Ali, Ayşe, Mehmet]
}
```
Dart’ta listeler **0. indeksten** başlar.  
Yani `isimler[0] = 'Ali'`


### 🧱 b) Tip Belirterek Liste Oluşturma

Dart'ta listeleri **tip belirterek** tanımlamak, o listeye yalnızca belirli bir türde veri eklenmesini sağlar.  
Bu, hataları önler ve kodun daha güvenli olmasını sağlar.

```dart
void main() {
  List<String> sehirler = ['Ankara', 'İzmir', 'Bursa'];
  List<int> sayilar = [1, 2, 3, 4];
  
  print(sehirler); // [Ankara, İzmir, Bursa]
  print(sayilar);  // [1, 2, 3, 4]
}
```

💡 `List<String>` sadece metin (String) türünde veri kabul eder.
`List<int>` sadece sayısal (int) değerlerle çalışır.

### 🧱 c) Boş Liste Oluşturma
```dart
void main() {
  List<String> bosListe = [];
  bosListe.add('Yeni Eleman');
  print(bosListe); // [Yeni Eleman]
}
```
`add()` metodu, listeye yeni bir eleman ekler.

## 🔒 3. Sabit Uzunluklu Listeler

Sabit uzunluklu listelerde eleman sayısı önceden belirlenir ve değiştirilemez.
```dart
void main() {
  var sabitListe = List<int>.filled(3, 0);
  print(sabitListe); // [0, 0, 0]
  
  sabitListe[1] = 5;
  print(sabitListe); // [0, 5, 0]
  
  // sabitListe.add(8); // ❌ Hata: Sabit uzunluklu listelere eleman eklenemez.
}
```

`dynamic` tipte sabit liste oluşturulabilir. 

dynamic liste her veri tipinden değer alabilir. Bunun için liste tipi boş bırakılır.

```dart
void main() {
  
  List karisikliste = List.filled(3, 0);
  
  print(karisikliste); // [0, 0, 0]
  
  karisikliste[0] = 5;
  karisikliste[1] = 'michael';
  karisikliste[2] = true;
  
  print(karisikliste); // [5, michael, true]
   
}
```

## ⚙️ 4. Liste Elemanlarına Erişim
```dart
void main() {
  List<String> hayvanlar = ['Kedi', 'Köpek', 'Kuş'];
  
  print(hayvanlar[0]); // Kedi
  print(hayvanlar.length); // 3
}
```

`.length` özelliği, listenin eleman sayısını döndürür.
`hayvanlar[2] `→ üçüncü elemana erişir.

## 🧩 5. Listeye Eleman Ekleme
```dart
void main() {
  List<int> sayilar = [1, 2, 3];
  
  sayilar.add(4);            // Tek eleman ekleme
  sayilar.addAll([5, 6, 7]); // Birden fazla eleman ekleme
  
  print(sayilar); // [1, 2, 3, 4, 5, 6, 7]
}
```
`.addAll()` başka bir listeyi eklemek için kullanılır.

## 🗑️ 6. Eleman Silme
```dart
void main() {
  List<String> meyveler = ['Elma', 'Armut', 'Muz', 'Kivi'];
  
  meyveler.remove('Armut');
  print(meyveler); // [Elma, Muz, Kivi]
  
  meyveler.removeAt(1);
  print(meyveler); // [Elma, Kivi]
  
  meyveler.clear();
  print(meyveler); // []
}
```

| Metot              | Açıklama                           |
| ------------------ | ---------------------------------- |
| `.remove(value)`   | Değerin kendisini siler            |
| `.removeAt(index)` | Belirtilen indexteki elemanı siler |
| `.clear()`         | Tüm elemanları siler               |


## 🔄 7. Listeyi Döngüyle Gezmek
For Döngüsü:
```dart
void main() {
  List<String> renkler = ['Kırmızı', 'Yeşil', 'Mavi'];
  
  for (int i = 0; i < renkler.length; i++) {
    print(renkler[i]);
  }
}
```
For-in Döngüsü:
```dart
void main() {
  List<String> renkler = ['Kırmızı', 'Yeşil', 'Mavi'];
  
  for (var renk in renkler) {
    print(renk);
  }
}

```
forEach() Fonksiyonu:
```dart
void main() {
  List<int> sayilar = [10, 20, 30];
  
  sayilar.forEach((sayi) {
    print(sayi * 2);
  });
}
```

## 🔍 8. Arama ve Filtreleme
```dart
void main() {
  List<int> sayilar = [5, 10, 15, 20];
  
  print(sayilar.contains(10)); // true
  print(sayilar.indexOf(15));  // 2
  print(sayilar.first);        // 5
  print(sayilar.last);         // 20
}
```

 ## 🧮 9. Listeyi Sıralama ve Ters Çevirme
```dart
void main() {
  List<int> sayilar = [4, 1, 7, 3];
  
  sayilar.sort();
  print(sayilar); // [1, 3, 4, 7]
  
  var ters = sayilar.reversed.toList();
  print(ters); // [7, 4, 3, 1]
}
```

## 🧠 10. Listeyi Dönüştürme (map, where, toList)
```dart
void main() {
  List<int> sayilar = [1, 2, 3, 4, 5];
  
  var kareler = sayilar.map((x) => x * x).toList();
  print(kareler); // [1, 4, 9, 16, 25]
  
  var ciftler = sayilar.where((x) => x.isEven).toList();
  print(ciftler); // [2, 4]
}
```
## 🧰 11. Listeyi Birleştirme
```dart
void main() {
  List<String> a = ['A', 'B'];
  List<String> b = ['C', 'D'];
  
  var birlesik = [...a, ...b];
  print(birlesik); // [A, B, C, D]
}
```
## 🧩 12. Null-Safe Spread Operatörü
```dart
void main() {
  List<int>? liste1;
  List<int> liste2 = [1, 2, 3, ...?liste1];
  
  print(liste2); // [1, 2, 3]
}
```
## 🧮 13. Listeyi Kopyalama
```dart
void main() {
  List<String> orijinal = ['A', 'B', 'C'];
  List<String> kopya = List.from(orijinal);
  
  kopya[0] = 'Z';
  print(orijinal); // [A, B, C]
  print(kopya);    // [Z, B, C]
}

```
## 🚀 14. Liste İçinde Liste (2 Boyutlu Liste)
```dart
void main() {
  List<List<int>> matris = [
    [1, 2],
    [3, 4],
    [5, 6],
  ];
  
  print(matris[0][1]); // 2
}
```

## 🧾 15. Listeyi String’e Dönüştürme
```dart
void main() {
  List<String> kelimeler = ['Merhaba', 'Dart', 'List'];
  print(kelimeler.join(' ')); // Merhaba Dart List
}
```

 # 📚 Özet Tablo

| Metot / Özellik | Açıklama                  |
| --------------- | ------------------------- |
| `.add()`        | Tek eleman ekler          |
| `.addAll()`     | Birden fazla eleman ekler |
| `.remove()`     | Değerle siler             |
| `.removeAt()`   | İndeksle siler            |
| `.clear()`      | Tüm elemanları siler      |
| `.length`       | Eleman sayısını verir     |
| `.contains()`   | Değer içeriyor mu?        |
| `.sort()`       | Küçükten büyüğe sıralar   |
| `.reversed`     | Listeyi ters çevirir      |
| `.map()`        | Her elemana işlem uygular |
| `.where()`      | Filtreleme yapar          |
| `.join()`       | String’e dönüştürür       |


---

# 🧩 Dart’ta List Metotları (first, last, isEmpty, vb.)

Dart dilinde List, birçok kullanışlı özelliğe ve metoda sahiptir.
Aşağıda en sık kullanılan metotların açıklamaları ve örnekleri yer alır.

 ## 🔹 first

Listenin ilk elemanını döndürür.

void main() {
  List<String> meyveler = ['Elma', 'Armut', 'Muz'];
  print(meyveler.first); // Çıktı: Elma
}

## 🔹 last

Listenin son elemanını döndürür.

void main() {
  List<String> meyveler = ['Elma', 'Armut', 'Muz'];
  print(meyveler.last); // Çıktı: Muz
}

## 🔹 isEmpty ve isNotEmpty

Listenin boş olup olmadığını kontrol eder.

void main() {
  List<int> sayilar = [];
  print(sayilar.isEmpty);    // true (liste boş)
  print(sayilar.isNotEmpty); // false (liste dolu değil)
}

## 🔹 length

Listenin eleman sayısını döndürür.

void main() {
  List<String> renkler = ['Kırmızı', 'Yeşil', 'Mavi'];
  print(renkler.length); // Çıktı: 3
}

## 🔹 reversed

Listenin ters çevrilmiş bir Iterable halini döndürür.
Listeye çevirmek için toList() kullanılır.

void main() {
  List<int> sayilar = [1, 2, 3, 4];
  print(sayilar.reversed.toList()); // Çıktı: [4, 3, 2, 1]
}

## 🔹 contains()

Liste içinde belirtilen değerin olup olmadığını kontrol eder.

void main() {
  List<String> meyveler = ['Elma', 'Muz', 'Armut'];
  print(meyveler.contains('Muz'));   // true
  print(meyveler.contains('Karpuz')); // false
}

## 🔹 indexOf()

Bir elemanın listedeki indeksini döndürür.
Bulamazsa -1 döner.

void main() {
  List<String> renkler = ['Kırmızı', 'Yeşil', 'Mavi'];
  print(renkler.indexOf('Yeşil')); // 1
  print(renkler.indexOf('Mor'));   // -1
}

## 🔹 add()

Listeye tek bir eleman ekler.

void main() {
  List<int> sayilar = [1, 2, 3];
  sayilar.add(4);
  print(sayilar); // [1, 2, 3, 4]
}

## 🔹 addAll()

Listeye birden fazla eleman (başka bir liste) ekler.

void main() {
  List<int> sayilar = [1, 2];
  sayilar.addAll([3, 4, 5]);
  print(sayilar); // [1, 2, 3, 4, 5]
}

## 🔹 remove()

Listeden belirtilen değeri siler.
Eğer değer birden fazla varsa, ilk gördüğünü siler.

void main() {
  List<String> meyveler = ['Elma', 'Muz', 'Elma'];
  meyveler.remove('Elma');
  print(meyveler); // [Muz, Elma]
}

## 🔹 removeAt()

Belirtilen indeksteki elemanı siler.

void main() {
  List<String> renkler = ['Kırmızı', 'Yeşil', 'Mavi'];
  renkler.removeAt(1);
  print(renkler); // [Kırmızı, Mavi]
}

## 🔹 clear()

Listeyi tamamen boşaltır.

void main() {
  List<int> sayilar = [10, 20, 30];
  sayilar.clear();
  print(sayilar); // []
}

## 🔹 join()

Listedeki elemanları birleştirir ve araya belirtilen karakteri ekler.

void main() {
  List<String> kelimeler = ['Merhaba', 'Dart', 'Dünyası'];
  print(kelimeler.join(' ')); // Merhaba Dart Dünyası
}

## 🔹 sort()

Listeyi küçükten büyüğe (alfabetik ya da sayısal) sıralar.

void main() {
  List<int> sayilar = [5, 3, 8, 1];
  sayilar.sort();
  print(sayilar); // [1, 3, 5, 8]
}

## 🔹 any() ve every()

Koşula göre herhangi bir veya tüm elemanların durumu kontrol edilir.

void main() {
  List<int> sayilar = [1, 2, 3, 4];

  print(sayilar.any((sayi) => sayi > 3));   // true (en az biri 3'ten büyük)
  print(sayilar.every((sayi) => sayi > 0)); // true (hepsi 0'dan büyük)
}

## 🔹 map() ve forEach()

Listedeki her eleman üzerinde işlem yapar.

void main() {
  List<int> sayilar = [1, 2, 3];
  var kareler = sayilar.map((sayi) => sayi * sayi).toList();
  print(kareler); // [1, 4, 9]
}

## 🔹 where()

Belirli bir şarta uyan elemanları filtreler.

void main() {
  List<int> sayilar = [10, 15, 20, 25];
  var sonuc = sayilar.where((sayi) => sayi > 15).toList();
  print(sonuc); // [20, 25]
}

## 🔹 sublist()

Listenin belirli bir alt kısmını (dilimini) alır.

void main() {
  List<String> renkler = ['Kırmızı', 'Yeşil', 'Mavi', 'Sarı'];
  print(renkler.sublist(1, 3)); // [Yeşil, Mavi]
}



# 📗 Dart’ta Set Yapısı

Dart’ta Set, eşsiz (unique) elemanlardan oluşan koleksiyon yapısıdır.
Listelerden farkı, bir Set’in aynı elemanı birden fazla kez tutmamasıdır.

🔹 1. Set Nedir?

Tanım: Eşsiz elemanlardan oluşan bir koleksiyon.

Sıralama: Dart’ta standart Set sıralı değildir.

Eleman tekrarını engeller.

void main() {
  Set<String> meyveler = {'Elma', 'Armut', 'Muz', 'Elma'};
  print(meyveler); // Çıktı: {Elma, Armut, Muz}
}


Elma sadece bir kez eklenir.

🔹 2. Set Oluşturma Yöntemleri
a) Doğrudan Küme İşaretleriyle
void main() {
  Set<int> sayilar = {1, 2, 3};
  print(sayilar); // {1, 2, 3}
}

b) Boş Set Oluşturma

Boş {} ifadesi Map olarak kabul edilir. Boş Set için Set<T>() kullanılır.

void main() {
  Set<String> bosSet = Set();
  bosSet.add('Yeni Eleman');
  print(bosSet); // {Yeni Eleman}
}

🔹 3. Set’e Eleman Ekleme
void main() {
  Set<int> sayilar = {1, 2};
  
  sayilar.add(3);
  sayilar.addAll([4, 5, 5]); // Tekrar eden eleman eklenmez

  print(sayilar); // {1, 2, 3, 4, 5}
}

🔹 4. Set’ten Eleman Silme
void main() {
  Set<String> meyveler = {'Elma', 'Armut', 'Muz'};

  meyveler.remove('Armut');
  print(meyveler); // {Elma, Muz}

  meyveler.clear();
  print(meyveler); // {}
}

🔹 5. Set Özellikleri
Özellik / Metot	Açıklama
.length	Eleman sayısını verir
.isEmpty / .isNotEmpty	Boşluk kontrolü
.contains(x)	x elemanı var mı?
.add(x) / .addAll()	Eleman ekler
.remove(x)	Eleman siler
.clear()	Tüm elemanları siler
.union(Set)	İki Set’i birleştirir
.intersection(Set)	Ortak elemanları alır
.difference(Set)	Farklı elemanları alır
🔹 6. Set Döngüyle Gezme
void main() {
  Set<String> renkler = {'Kırmızı', 'Yeşil', 'Mavi'};

  // For-in ile
  for (var renk in renkler) {
    print(renk);
  }

  // forEach ile
  renkler.forEach((renk) => print(renk));
}

🔹 7. Set İşlemleri
a) Birleştirme (union)
void main() {
  Set<int> a = {1, 2, 3};
  Set<int> b = {3, 4, 5};
  
  var birlesik = a.union(b);
  print(birlesik); // {1, 2, 3, 4, 5}
}

b) Kesişim (intersection)
void main() {
  Set<int> a = {1, 2, 3};
  Set<int> b = {2, 3, 4};

  var ortak = a.intersection(b);
  print(ortak); // {2, 3}
}

c) Fark (difference)
void main() {
  Set<int> a = {1, 2, 3};
  Set<int> b = {2, 3, 4};

  var fark = a.difference(b);
  print(fark); // {1}
}

🔹 8. Set ve List Dönüşümleri
Set → List
void main() {
  Set<int> sayilar = {1, 2, 3};
  List<int> liste = sayilar.toList();
  print(liste); // [1, 2, 3]
}

List → Set
void main() {
  List<int> liste = [1, 2, 2, 3, 3];
  Set<int> set = liste.toSet();
  print(set); // {1, 2, 3}
}

🔹 9. Set ile Null-Safe Kullanım
void main() {
  Set<int>? sayilar;
  var bosSet = {...?sayilar, 1, 2}; 
  print(bosSet); // {1, 2}
}

🔹 10. Örnek Kullanım Senaryoları

Eşsiz değerler (ID, isim, e-posta) saklamak için.

Tekrarlayan verileri temizlemek için.

Kesişim, fark ve birleşim işlemleri gerektiren durumlar.

void main() {
  List<int> tumSayilar = [1, 2, 2, 3, 4, 4, 5];
  Set<int> benzersiz = tumSayilar.toSet();
  print(benzersiz); // {1, 2, 3, 4, 5}
}

