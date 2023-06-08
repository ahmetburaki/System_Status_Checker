Sistem Durumu Kontrolcüsü
Bu Go kodu, sistem durumunu düzenli aralıklarla kontrol eden ve sistem uptime, yük ortalama, disk kullanımı, bellek kullanımı ve ağ durumu gibi çeşitli metrikleri rapor eden basit bir sistem durumu kontrolcüsü sağlar. Sürekli bir işlem olarak çalışır ve sistem hakkında gerçek zamanlı bilgi sağlar.

Önkoşullar
Bu kodu çalıştırmadan önce sisteminizde Go'nun kurulu olduğundan emin olun. Go'yu resmi Go web sitesinden (https://golang.org) indirip kurabilirsiniz.

Kullanım
Depoyu klonlayın veya yeni bir Go projesi oluşturun.
Yeni bir Go dosyası oluşturun (örneğin, main.go) ve kodu içine kopyalayın.
Bir terminal veya komut istemi açın ve proje dizinine gidin.
Aşağıdaki komutu kullanarak kodu çalıştırın:
go
Copy code
go run main.go
Sistem durumu kontrolcüsü çalışmaya başlayacak ve sistem durumu raporunu her 5 dakikada bir görüntüleyecektir.

Nasıl Çalışır
Kod, Go'nun yerleşik time paketini kullanarak sistem durumu kontrollerini her 5 dakikada bir planlar. checkSystemStatus işlevini düzenli aralıklarla tetikleyen bir sayaç (ticker) oluşturur. checkSystemStatus işlevi, farklı sistem metriklerini toplamak ve görüntülemek için çeşitli yardımcı işlevleri çağırır.

Program ayrıca bir sonlandırma sinyalini (örneğin, CTRL+C) bekleyerek programı düzgün bir şekilde durdurur. Sonlandırma sinyali alındığında, sayaç (ticker) durdurulur ve program sonlandırılır.

İşlevler
main
main işlevi programın giriş noktasıdır. Sistem durumu kontrollerini planlamak için bir sayaç (ticker) oluşturur, kontrolleri gerçekleştirmek için bir gorutini başlatır ve sonlandırma sinyalini bekler.

checkSystemStatus
checkSystemStatus işlevi, sistem durumunu toplamak ve görüntülemekten sorumludur. Farklı metrikleri almak ve sonuçları konsola yazdırmak için çeşitli yardımcı işlevleri çağırır.

checkUptime
checkUptime işlevi, sistem uptime'ini almak için uptime komutunu kullanır ve sonucu konsola yazar.

checkLoadAverage
checkLoadAverage işlevi, /proc/loadavg dosyasından yük ortalamasını okur ve sonucu konsola yazar.

checkDiskUsage
checkDiskUsage işlevi, belirtilen bir yol için disk kullanımını kontrol
