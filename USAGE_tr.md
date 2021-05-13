# Akiyama Docs

[Geri](./README_tr.md)

Kullanım
--------

#### Not

Komutlarda, gerekli alanlar `<` ve `>` ile başlayıp biticek.
Opsiyonel olanlar ise `[` ve `]` ile başlayıp biter.
Komutları kullanırken o sembolleri yazmayın.


## OOC Mesajları

OOC mesajları, Out Of Character yani karakter dışı mesajlardır.
Genellikle roleplaylerde karakterinin dışında konuşurken kullanılır (mesela AFK olduğunu belirtmek için),
ama sayı sayma vs gibi oyun kanallarında da kullanılıyor.

OOC mesaj örnekleri:
- `((hayır dur`
- `//evet`
- `ben afkyım bb))`

Bazı zamanlarda kanallar OOC mesajlar ile kaplı olabilir.
Bunun için Akiyama'da birkaç komut var.

> `.clearooc`

Kanaldaki OOC mesajları temizler. Eğer diğerlerinin mesajlarını
silmeye yetkin yok ise Akiyama sadece senin OOC mesajlarını siler.

> `.autoclearooc [süre]`

**Gereksinim:** yönetici yetkisi (administrator)

Bu bir ayar. Eğer ayarlı ise Akiyama OOC mesaj gördüğünde *süre* kadar saniye bekler
ve ondan sonra mesajı siler.

Ayrıca, eğer OOC mesajın *3'üncü* karakteri `!` ise
(örn. `((!selam`) Akiyama otomatik olarak silmez.
Bu özellik diğer kişinin görmesi uzun sürüyorsa vs için kullanışlıdır.

Bu özelliği kapatmak için `.autoclearooc off` komutunu kullanabilirsiniz

Örnek kullanımlar:
- `.autoclearooc 60` // bir dakika sonra sil
- `.autoclearooc 120` // iki dakika
- `.autoclearooc off` // kapat

## İtem Ayarlama


TODO!!! -dennis

