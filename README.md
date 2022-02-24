# IDS-based-on-machine-learning

Makine Öğrenmesi Teknikleri ile Saldırı Tespiti
Linda Türkmen
Makine Öğrenmesi Teknikleriyle Saldırı Tespiti: Saldırı Tespit Sistemleri; İlk saldırı tespit sistemi konsepti Anderson tarafından 1980 yılında önerilmişti. saldırı tespit sisteminin görevini, bilgisayar sisteminde ya da ağ sisteminde gerçekleşen tüm olayları denetlemek ve kontrol etmek, güvenlik sorunları ortaya çıktığında ilgili personel ve birimleri uyarmak için alarm göndermek ve olası riskleri azaltmak için gerekli tedbirleri almak şeklinde tanımlamıştır. Saldırı tespit sisteminin çalışma döngüsünü bilgi toplama, analiz motoru ve cevap olarak üç başlık altında incelemiştir [1] .

Ağ üzerinden yapılabilecek saldırılar aşağıdaki gibi sıralanabilir:

1) Hizmet engelleme (Denial of Service-DOS)

2) Yönetici hesabını ele geçirerek yerel ağda oturum açma (Remote to Local-R2L)

3) Kullanıcı hesabını yönetici hesabına yükseltme (User to Root-U2R)

4) (Probe): Saldırganın, kaynak üzerinde çalışan hizmetleri tanımlamak için kullanılabilecek açık bağlantı noktaları gibi güvenlik açıkları için bir ağı araştırdığı bir saldırı sınıfıdır. Genellikle, tanımlanmış bir güvenlik açığı aracılığıyla beklemeyen bir ana bilgisayara ayrıcalıklı erişim elde ederler.

Yapay zekânın bir alt dalı olan makine öğrenmesini ile saldırı tesip sistemi tasarlanacaktır. Makine öğrenimi algoritmaları, insan müdahalesi olmadan verilerden öğrenebilen ve deneyimler ile geliştirebilen programlardır. Makine öğrenimi algoritmaları denetimli öğrenme ve denetimsiz öğrenme olarak kategorize edilir. Sınıflandırma problemlerinde başarılı bir şekilde kullanılmaktadır. Literatürde, saldırı tespit sistemlerinde sıklıkla kullanılan makine öğrenme teknikleri aşağıdaki gibidir. -Bayes sınıflama -Destek vektör makinesi -Karar ağaçları -Yapay sinir ağları -Lojistik Regresyon

Dataset olarak KDD Cup 1999 kullanılmıştır.

Eldeki probleme en uygun tekniklerin seçilmesi, yeterli sayıdaki tekniklerin denenmesi ile mümkün olabilmektedir. Bu nedenle veri önişleme ve model kurma aşamaları, en iyi sonucu veren tekniğe ulaşıncaya kadar tekrarlayan bir süreçtir. Problemin başarımla yapılabilmesi için problemimize uygun çözüm olarak sınıflandırma modelleri kullanılmıştır. Dolaysıyla bizim problemimiz özelinde Denetimli öğrenme modelleri ile uygun çözüm gerçekleştirilmiştir. Denetimli öğrenmede seçilen tekniğe uygun hazırlanan verilerin, ilk aşamada bir kısmı modelin öğrenimi, diğer kısmı ise modelin performansının test edilmesi için ayrılmaktadır. Modelin eğitilmesi, eğitim verisi üzerinde uygulandıktan sonra, test verisi ile modelin doğruluk oranı belirlenmektedir. Model kuruluşu çalışmalarının sonucuna bağlı olarak, aynı teknikle farklı parametrelerin kullanıldığı veya başka algoritma ve araçların denendiği değişik modeller kurulabilmektedir. Bu sebeple projemizde accuracy ve diğer metriklerin daha iyi yorumlanabilmesi ve yüksek değerlerin elde edilmesi için farklı makine öğrenmesi modelleri de kullanılmıştır. Bunları kısaca açıklamak gerekirse:

5 Farklı İnceleme Adımları:
Beş farklı şekilde dataset üzerinde analizler yapıldı.

1) Başlangıç olarak DOS, U2R, R2L ve Probe'ı karegorilerin kendi içinde attack sınıfları mevcut. Her bir kategorinin attack sınıslarını ayırdım ve toplamda 5 tane ayrı dataset oluşturmuş oldum. Her bir kategoriyi kendi içinde sınıflandırdım. Örneğin DOS datasetinde [smurf, neptune, back, pod, teardrop] attack sınıfları mevcut. Bunrada DOS datasetinde sınıflandırmaya çalışrığım attack tipleri. Bu işlem diğer tüm kategoryler için de gerçekleştirildi. Heri bir dataset için eğitim ve test adımlarını gerçekleşitrdim. Daha kolay yorumlayabilmek adına Confusion Matrisini ve diğer metricleri hesapladım. Sonuçları daha rahat bir şekilde görebilmek için tablo ile ifade ettim.

2) Bu aşamada 2 sınıf ile çalıştım. normal ve anormal şeklinde. [label] sütununda bulunun normal dışındaki tüm sınıfları(attacks) anormal olarak isimlendirildi, sınıflandırma iki sınıf üzerinde yapıldı. Eğitim ve test aşmasında sonra önceki bölümde olduğu gibi Confusion Matrisi ve diğer metricler hesaplandı.

3) Datasetini olduğu gibi sınıflandırma. Totalde [label] sütununda 23 tane sınıf mevcut. Buradaki amacım herhangi bir gruplama yapılmadan datasetin saf hali alınarak, çoklu sınıf ayrıştırmasında modelimizin sonucunu gözlemlemek ve accuracy değerinde herhangi bir değişim oranı olup olmadığını öğrenmek.

4) Dataset içinde kategorik feature/sütun sayısı 3, bunlar ["service_num", "protocol_type", "flag_num"]. Bundan önceki eğtimlerde bu sütunları dahil edilmedi. Bu aşamada bu sütunlar nümerik değerlere dönüştürüldü ve featurer olarak sadece bu 3 sütun kullanılarak sınıflandırma yapıldı.

5) Son olarak ise veri setini genel kategorilere göre sınıflandırıldı ve toplamda 5 sınıfım oldu. [normal, dos, u2r, r2l, probe] sınıfları. Buradaki amacım kategoriye göre nasil başar sergileyeceğinin gözlemlemek.
