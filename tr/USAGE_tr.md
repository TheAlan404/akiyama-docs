# Akiyama Docs

[Geri](./INDEX_tr.md)

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

---

> <a name="cmd_clearooc"></a> `.clearooc`

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

---

## Alan Komutları

Alanlar, Akiyama'da kaydedilmiş kilitli kanallardır.
Alanlar ile:
- Among us gibi haritalar (sus),
- Sunucuna ev satın alma sistemi,
- SCP gibi odalar
ve daha fazlasını yapabilirsin.

Her alan bir kilitli kanaldır. Komut kullanarak iki alanı birleştirebilirsiniz.
Bu şekilde üyeleriniz bir komut ile bir alandan diğerine gidebilir.

### Kullanıcı Komutları

---

> <a name="cmd_move"></a> `.move`

**Gereksinim:** yok

Başka bir alana gitmak için bu komutu kullanın. Akiyama size hangi alana gitmek istediğinizi sorar.
Gideceğiniz alanın numarasını yazmanız yeterlidir.

![Move Command Usage by takipsizad](https://ta.is-inside.me/nTEPxm27.gif)

---

> <a name="cmd_connections"></a> `.connections`

**Gereksinim:** none

**Kısaltmalar:** `.conns`

Bu alanın bağlı olduğu diğer alanları listeler.



### Yönetici Komutları

---

> <a name="cmd_create"></a> `.create [kategori id'si] <isim>`

**Gereksinim:** yönetici izni

Bir kanal açar ve alan olarak kaydeder.
Kategori id'si girilmemiş ise komutun çalıştırıldığı kategorinin altında oluşturur.

*Örnek:*
- `.create otel-odası-6`
- `.create 852916054531637289 otel-koridoru`

---

> <a name="cmd_bind"></a> `.bind [#kanal(lar)]`

**Gereksinim:** yönetici izni

Var olan bir kanalı alan olarak kaydeder, kilitli değil ise kilitler.
Eğer bir kanal verilmemişse komutun yazıldığı kanalı kaydeder.
Birden fazla kanalı kabul eder.

*Örnek:*
- `.bind`
- `.bind #güvenlik-ofisi`
- `.bind #otel-odası-2 #otel-odası-7 #asansör`

---

> <a name="cmd_bindcategory"></a> `.bindcategory <kategori id'si>`

**Gereksinim:** yönetici izni

Bütün bir kategoriyi/içindeki kanalları bir alan olarak kaydeder.

---

> <a name="cmd_label"></a> `.label`

**Gereksinim:** yönetici izni

**Kısaltmalar:** `.setlabel`

Bir alan için bir label (etiket) ayarlar.
Etiketler `.move` ve `.connections` komutunda gözükür.

---

> `.connect <#kanal1> <#kanal2>`

**Gereksinim:** yönetici izni

İki alanı bağlar, böylece üyeler `.move` ile iki alan arasında geçiş yapabilir.

---

> `.deconnect <#kanal1> <#kanal2>`

**Gereksinim:** yönetici izni

Bağlantıyı siler.

---

#### <a name="Requirements"></a> Gereksinimler

Akiyama'da bir alanın bağlantılarına gereksinim ekleyebilirsiniz.
Gereksinimler bazı şeylerin olup olmadığına bakar.
Mesela kullanıcıda bir rol varmı yada yok mu

Gereksinimlerin bir *değer*i vardır

<a name="reqtypes"></a> **Gereksinim Tipleri**
- `item_has`

    değer bir item id'sidir
    kullanıcıda bir itemin olduğuna bakar

- `item_nothas`

    değer bir item id'sidir
    kullanıcıda bir itemin *olmadığına* bakar

- `roles_has`

    değer bir rol id'sidir
    kullanıcıda bir rolün olduğuna bakar

- `role_nothas`

    değer bir rol id'sidir
    kullanıcıda bir rolün *olmadığına* bakar

Daha fazla gereksinim tipi var ama yapımdadır.



---

> `.addrequirement <connection idx.> <req. type> <req. data>`

**Requires:** administrator permissions

**Aliases:** `.addreq`

Adds a requirement to a connection. This can be used to "lock" an area to certain users.
For example, a hotel room that requires a keycard.

✨ **Editors Note!:** This looks very complicated, but trust me, its easy.
- Connection index is the number that you type when you use `.move`
- Req. type is the requirement type, for example `item_has`
- Req. data is the requirement's data.
  For example, if the requirement is `item_has` then it is the item's id.
  All the types and what their data is [can be found here](#reqtypes)

*Examples:*
- `.addreq 1 item_has ZMYSBI`

   add a requirement to the first connection,
   that checks if the user has the item with the ID 'ZMYSBI'

- `.addreq 1 role_has 850810225933025320`

   add a requirement that checks for the role


---

> `.removerequirement <connection index> <requirement index>`

**Requires:** administrator permissions

**Aliases:** `.remreq`

Removes a requirement. The requirement index is listed in the `.connections` command.

*Examples:*
- `.remreq 1 1`
- `.remreq 2 1`

---


## İtem Ayarlama


TODO!!! -dennis

