# 🐧 Linux Nedir? 

> *"Linux sadece bir işletim sistemi değil, bir felsefe."*
> — Neredeyse herkes

Selamun aleyküm! Bu seri boyunca Linux'u sıfırdan öğreneceğiz. Ama önce şunu sormamız lazım: **Linux tam olarak ne?** Bunu anlamadan devam etmek, binanın temelini dökmeden kata çıkmaya benzer. O yüzden bu ilk yazıda acele etmeyeceğiz. Tek tek, katman katman, "neden böyle?" sorularını da yanıtlayarak gideceğiz.


---

## İçindekiler

1. [İşletim Sistemi Denen Şey Ne Zaten?](#1-i̇şletim-sistemi-denen-şey-ne-zaten)
2. [Linux Nasıl Ortaya Çıktı?](#2-linux-nasıl-ortaya-çıktı)
3. [Linux Bir Çekirdek, Dağıtımlar İse Bütün Sistem](#3-linux-bir-çekirdek-dağıtımlar-i̇se-bütün-sistem)
4. [Katmanlar: Bilgisayarın İçindeki Soğan](#4-katmanlar-bilgisayarın-i̇çindeki-soğan)
   - [Donanım Katmanı](#donanım-katmanı)
   - [Çekirdek (Kernel) Katmanı](#çekirdek-kernel-katmanı)
   - [Sistem Çağrıları (Syscall) Katmanı](#sistem-çağrıları-syscall-katmanı)
   - [Kullanıcı Alanı (Userspace) Katmanı](#kullanıcı-alanı-userspace-katmanı)
   - [Kabuk (Shell) Katmanı](#kabuk-shell-katmanı)
   - [Masaüstü Ortamı Katmanı](#masaüstü-ortamı-katmanı)
5. [Linux Ne Değildir?](#5-linux-ne-değildir)
6. [Linux Neden Bu Kadar Yaygın?](#6-linux-neden-bu-kadar-yaygın)

---

## 1. İşletim Sistemi Denen Şey Ne?

Şöyle düşün: Bilgisayarın var. İçinde CPU var, RAM var, depolama var. Bunlar ham donanım — tek başlarına hiçbir şey yapamıyorlar. Birine "Hey, şu dosyayı oku" demen için arada bir *tercüman* lazım.

İşte o tercüman: **işletim sistemi (Operating System / OS)**.

İşletim sistemi temel olarak şunları yapar:

- Programların donanımı *doğrudan* kullanmasını engeller (bu kaos yaratır)
- Bunun yerine programlara "benden iste, ben hallederim" der
- Birden fazla programın aynı anda çalışmasını yönetir
- Belleği kim ne kadar kullanacak, ona karar verir
- Dosyaları diskten okur, diske yazar
- Ağ kartına "şu paketi gönder" der

Yani sen bir tarayıcı açtığında, işletim sistemi arka planda onlarca kararı senin adına veriyor. Sen sadece "Google" yazıp Enter'a basıyorsun.

---

## 2. Linux Nasıl Ortaya Çıktı?

1991'de Linus Torvalds adında Finlandiyalı bir üniversite öğrencisi, bilgisayarı için iyi bir işletim sistemi istiyordu. O dönemin Unix'i pahalıydı, MS-DOS ise çok ilkeldi.

21 yaşındaki Linus şöyle bir mesaj attı bir e-posta listesine:

> *"Merhaba. Minix gibi (ama daha iyisi olan) ücretsiz bir işletim sistemi yapıyorum. Bu sadece bir hobi, GNU gibi büyük ve profesyonel bir şey olmayacak..."*

Ve işte o "hobi" projesi bugün:

- 🌍 Dünyanın en büyük web sunucularının %96'sını çalıştırıyor
- 📱 Milyarlarca Android telefonun içinde yaşıyor
- 🚀 NASA ve SpaceX'in kritik sistemlerinde kullanılıyor
- 🔬 Mars'taki Ingenuity helikopterini uçurdu
- 💻 Dünyanın en hızlı 500 süper bilgisayarının **tamamında** çalışıyor

Küçük hobiler bazen dünyayı değiştirir.

---

## 3. Linux Bir Çekirdek, Dağıtımlar İse Bütün Sistem

Burada çok önemli bir ayrım var ve çoğu kişi bunu karıştırıyor.

**Linux teknik olarak sadece bir *çekirdek* (kernel).**

Çekirdek ne demek? Birazdan çok daha detaylı anlatacağım ama kısaca: donanımla konuşan, her şeyin üzerine inşa edildiği temel yazılım parçası.

Ama sen masaüstüne sağ tıklayıp "Yeni Klasör" oluşturduğunda, sadece çekirdek çalışmıyor. Orada bir grafik arayüz var, bir dosya yöneticisi var, bir terminal var, bir paket yöneticisi var... Bunların hepsi bir araya gelince ortaya bir **dağıtım (distribution / distro)** çıkıyor.

Yani Linux çekirdeği + GNU araçları + masaüstü ortamı + paket yöneticisi + diğer yazılımlar = **dağıtım**

Bu yüzden teknik olarak "Ubuntu kullanıyorum" veya "Fedora kullanıyorum" demen daha doğru. Ama herkes kısaca "Linux kullanıyorum" diyor ve bu da tamamen kabul edilebilir.

Birkaç popüler dağıtım:

| Dağıtım | Kime Göre? | Not |
|---|---|---|
| **Ubuntu** | Yeni başlayanlar | En geniş topluluk desteği |
| **Linux Mint** | Windows'tan geçenler | Tanıdık arayüz |
| **Fedora** | Güncel teknoloji isteyenler | Red Hat'in sponsorluğunda |
| **Debian** | Kararlılık arayanlar | Onlarca dağıtımın anası |
| **Arch Linux** | "Ben her şeyi kendim yaparım" diyenler | Dik öğrenme eğrisi |
| **Kali Linux** | Siber güvenlik meraklıları | Güvenlik araçları paketi |
| **Ubuntu Server** | Sunucu yöneticileri | Grafik arayüz yok |

> 💡 **Not:** Hangi dağıtımı seçmeli sorusunu ilerleyen yazılarda ele alacağız. Şimdilik sadece "bunlar var" bil.

---

## 4. Katmanlar: Bilgisayarın İçindeki Soğan

Şimdi işin en güzel kısmına geliyoruz. Linux'u (ve aslında modern her işletim sistemini) anlamanın en iyi yolu onu **katmanlar** olarak düşünmek.

Soğanı hatırla. Dışarıdan soyarken katmanlar çıkar. Bilgisayar da böyle. En dışta kullanıcı var, en içte donanım var. Ve arada bir sürü katman.

```
┌─────────────────────────────────────────────────────────┐
│                   KULLANICI (Sen)                        │
├─────────────────────────────────────────────────────────┤
│              Masaüstü Ortamı (GNOME, KDE...)             │
├─────────────────────────────────────────────────────────┤
│                 Kabuk / Shell (Bash, Zsh)                │
├─────────────────────────────────────────────────────────┤
│           Kullanıcı Alanı (Uygulamalar, Kütüphaneler)    │
├─────────────────────────────────────────────────────────┤
│              Sistem Çağrıları (Syscall API)              │
├─────────────────────────────────────────────────────────┤
│                  ÇEKİRDEK (Kernel)                       │
├─────────────────────────────────────────────────────────┤
│              DONANIM (CPU, RAM, Disk, Ağ...)             │
└─────────────────────────────────────────────────────────┘
```

Her katmanı tek tek konuşalım.

---

### Donanım Katmanı

En alt katman. Fiziksel şeyler burada:

- **CPU (İşlemci):** Hesaplamaları yapar. Sadece 0 ve 1 bilir.
- **RAM (Bellek):** Şu an çalışan şeylerin geçici deposu. Bilgisayar kapanınca silinir.
- **Disk (SSD/HDD):** Kalıcı depolama. Dosyaların, programların yaşadığı yer.
- **Ağ Kartı (NIC):** İnternete bağlanmanı sağlar.
- **GPU:** Ekrana pikselleri çizer. Artık hesaplama için de kullanılıyor (yapay zeka vs.).
- **Diğer aygıtlar:** USB, klavye, fare, mikrofon, sensörler...

Donanım, tek başına bir robot gibi. Sana talimat verilmeden hiçbir şey yapamaz. Ve donanımla konuşmak için özel bir dil gerekir — her donanımın kendine özgü komutları vardır.

Peki her uygulama bu dili öğrenmek zorunda mı? Hayır. İşte bu sorunu çekirdek çözüyor.

---

### Çekirdek (Kernel) Katmanı

Çekirdek, tüm sistemin kalbidir. Bir tür "donanım yöneticisi" olarak düşün.

Şunları yapar:

**Bellek Yönetimi:** RAM'i kim ne kadar kullanacak? Bir program 8 GB RAM istiyorsa ve sistemde 4 GB varsa ne olacak? Sanal bellek devreye girer. Çekirdek, programlara "tamam sende 8 GB var" der ama aslında diski de bellek gibi kullanır (swap). Program bunun farkında bile olmaz.

**Süreç Yönetimi:** Bilgisayarında şu an yüzlerce program çalışıyor olabilir. Ama CPU tek bir anda sadece birkaç şey yapabilir. Çekirdek, CPU zamanını programlar arasında o kadar hızlı böler ki sanki hepsi aynı anda çalışıyormuş gibi görünür. Buna **çok görevlilik (multitasking)** denir.

**Aygıt Sürücüleri (Device Drivers):** Her donanımla konuşmanın kendi yolu var. Çekirdek, içinde binlerce donanım sürücüsü barındırır. Sürücüler, çekirdekle donanım arasındaki çevirmeni oynar. Sen "dosyayı kaydet" diyorsun, çekirdek disk sürücüsüne "şu sektöre şu veriyi yaz" diyor.

**Dosya Sistemi:** Diskteki verileri anlamlı bir yapıya kavuşturur. Linux'ta birden fazla dosya sistemi desteklenir: ext4, btrfs, xfs, zfs... Her birinin avantajları farklı ama bunu ilerleyen yazılarda anlatacağız.

**Ağ Yönetimi:** TCP/IP paketlerini gönderip almak, ağ arayüzlerini yönetmek, güvenlik duvarı kurallarını uygulamak — bunlar çekirdeğin işi.

**Güvenlik ve İzinler:** Hangi kullanıcı hangi dosyaya erişebilir? Hangi program hangi kaynağı kullanabilir? Çekirdek bunu takip eder.

> 💡 **Önemli Bir Şey:** Çekirdek, iki ayrı dünyada çalışır: **Kernel Space** (çekirdeğin kendi alanı) ve **User Space** (senin programlarının alanı). Bu ayrım kasıtlı. Bir uygulama hata yapsa bile çekirdeği çökertemiyor. Güvenlik de, kararlılık da buradan geliyor.

---

### Sistem Çağrıları (Syscall) Katmanı

Tamam, çekirdek var. Ama senin programın (mesela bir metin editörü) "hey çekirdek, şu dosyayı aç" demesi lazım. Bunu nasıl yapıyor?

**Sistem çağrıları (system calls / syscalls)** ile.

Syscall'lar, kullanıcı alanındaki programların çekirdeğe resmi olarak istek gönderebildiği kapılardır. Sadece belirlenmiş kapılar var. Programlar istediği kapıdan giremez — sadece tanımlı syscall'ları kullanabilir.

Linux'ta yaklaşık 300-400 tane syscall var. Birkaç örnek:

```
open()    → dosya aç
read()    → dosyadan oku
write()   → dosyaya yaz
fork()    → yeni bir süreç oluştur
exec()    → bir programı çalıştır
socket()  → ağ bağlantısı oluştur
exit()    → programı sonlandır
```

Sen bir Python scripti yazarken `open("dosya.txt")` diyorsun ya? Python kütüphanesi bu talebi alıp `open()` syscall'ına çeviriyor. Çekirdek de gidip gerçekten diskteki dosyayı açıyor.

Aradaki katmanlar şeffaf — sen görmüyorsun ama hepsi çalışıyor.

---

### Kullanıcı Alanı (Userspace) Katmanı

Çekirdeğin dışındaki her şey kullanıcı alanında çalışır. Tarayıcın, metin editörün, müzik uygulamandaki her şey burada.

Bu katmanda iki önemli şey var:

**Kütüphaneler (Libraries):** Programcıların her şeyi sıfırdan yazmaması için önceden yazılmış, tekrar kullanılabilir kod blokları. En önemli örnek: **glibc** (GNU C Library). Linux'taki programların büyük çoğunluğu syscall'lara bu kütüphane üzerinden erişir.

Örneğin ekrana bir şey yazdırmak istiyorsun. Doğrudan ekran kartıyla mı konuşacaksın? Hayır. `printf()` fonksiyonunu çağırıyorsun, o da arka planda `write()` syscall'ını tetikliyor, çekirdek de terminale yazıyor.

**Sistem Araçları ve GNU Araçları:** `ls`, `cp`, `grep`, `awk`, `sed`... Bunlar terminal komutları. Hepsi birer küçük programdır ve kullanıcı alanında çalışırlar. Richard Stallman ve GNU projesi, Linus'un çekirdeğini tamamlamadan önce bu araçların büyük bölümünü yazmıştı. Bu yüzden "GNU/Linux" deniyor.

---

### Kabuk (Shell) Katmanı

Shell, senin komutlarını alıp çalıştıran programdır. Terminal açtığında karşına gelen `$` işaretinin arkasında shell var.

Shell bir *arayüz* ama grafik değil, metin tabanlı. Ona komut yazarsın, o da ilgili programları çalıştırır, syscall'ları tetikler, sonuçları sana gösterir.

Linux'ta birden fazla shell var:

- **Bash (Bourne Again Shell):** En yaygın, çoğu sistemde varsayılan
- **Zsh:** Bash'in daha güçlü hali, macOS'un yeni varsayılanı
- **Fish:** Kullanıcı dostu, otomatik tamamlama özelliği mükemmel
- **sh (POSIX shell):** En basit, en temel, her yerde var

Shell aynı zamanda **script yazabileceğin** bir programlama dili sunar. Tekrar eden görevleri otomatize etmek için shell script'leri yazılır. Mesela her gece yedekleme alan, log temizleyen, rapor gönderen scriptler. Bunları ilerleyen yazılarda çok detaylı göreceğiz.

---

### Masaüstü Ortamı Katmanı

Bu katman opsiyonel. Sunucularda hiç masaüstü olmaz. Ama kişisel bilgisayarlarda grafik arayüz istiyorsan bu katman devreye girer.

Linux'ta masaüstü ortamları da modüler yapıdadır — istediğini seçebilirsin:

**GNOME:** Modern, sade tasarım. Ubuntu'nun varsayılanı. Dokunmatik ekranlar için de iyi.

**KDE Plasma:** Özelleştirme cenneti. Windows'a benzer bir düzen isteyenler için ideal. Hafıza kullanımı verimli.

**XFCE:** Hafif ve hızlı. Eski bilgisayarlar için biçilmiş kaftan.

**LXDE / LXQt:** Daha da hafif. Gerçekten eski donanımlarda bile çalışır.

**i3 / Sway:** "Masaüstüm tam benim kontrolümde olsun" diyenler için. Fare kullanmadan, sadece klavyeyle yönetilen pencere yöneticileri.

Masaüstü ortamının altında bir de **display server** var. Uzun süre X11 kullanıldı, şimdi yerine **Wayland** geçiyor. Ama bunun detayına şimdi girmemize gerek yok.

---

## 5. Linux Ne Değildir?

Bazen bir şeyi anlamanın en iyi yolu, ne olmadığını söylemektir.

**Linux bir şirketin ürünü değildir.** Windows Microsoft'a, macOS Apple'a aittir. Linux ise kimseye ait değildir — ya da herkese aittir, nasıl bakarsan. Linus Torvalds çekirdeğin bakımını yönetiyor ama o bile tek başına karar veremiyor.

**Linux sadece sunucular için değildir.** Bu önyargı hâlâ yaygın. Ama masaüstü Linux çok olgunlaştı. Günlük kullanım için gayet yeterli.

**Linux kullanmak için hacker olmak gerekmez.** Terminal seni korkutmasın. Başlangıçta grafik arayüzle her şeyi yapabilirsin. Terminal, işleri hızlandıran bir araç — zorunlu bir eziyet değil.

**Linux tek bir şey değildir.** Ubuntu ile Arch Linux teknik olarak aynı çekirdekle çalışır ama birbirinden çok farklı deneyimler sunarlar. "Linux kullandım, sevmedim" derken hangi dağıtımı denediğin önemli.

**Linux ücretsiz ama "değersiz" değildir.** Ücretsiz olması düşük kaliteli olduğu anlamına gelmez. Aksine, dünyanın en yetenekli yazılımcıları onlarca yıldır bu projeye katkıda bulunuyor.

---

## 6. Linux Neden Bu Kadar Yaygın?

Özellikle sunucularda Linux'un bu denli hakim olmasının somut nedenleri var:

**Kararlılık:** Düzgün yapılandırılmış bir Linux sunucusu yıllarca yeniden başlatılmadan çalışabilir. Windows Server bunu nadiren başarabilir.

**Güvenlik:** İki nedenden dolayı daha güvenli. Birincisi, açık kaynak olduğu için binlerce göz kodu inceliyor, açıklar hızla bulunup kapatılıyor. İkincisi, kullanıcı izinleri modeli çok daha katı — kötü amaçlı bir program kolayca yayılamıyor.

**Verimlilik:** Linux, kaynaklarını çok verimli kullanır. Aynı donanımda Windows'tan daha iyi performans verir. Sunucu maliyetleri düşer.

**Özelleştirme:** Her şeyi ihtiyacına göre ayarlayabilirsin. Gereksiz hiçbir şey yok — sadece ne lazımsa o var.

**Topluluk ve Ekosistem:** Bir sorunla karşılaştığında Stack Overflow'da, Reddit'te, forum sayfalarında büyük ihtimalle aynı soruyu yaşamış biri var ve çözüm zaten yazılı.

**Maliyet:** Ücretsiz. Yüzlerce sunucu çalıştıracaksan bu lisans maliyeti ciddi bir rakam demek.

---

> **Bu seri hakkında:** Bu GitHub reposu, Siber güvenliği sıfırdan öğrenmek isteyenler için yazılıyor. Her yazı bir öncekinin üzerine inşa edilecek. Takip et, yıldız ver, arkadaşlarınla paylaş. 

---

*Yazım hatası mı buldun? Eklememi istediğin bir konu var mı? Issue aç veya PR gönder!*
