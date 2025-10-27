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
void main() {
  List<String> sehirler = ['Ankara', 'İzmir', 'Bursa'];
  List<int> sayilar = [1, 2, 3, 4];
}
