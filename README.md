# Golang Dilini Anlamak

## Golang İlk Proje 

- Go ile Web Uygulaması Geliştirmeye Başlamak

Go programlama dili ile web uygulamaları geliştirmek oldukça keyifli bir süreçtir.
Bu bölümde, Go geliştirme ortamını hazırlayacak ve basit bir web uygulaması oluşturup çalıştıracağız.
Amacımız, Go yazmanın nasıl bir deneyim olduğunu anlamaktır; bu nedenle, kullanılan tüm dil özelliklerini tam olarak anlamasanız da sorun yok.

1. Senaryoyu Belirleme

Hayal edin ki bir erkek arkadaşınız bekarlığa veda partisinin ev sahipliğini yapıyor ve 
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

## Go ile Web Uygulaması Geliştirme Projesi Oluşturma

Go programlama dili ile web uygulamaları geliştirmek için ilk adım, projenizi oluşturmaktır. 
"bachelorette" adında bir proje oluşturmayı öğreneceksiniz. 

1. Proje Klasörünü Oluşturma

Öncelikle, bir komut istemcisi açın ve uygun bir konuma gidin. 
Ardından, aşağıdaki komutla "bachelorette" adında bir klasör oluşturun:

```bash
mkdir bachelorette
cd bachelorette
```

Resim :

