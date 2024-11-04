# OtobusBiletiRezervasyonSistemi
### Yolcular 
•	YolcuID (Birincil Anahtar)
•	Ad
•	Soyad
•	E-posta
•	Şifre
•	Telefon
•	KayıtTarihi
•	Adres
•	Cinsiyet
________________________________________
## Otobüsler 
•	OtobüsID (Birincil Anahtar)
•	PlakaNo
•	Kapasite
•	Model
•	OtobüsTürü 
•	Özellikler 
•	Klima
•	ÜretimYılı
________________________________________
## Yolculuk Değerlendirmeleri 
•	DeğerlendirmeID (Birincil Anahtar)
•	YolcuID (Yabancı Anahtar)
•	SeferID (Yabancı Anahtar)
•	Puan 
•	Yorum
•	DeğerlendirmeTarihi
•	GörüntülemeDurumu
________________________________________
## Şehirler
•	ŞehirID (Birincil Anahtar)
•	ŞehirAdı
•	Bölge
•	PostaKodu
________________________________________
## Rezervasyonlar
•	RezervasyonID (Birincil Anahtar)
•	SeferID (Yabancı Anahtar)
•	YolcuID (Yabancı Anahtar)
•	KoltukNo
•	RezervasyonTarihi
•	YolculukTürü 
•	Durum
________________________________________
## Otogarlar
•	OtogarID (Birincil Anahtar)
•	ŞehirID (Yabancı Anahtar)
•	OtogarAdı
•	Adres
________________________________________
## Seferler
•	SeferID (Birincil Anahtar)
•	OtobüsID (Yabancı Anahtar)
•	KalkışOtogarID (Yabancı Anahtar)
•	VarışOtogarID (Yabancı Anahtar)
•	KalkışTarihi
•	VarışTarihi
•	Fiyat
•	Durum
________________________________________
## Ödemeler
•	ÖdemeID (Birincil Anahtar)
•	RezervasyonID (Yabancı Anahtar)
•	Tutar
•	ÖdemeTarihi
•	ÖdemeYöntemi
•	Durum
________________________________________
## İndirim Kuponları
•	KuponID (Birincil Anahtar)
•	KuponKodu
•	İndirimOranı
•	GeçerlilikTarihi
•	MinimumTutar
________________________________________
## Bildirimler
•	BildirimID (Birincil Anahtar)
•	YolcuID (Yabancı Anahtar)
•	SeferID (Yabancı Anahtar)
•	Başlık
•	Mesajİçeriği
•	GönderimTarihi
•	Okundu
•	BildirimTürü
 ________________________________________
## Geri Bildirimler ve Şikayetler 
•	GeriBildirimID (Birincil Anahtar)
•	YolcuID (Yabancı Anahtar)
•	SeferID (Yabancı Anahtar)
•	Konu
•	Açıklama
•	Tarih
•	Durum
________________________________________
## Sadakat Programı 
•	ProgramID (Birincil Anahtar)
•	YolcuID (Yabancı Anahtar)
•	ProgramAdı
•	Puan
•	Avantajlar
________________________________________
## Şoförler 
•	ŞoförID (Birincil Anahtar)
•	Ad
•	Soyad
•	Telefon
•	EhliyetNo
•	ÇalışmaDurumu
•	DeneyimYılı
________________________________________
## Operatörler 
•	OperatörID (Birincil Anahtar)
•	OtogarID (Yabancı Anahtar)
•	Ad
•	Soyad
•	Telefon
•	ÇalışmaDurumu
•	İşeGirişTarihi
________________________________________
## Geçiş Noktaları 
•	GeçişID (Birincil Anahtar)
•	SeferID (Yabancı Anahtar)
•	ŞehirID (Yabancı Anahtar)
•	GeçişSırası
•	VarışSaati
•	KalkışSaati



İlişkiler : 
1.	Yolcular - Rezervasyonlar: 1-N (Bir yolcu birden fazla rezervasyon yapabilir.)
2.	Yolcular - Geri Bildirimler: 1-N (Bir yolcu birden fazla geri bildirimde bulunabilir.)
3.	Yolcular - İndirim Kuponları: N-M (Bir yolcu birden fazla indirim kuponu kullanabilir.)
4.	Yolcular - Bildirimler: 1-N (Bir yolcuya birden fazla bildirim gönderilebilir.)
5.	Yolcular - Sadakat Programı: 1-1 (Bir yolcu bir sadakat programına sahip olabilir.)
6.	Yolcular - Yolculuk Değerlendirmeleri: 1-N (Bir yolcu birden fazla yolculuk için değerlendirme yapabilir.)
7.	Otobüsler - Seferler: 1-N (Bir otobüs birden fazla sefere çıkabilir.)
8.	Şehirler - Otogarlar: 1-N (Bir şehirde birden fazla otogar olabilir.)
9.	Otogarlar - Seferler: N-1 (Her seferin kalkış ve varış otogarı vardır.)
10.	Seferler - Rezervasyonlar: 1-N (Bir sefere birden fazla rezervasyon yapılabilir.)
11.	Rezervasyonlar - Ödemeler: 1-1 (Her rezervasyon için bir ödeme yapılır.)
12.	Rezervasyonlar - Bildirimler: 1-N (Bir rezervasyon için birden fazla bildirim yapılabilir.)
13.	Rezervasyonlar - İndirim Kuponları: N-M (Bir rezervasyon birden fazla kuponla yapılabilir.)
14.	Seferler - Geri Bildirimler: 1-N (Bir sefere birden fazla geri bildirim yapılabilir.)
15.	Seferler - Yolculuk Değerlendirmeleri: 1-N (Bir sefere birden fazla değerlendirme yapılabilir.)
16.	Şoförler - Seferler: 1-N (Bir şoför birden fazla sefere çıkabilir.)
17.	Otogarlar - Operatörler: 1-N (Bir otogarda birden fazla operatör çalışabilir.)
18.	Seferler - Bildirimler: N-1 (Bir sefere bağlı bildirimler olabilir.)
19.	Sadakat Programı - Yolcular: 1-1 (Bir yolcu bir sadakat programına sahip olabilir.)
20.	Geçiş Noktaları - Seferler: 1-N (Bir sefer birden fazla şehirden geçebilir.)
21.	Geçiş Noktaları - Şehirler: N-1 (Bir şehirden birden fazla sefer geçebilir.)
22.	Yolcular - Ödemeler: 1-N (Bir yolcu birden fazla ödeme gerçekleştirebilir.)
