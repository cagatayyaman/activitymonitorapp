# ActivityMonitorApp ve UserNameSetup

Bu projede, kullanıcıların fare ve klavye etkinliklerini izleyen ve hareketsiz kaldıkları süreleri kaydeden bir Windows Forms uygulaması olan **ActivityMonitorApp** ve bu uygulama için kullanıcı adını belirlemek için kullanılan **UserNameSetup** konsol uygulaması bulunmaktadır.

## UserNameSetup

**UserNameSetup**, kullanıcının adını belirlemek ve bu adı `ActivityMonitorApp` uygulaması tarafından kullanılmak üzere kaydetmek için kullanılan bir konsol uygulamasıdır.

### Özellikler

- Kullanıcı adını girme ve kaydetme

### Kurulum ve Kullanım

1. **Projeyi Klonlayın:**
   ```bash
   git clone https://github.com/cagatayyaman/activitymonitorapp.git

  2 .	Proje Dosyasını Açın:
Visual Studio Community veya Visual Studio Code ile projeyi açın.
	3.	Proje Ayarlarını Yapın:
Program.cs dosyasını açın ve aşağıdaki gibi olmalıdır:

using System;
using System.IO;

namespace UserNameSetup
{
    class Program
    {
        static void Main(string[] args)
        {
            string userFilePath = @"C:\ActivityMonitor\username.txt";
            Directory.CreateDirectory(@"C:\ActivityMonitor");

            Console.WriteLine("Kullanıcı adını girin:");
            string userName = Console.ReadLine();
            File.WriteAllText(userFilePath, userName);

            Console.WriteLine("Kullanıcı adı kaydedildi.");
        }
    }
}


4.	Projeyi Derleyin ve Çalıştırın:
	•	Build > Build Solution menüsünden projeyi derleyin.
	•	Debug > Start Without Debugging (Ctrl + F5) menüsünden uygulamayı çalıştırın.
	•	Konsol penceresinde kullanıcı adını girin ve Enter’a basın. Kullanıcı adı belirtilen dosya yoluna kaydedilecektir.

ActivityMonitorApp

ActivityMonitorApp, fare ve klavye etkinliklerini izleyen ve kullanıcı belirli bir süre (3 dakika) hareketsiz kaldığında bu süreleri kaydeden bir Windows Forms uygulamasıdır. Ayrıca, her gün saat 17:00’da belirlenen e-posta adreslerine günlük rapor gönderir.

Özellikler

	•	Fare ve klavye etkinliklerini izleme
	•	3 dakika hareketsiz kalındığında süreleri kaydetme
	•	Günlük raporları e-posta ile gönderme
	•	Uygulama başlatıldığında deneme e-postası gönderme
	•	Sistem tepsisinde (görev çubuğu) simge olarak çalışma

Kurulum ve Kullanım

	1.	Projeyi Klonlayın:
 	2.	Proje Dosyasını Açın:
Visual Studio Community veya Visual Studio Code ile projeyi açın.
	3.	Gerekli Bağımlılıkları Yükleyin:
Microsoft.VisualBasic paketini NuGet üzerinden yükleyin.
	4.	Proje Ayarlarını Yapın:
Form1.cs dosyasındaki SMTP ayarlarını kendi e-posta sunucunuza göre güncelleyin:
 SmtpClient client = new SmtpClient("mail.smtpsunucunuz.com");
client.Port = 587;
client.Credentials = new NetworkCredential("eposta@adresiniz.com", "sifreniz");
client.EnableSsl = false; // SSL kullanıyorsanız true yapın

5.	ActivityMonitorApp Windows Forms Uygulamasını Çalıştırın:
	•	Build > Build Solution menüsünden projeyi derleyin.
	•	Debug > Start Without Debugging (Ctrl + F5) menüsünden uygulamayı çalıştırın.

Kullanım

	•	UserNameSetup konsol uygulamasını çalıştırarak kullanıcı adını girin.
	•	ActivityMonitorApp uygulamasını çalıştırın. Uygulama başlatıldığında, sistem tepsisinde bir simge olarak çalışmaya devam eder.
	•	Kullanıcı 3 dakika boyunca hareketsiz kaldığında, bu süre kaydedilir.
	•	Her gün saat 17:00’da günlük rapor belirlenen e-posta adreslerine gönderilir.
	•	Uygulama ilk başlatıldığında bir deneme e-postası gönderir.

Katkıda Bulunma

Katkıda bulunmak isterseniz, lütfen bir issue açın veya bir pull request gönderin.

Lisans

Bu proje MIT Lisansı ile lisanslanmıştır. Daha fazla bilgi için LICENSE dosyasına bakın.

Her iki uygulamada da .exe olan uzantıları çalıştırmanız yeterlidir. Önce UserNameSetup.exe çalıştırıız. Sizden bir kullanıcı adı yazmanızı isteyecek. Kullanı adı sizin ilgili kişiyi raparlarken tanımlayacağınız isim olacak. Daha sonra ise ActivityMonitorApp.exe çalıştırınız. 
