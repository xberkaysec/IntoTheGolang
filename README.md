# Golang Dilini Anlamak

## Golang İlk Proje 

- Go ile Web Uygulaması Geliştirmeye Başlamak

Go programlama dili ile web uygulamaları geliştirmek oldukça keyifli bir süreçtir.
Bu bölümde, Go geliştirme ortamını hazırlayacak ve basit bir web uygulaması oluşturup çalıştıracağız.
Amacımız, Go yazmanın nasıl bir deneyim olduğunu anlamaktır; bu nedenle, kullanılan tüm dil özelliklerini tam olarak anlamasanız da sorun yok.

1. Senaryoyu Belirleme

Hayal edin ki bir erkek arkadaşınız bekarlığıa veda partisinin ev sahipliğini yapıyor ve 
davetlilerin elektronik ortamda katılım bildirmesi için bir web uygulaması oluşturmanızı istiyor.
Arkadaşınızın istediği temel özellikler şunlardır:

- Partinin bilgilerini gösteren bir ana sayfa.
- Katılım bildirmek için kullanılacak bir form ve bu formun ardından teşekkür sayfası.
- RSVP(Lütfen yanıtlayın) formunun doldurulup doldurulmadığını kontrol eden bir doğrulama.
- Partiye katılacakların listesini gösteren bir özet sayfa.

Bu bölümde, bu özellikleri içeren basit bir uygulama geliştireceğiz.

2. Geliştirme Araçlarını Kurma

İlk adım, Go geliştirme araçlarını kurmaktır. [Go resmi web sitesine](https://golang.org/dl) gidin ve işletim sisteminize uygun kurulum dosyasını indirin. 
Windows, Linux ve macOS için kurulum dosyaları mevcuttur. 
İşletim sisteminize uygun kurulum talimatlarını [buradan](https://golang.org/doc/install) bulabilirsiniz.

Kurulumu tamamladıktan sonra, bir komut istemcisi açın ve aşağıdaki komutu çalıştırarak Go araçlarının doğru bir şekilde yüklendiğini kontrol edin:

```bash
go version
```

Yazım zamanında mevcut versiyon 1.23.1’dir ve Windows makinemde aşağıdaki çıktıyı üretmektedir:

```bash
go version go1.23.1 windows/amd64
```

Resim : 

![Resim](https://i.ibb.co/6sKvz3n/resim-2024-09-22-141915811.png)

Farklı bir sürüm numarası veya işletim sistemi detayları görseniz de sorun yok; önemli olan go komutunun çalışması ve çıktı vermesidir.

3. Git Kurulumu

Bazı Go komutları, Git versiyon kontrol sistemine ihtiyaç duyar. 
[Git resmi web sitesine](https://git-scm.com) gidin ve işletim sisteminize uygun kurulum talimatlarını takip edin.

4. Kod Editörü Seçimi

Son adım, bir kod editörü seçmektir. Go kaynak kodu dosyaları düz metin olduğundan, neredeyse her editörü kullanabilirsiniz. 
Ancak bazı editörler, Go için özel destek sunmaktadır. En popüler seçeneklerden biri ücretsiz olan Visual Studio Code’dur; bu editör, en son Go dil özelliklerini desteklemektedir.
Eğer başka bir tercihiniz yoksa, Visual Studio Code’u öneririm. [Visual Studio Code’u buradan](http://code.visualstudio.com) indirebilirsiniz; 
tüm popüler işletim sistemleri için kurulum dosyaları mevcuttur. Projeye başlayacağınızda Go için gerekli uzantıları yüklemeniz istenecektir.

Eğer Visual Studio Code’u beğenmiyorsanız, [buradan](https://github.com/golang/go/wiki/IDEsAndTextEditorPlugins) mevcut diğer seçenekleri görebilirsiniz.