![Resim](https://i.ibb.co/zFKbPYZ/Bachelorette-File.png)

2. Go Projesini Başlatma

Klasöre girdikten sonra, yeni bir Go projesi başlatmak için aşağıdaki komutu çalıştırın:

```bash
go mod init bachelorette
```

Bu komut, projenizin bağımlılıklarını takip eden bir go.mod dosyası oluşturur. 
Ayrıca, projenizi gerektiğinde yayınlamak için de kullanılabilir.

![Resim](https://i.ibb.co/1XFSw6m/resim-2024-09-22-142821998.png)

3. Main Go Dosyasını Oluşturma

Go kod dosyaları .go uzantısına sahiptir. 
Seçtiğiniz editörü kullanarak "main.go" adında bir dosya oluşturun ve aşağıdaki içeriği ekleyin:

```golang
package main

import "fmt"

func main() {
    fmt.Println("Hello World!")
}
```

![Resim](https://i.ibb.co/G5yXB7X/resim-2024-09-22-143218374.png)

Eğer Visual Studio Code kullanıyorsanız ve bu sizin ilk Go dosyanızsa, Go dilini destekleyen uzantıları yüklemeniz istenecektir.

![Resim](https://i.ibb.co/h180Xmc/VS-Code-Golang.png)

## Go Dilinin Temel Yapısı

Go dilinin sözdizimi, C veya C benzeri diller (C#, Java vb.) ile tanıdık gelebilir. 
Go dilini derinlemesine inceleyeceğiz, ancak kodun yapısına ve anahtar kelimelerine bakarak çok şey öğrenebilirsiniz.

- Package: Özellikler paketler halinde gruplanır; bu nedenle package ifadesi kullanılır.
- Import: Diğer paketlere bağımlılıkları belirtmek için import ifadesi kullanılır.
- Function: İşlevler func anahtar kelimesi ile tanımlanır. main işlevi, uygulamanın başlangıç noktasıdır.

Yukarıdaki kodda main fonksiyonu, fmt paketinden sağlanan Println fonksiyonunu çağırır ve "Hello World!" mesajını ekrana yazdırır.


4. Projeyi Derleme ve Çalıştırma

Projeyi derleyip çalıştırmak için aşağıdaki komutu kullanın:

```bash
go run .
```

Bu komut, geliştirme sürecinde oldukça kullanışlıdır çünkü derleme ve çalıştırma işlemlerini tek adımda gerçekleştirir. 

Uygulama şu çıktıyı verecektir:

```
Hello World!
```

Resim :

![Resim](https://i.ibb.co/KVzWN6m/Go-Run.png)

Eğer bir derleyici hatası alırsanız, muhtemelen kodu tam olarak belirtilen şekilde girmemişsinizdir. 
Go, belirli bir kod biçimini zorunlu kılar. 

5. Kod Biçimlendirme Hatası

Eğer kodu aşağıdaki gibi yazdıysanız:

```golang
package main

import "fmt"

func main()
{
    fmt.Println("Hello World!")
}
```

Aşağıdaki hatalarla karşılaşabilirsiniz:

```bash
missing function body
syntax error: unexpected semicolon or newline before {
```

Resim :

![Resim](https://i.ibb.co/1rDpfvL/Go-Error.png)

Go, belirli bir kod stiline uymayı zorunlu kılar ve yaygın kod öğeleri (noktalı virgül gibi) ile alışılmadık şekillerde ilgilenir.

## Go ile Özel Veri Türü ve Koleksiyon Oluşturma

Go dilinde, özel veri türleri tanımlamak ve koleksiyonlar oluşturmak, uygulama geliştirme sürecinin önemli bir parçasıdır.
Bu yazıda, RSVP yanıtlarını temsil eden bir veri türü oluşturmayı ve bu yanıtları bir koleksiyonda saklamayı öğreneceksiniz.

1. Özel Veri Türü Tanımlama

Öncelikle, RSVP yanıtlarını temsil eden bir veri türü tanımlayalım. 
Aşağıdaki kod parçası, Rsvp adında bir yapı (struct) oluşturmaktadır:

```golang
package main

import "fmt"

type Rsvp struct {
	Name, Email, PhoneNumber string
	Participation            bool
}
```


Bu yapı, dört alan içermektedir: Name, Email, PhoneNumber ve Participation. 
Name, Email ve PhoneNumber alanları string veri türünde, Participation alanı ise boolean (bool) veri türündedir.
Go dilinde özel türler tanımlamak için type anahtar kelimesi kullanılır. 
Yapılar, ilişkili değerlerin bir arada gruplanmasına olanak tanır.

2. Yanıtları Toplama

RSVP yanıtlarını toplamak için bir koleksiyon oluşturmamız gerekiyor. 
İlerleyen bölümlerde veritabanı kullanımı hakkında bilgi vereceğiz; ancak bu bölümde yanıtları bellekte saklayacağız. 
Bu nedenle, uygulama durdurulduğunda yanıtlar kaybolacaktır.

Go, fixed length arrays(sabit uzunlukta dizeler), variable length arrays (değişken uzunlukta dizeler) ve 
key-value pairs(anahtar-değer çiftleri) içeren haritalar (maps) için yerleşik destek sunar. 

Aşağıdaki kod parçası, bilinmeyen sayıda değer depolamak için uygun olan bir dilim (slice) oluşturmaktadır:

```golang
var responses = make([]*Rsvp, 0, 10)
```


3. Slice Tanımlama Açıklaması

Yukarıdaki kodda, make fonksiyonu kullanılarak yeni bir slice oluşturulmaktadır. 
'make' fonksiyonu üç argüman alır: slice veri türü, başlangıç boyutu ve başlangıç kapasitesi.

- Başlangıç Boyutu: 0 olarak ayarlandığında boş bir slice oluşturulur.
- Başlangıç Kapasitesi: 10 olarak belirlendiğinde, slice 10 eleman eklenmeden önce yeniden boyutlandırılmasına gerek kalmayacaktır.

Slice tanımında kullanılan *Rsvp, Rsvp yapısının işaretçilerini (pointer) içeren bir dilimi temsil eder. 
İşaretçi kullanımı, değerlerin kopyalanmasını önleyerek bellek kullanımını optimize eder.

Kodu kullanmak için tam hali şu şekil de :

```golang
package main

import "fmt"

type Rsvp struct {
	Name, Email, PhoneNumber string
	Participation            bool
}

var response = make([]*Rsvp, 0, 10)

func main() {

	newRsvp := &Rsvp{
		Name:          "BerKolik",
		Email:         "berkolik@example.com",
		PhoneNumber:   "123-456-7890",
		Participation: true,
	}

	newRsvp2 := &Rsvp{
		Name:          "BerKolikTwo",
		Email:         "berkoliktwo@example.com",
		PhoneNumber:   "123-456-4321",
		Participation: true,
	}

	newRsvp3 := &Rsvp{
		Name:          "BerKolikThree",
		Email:         "berkolikthree@example.com",
		PhoneNumber:   "123-456-3214",
		Participation: true,
	}

	response = append(response, newRsvp, newRsvp2, newRsvp3)

	fmt.Println(response)
}
```
