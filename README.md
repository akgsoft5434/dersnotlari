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

---

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

