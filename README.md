-----

# Leantime®

⭐ Leantime'ı faydalı buluyorsanız, lütfen bizi GitHub'da yıldızlayın\! ⭐

Leantime, proje yöneticisi olmayanlar için açık kaynaklı bir proje yönetim sistemidir. Strateji, planlama ve yürütmeyi bir araya getirirken, ekipteki herkesin kullanmasını kolaylaştırıyoruz. ADHD, disleksi ve otizm düşünülerek tasarlandı. 🧠

💪 Trello kadar basit ama Jira kadar zengin özellikli
🔄 ClickUp, Monday veya Asana'ya mükemmel bir alternatif
🌐 [https://leantime.io](https://leantime.io)

[](https://www.gnu.org/licenses/agpl-3.0.en.html)
[](https://hub.docker.com/r/leantime/leantime)
[](https://discord.gg/4zMzJtAq9z)
[](https://crowdin.com/project/leantime)
\<br /\>

-----

## 🚀 Özellikler\*

| Görev Yönetimi                                         | Proje Planlama                                    | Bilgi/Bilgi Yönetimi                             | Yönetim                                       |
| :----------------------------------------------------- | :------------------------------------------------ | :----------------------------------------------- | :-------------------------------------------- |
| Kanban panoları, gantt, tablo, liste ve takvim görünümleri aracılığıyla görev yönetimi | Proje Panoları, raporlar ve durum güncellemeleri | Wikiler / Belgeler                               | Kolay kurulum                                 |
| Sınırsız alt görev ve bağımlılıklar                   | Hedef ve metrik takibi                            | Fikir Panoları                                   | Çoklu kullanıcı rolleri ve proje bazında izinler |
| Dönüm noktası yönetimi                                 | Lean & İş Modeli Kanvası                          | Retrospektifler                                  | İki faktörlü kimlik doğrulama                  |
| Sprint Yönetimi                                        | SWOT Analizi kanvası                              | S3 veya yerel dosya sistemi aracılığıyla dosya depolama | LDAP, OIDC entegrasyonu                         |
| Zaman takibi ve zaman çizelgeleri                      | Risk Analizi                                      | Ekran ve web kamerası kaydı                      | Eklentiler ve API aracılığıyla genişletilebilir |
|                                                        | ... ve daha fazlası                               | Her şeyde yorumlar/tartışmalar                   | Slack, Mattermost, Discord ile entegre olur   |
|                                                        | ... ve daha fazlası                               |                                                  | 20'den fazla dilde mevcuttur                  |
\*Evet, tüm bu özellikler OSS sürümünde bulunur.

-----

## 📸 Ekran Görüntüleri

| My Work (Koyu Tema) | Proje Panosu | Gruplandırılmış Yapılacaklar |
|---------------------|--------------|------------------------------|
|  |  |  |

| Kanban Panosu | Zaman Çizelgesindeki Görevler | Proje Takvimi |
|---------------|-------------------------------|---------------|
|  |  |  |

| Hedefler | Belgeler & Wikiler | Zaman Çizelgeleri |
|----------|--------------------|-------------------|
|  |  |  |

-----

## ❗ Sistem Gereksinimleri

  * PHP 8.2+
  * MySQL 8.0+ veya MariaDB 10.6+
  * Apache veya Nginx (IIS bazı değişikliklerle çalışır)
  * PHP Uzantıları:
      * BC Math (bcmath)
      * Ctype
      * cURL
      * DOM
      * Exif
      * Fileinfo
      * Filter
      * GD
      * Hash
      * LDAP
      * Multibyte String (mbstring)
      * MySQL
      * OPcache
      * OpenSSL
      * PCNTL
      * PCRE
      * PDO
      * Phar
      * Session
      * Tokenizer
      * Zip
      * SimpleXML

-----

## ⚡️ Kurulum (Üretim)

Leantime'ı üretim için kurmanın iki ana yolu vardır. Birincisi, sistemin tüm gerekli parçalarını yerel olarak kurmaktır. İkincisi ise resmi olarak desteklenen Docker görüntüsünü kullanmaktır.

### Yerel Üretim Kurulumu

  * En son sürüm paketini (dosya adı: Leantime-vx.x.x.zip) [sürüm sayfasından](https://github.com/Leantime/leantime/releases) indirin.
  * Boş bir MySQL veritabanı oluşturun.
  * Tüm dizini sunucunuza yükleyin.
  * Alan adınızın kökünü `public/` dizinine yönlendirin.
  * `config/.env.sample` dosyasının adını `config/.env` olarak değiştirin.
  * Veritabanı kimlik bilgilerinizi (kullanıcı adı, parola, ana bilgisayar, veritabanı adı) `config/.env` dosyasına girin.
  * `<alanadiniz.com>/install` adresine gidin.
  * Veritabanını kurmak ve ilk kullanıcı hesabını oluşturmak için talimatları izleyin.

#### IIS Kurulum Notları

Yukarıdaki adımlar Internet Information Services (IIS) için de geçerli olsa da, tam işlevsellik sağlamak için IIS'de ek bir yapılandırma değişikliği gerekebilir - **PATCH yöntemine izin vermeniz gerekir**:

  * IIS'yi açın.
  * Soldaki sunucuyu ve siteleri genişletin ve Leantime sitesini seçin.
  * `Handler Mappings`'e çift tıklayın.
  * Site tarafından kullanılan PHP işleyici eşleşmesine çift tıklayın.
  * `Request Restrictions…`'a tıklayın.
  * `Verbs` sekmesine tıklayın.
  * `One of the following verbs` metin kutusuna `PATCH` ekleyin - örneğin: `GET,HEAD,POST,PATCH`.
  * `OK` düğmesine tıklayın.
  * `Executable (optional)` metin kutusuna, `php-cgi.exe` dosyasının yolunun başına ve sonuna çift tırnak karakteri (`“`) koyun (yolda boşluk yoksa buna gerek yoktur).
  * `OK` düğmesine tıklayın.
  * Bir açılır pencere FastCGI uygulaması oluşturmak isteyip istemediğinizi soracaktır - `Evet`'e tıklayın.

Not: PHP'yi yükselttiğinizde bunu tekrarlamanız gerekebilir.

### Docker Aracılığıyla Üretim Kurulumu

[Dockerhub'da resmi bir Docker görüntüsü](https://hub.docker.com/r/leantime/leantime) bulundurmaktayız.
Görüntüyü çalıştırmak için MySQL kimlik bilgilerinizi girin ve yürütün. Tüm yapılandırma değişkenlerini .env dosyasından geçirebilirsiniz.

```
docker run -d --restart unless-stopped -p 8080:8080 --network leantime-net \
-e LEAN_DB_HOST=mysql_leantime \
-e LEAN_DB_USER=admin \
-e LEAN_DB_PASSWORD=321.qwerty \
-e LEAN_DB_DATABASE=leantime \
-e LEAN_EMAIL_RETURN=changeme@local.local \
--name leantime leantime/leantime:latest
```

Başka bir yerde tanımlanmış bir veritabanınız yoksa, [docker-compose dosyamızı](https://github.com/Leantime/docker-leantime/blob/master/docker-compose.yml) kullanmalısınız.

Başlatıldıktan sonra `<alanadiniz.com>/install` adresine giderek kurulum betiğini çalıştırabilirsiniz.

**Önemli: Eklentileri kullanmayı planlıyorsanız, `plugins:/var/www/html/app/Plugins` eklenti klasörünü bağlamanız ve www-data kullanıcısının bu klasöre erişebildiğinden emin olmanız gerekir. Aksi takdirde kurulum başarısız olabilir veya eklentiler yeniden başlatıldıktan sonra kaldırılabilir.**

#### Docker Kurulum Notları

Leantime'ı özel alan adı çözünürlüğü ve SSL boşaltmayı ele almak için bir ters proxy'nin (nginx vb.) arkasına yerleştirmeyi düşünüyorsanız, docker'da aşağıdaki ortam değişkenini ayarlamanız gerekecektir:

```
-e LEAN_APP_URL=https://alanadiniz.com \
```

  * `alanadiniz.com` adresini kendi özel alan adınızla güncelleyin.

-----

## 🤓 Kurulum (Geliştirme)

LeanTime'ın bir geliştirme kurulumunu yapmanın iki yolu vardır. Birincisi (ancak en teknik olanı) sistemin tüm parçalarını yerel olarak kurmaktır. İkincisi (ve tercih edilen yöntem) bir docker kapsayıcılı geliştirme ortamı kullanmaktır.

### Yerel Geliştirme Kurulumu

  * Depoyu yerel sunucunuza klonlayın.
  * MySQL veritabanı oluşturun.
  * `make build-dev` komutunu kullanarak webpack oluşturucuyu çalıştırın.
  * Yerel alan adınızı `public/` dizinine yönlendirin.
  * `config/.env.sample` dosyasının adını `config/.env` olarak değiştirin.
  * Veritabanı kimlik bilgilerinizi (kullanıcı adı, parola, ana bilgisayar, veritabanı adı) `config/.env` dosyasına girin.
  * `<yerelalanadi>/install` adresine gidin.
  * Veritabanını ve kullanıcı hesabını kurmak için talimatları izleyin.

### Docker Aracılığıyla Geliştirme Kurulumu

Geliştirme için, dockerize edilmiş bir geliştirme ortamı kullanıyoruz. `docker`, `docker compose`, `make`, `composer`, `git` ve `npm` yüklü olmalıdır.

  * Windows Ortamları için Notlar:
      * Unix'e özgü komutları kullanmak için tüm komutları git bash terminalinde çalıştırın.
      * Php'yi bir zip dosyasından yüklüyorsanız, php.ini'yi yapılandırdığınızdan emin olun.
      * Başlangıçta mevcut değildir, bu yüzden `C:\php\php.ini-development` dosyasını `C:\php\php.ini` olarak kopyalayın. Ayrıca bir metin düzenleyicide php.ini'yi düzenlemeniz ve derleme süreci için gerekli tüm uzantıları etkinleştirmeniz gerekecektir. Bunları make komutlarını çalıştırarak ve eksik uzantılar olarak hata veren uzantıları arayarak bulabilirsiniz. Bunları, `php.ini` dosyasında `;extension=gd` gibi görünen uzantıyı arayarak ve noktalı virgülü kaldırarak etkinleştirebilirsiniz.

Geliştirme docker görüntüsünü oluşturmak için, bu deponun kök dizininde, bir ön hazırlık komutu çalıştırın:

`make clean build`

ardından, şunu çalıştırın:

`make run-dev`

Bu, geliştirme sunucusunu 8090 numaralı bağlantı noktasında başlatacaktır.

Geliştirme ortamı bir MySQL sunucusu, posta sunucusu, s3 sunucusu sağlar ve kutudan çıktığı gibi ihtiyaçlarınız için iyi olmalıdır. Geliştirme ortamının yapılandırması `.dev/.env` dosyasında bulunur ve uygun değerlerle zaten önceden doldurulmuştur. **Özel bir entegrasyon üzerinde çalışmayı planlamıyorsanız muhtemelen bunu değiştirmemelisiniz.** alacağınız uygulamalar şunlardır:

  * [http://localhost:8090](https://www.google.com/search?q=http://localhost:8090) : leantime
  * [http://localhost:8081](https://www.google.com/search?q=http://localhost:8081) : maildev - gönderilen e-postaları kontrol etmek için
  * [http://localhost:8082](https://www.google.com/search?q=http://localhost:8082) : phpMyAdmin (kimlik doğrulama `leantime:leantime`) - DB şemasını ve verilerini kontrol etmek için
  * [http://localhost:8083](https://www.google.com/search?q=http://localhost:8083) : s3ninja - s3 yüklemelerini kontrol etmek için. Bunu `.dev/.env` dosyasında s3'ü etkinleştirerek etkinleştirmeniz gerekir.

Ek olarak, Xdebug etkinleştirilmiştir, ancak IDE anahtarınızı `.dev/xdebug.ini` dosyasında (veya alternatif olarak IDE'nizde) değiştirmeniz gerekecektir. Ayrıca, güvenlik duvarınızda 9003 numaralı bağlantı noktasını geçici olarak açmanız gerekir, böylece etkili bir şekilde kullanabilirsiniz. Bunun nedeni, docker'dan ana bilgisayara yapılan bağlantıların harici gelen bağlantılar olarak sayılmasıdır.

-----

### Testleri Çalıştır

Statik Analiz `make phpstan`
Kod Stili `make test-code-style` (kod stilini otomatik olarak düzeltmek için `make fix-code-style` kullanın)
Birim Testleri `make unit-test`
Kabul Testleri `make acceptance-test` (docker gerektirir)

Bireysel kabul testi gruplarını doğrudan kullanarak test edebilirsiniz:
API için:
`docker compose --file .dev/docker-compose.yaml --file .dev/docker-compose.tests.yaml exec leantime-dev php vendor/bin/codecept run -g api --steps`
Zaman çizelgeleri için:
`docker compose --file .dev/docker-compose.yaml --file .dev/docker-compose.tests.yaml exec leantime-dev php vendor/bin/codecept run -g timesheet --steps`

-----

### 🏗 Güncelleme

#### Manuel

  * Veritabanınızın ve dosyalarınızın yedeğini aldığınızdan emin olun.
  * Dizinizi güncellenmiş sürümle değiştirin.
  * Veritabanı değişiklikleri varsa, sistem sizi `<alanadiniz.com>/update` adresine yönlendirecektir.

#### CLI

  * `php bin/leantime system:update` komutunu çalıştırın.

#### Docker

  * Güncellemeden önce, mysql kapsayıcınızın bağlı bir birim kullanılarak başlatıldığından emin olun, aksi takdirde içeriğiniz silinir.
  * Mevcut kapsayıcıyı silin/durdurun.
  * En son docker görüntüsünü çekin ve compose dosyanızı kullanarak yeniden oluşturun.

-----

### Yaygın Sorunlar

Leantime'ı kurarken veya güncellerken karşılaşılan yaygın sorunlar hakkında [belgelerimize](https://docs.leantime.io/installation/common-issues) başvurabilirsiniz.

-----

## 🔌 Leantime'ı Genişletin

Leantime'ı şu yollarla genişletebilirsiniz:

  * Kendi eklentinizi oluşturma: [Eklenti Belgeleri](https://docs.leantime.io/development/plugin-development)
  * json-rpc API'mizi kullanma: [API Belgeleri](https://docs.leantime.io/api/usage)
  * Veya [pazar yerimizden](https://marketplace.leantime.io) bir eklenti satın alarak.

-----

## 🛟 Sizin İçin Kurmamıza İzin Verin.

Ortamlarınızda sorunsuz kurulum hizmeti. Tam kurulumlar, güncellemeler, yapılandırmalar veya eklenti kurulumları yapabiliriz. Ayrıntılar için [Pazar Yerimize](https://marketplace.leantime.io/product-category/services/technical/) bakın.

-----

## ☁️ Kendiniz barındırmakla ilgilenmiyor musunuz? Sizin için yapalım

[Yönetilen barındırma planları](https://leantime.io/managed-hosting/) ve bir [SaaS ürünü](https://leantime.io/pricing/) sunuyoruz, böylece Leantime'ın tüm avantajlarından zahmetsizce yararlanabilirsiniz.
Daha fazla bilgi için [leantime.io](https://leantime.io/) adresine gidin.

-----

## 🤙 Teknik desteğe mi ihtiyacınız var?

Leantime'ı ortamınızda kurmanıza ve ihtiyaçlarınıza göre özelleştirmenize yardımcı olabiliriz. Destek planlarımız [web sitemizde](https://leantime.io/priority-support/) belirtilmiştir.

Lütfen dikkat: Şu anda yalnızca resmi Leantime docker compose ve standart kurulumları destekliyoruz.
Yalnızca en son sürüm için destek sunuyoruz.

Cloudron, Elestio, Turnkey veya Leantime'ın resmi olmayan sürümlerini paylaşan diğer harici dağıtım platformları için destek sunmuyoruz.

-----

## 🫴 Katkıda Bulunma

Leantime'a katkıda bulunmakla ilgilenmenize heyecan duyuyoruz. Leantime'a katkıda bulunurken harika bir deneyim yaşamanızı ve oluşturduğunuz yeni özelliklerin çekirdeğe dahil olmasını sağlamak istiyoruz.

### 🪲 Hatalar

Github'da bir sorun bulun (veya yeni bir tane oluşturun), adınızı ekleyin veya üzerinde çalışacağınızı belirtin. Düzeltildikten sonra bir Çekme İsteği oluşturun.

### Çekirdekteki Yeni Özellikler

Yeni özellikler hakkında bir fikriniz varsa lütfen Discord'dan bize ulaşın. Burası, özellik geliştirme koordinasyonunu yaptığımız ve yeni özelliklerinizi eklemek için çekirdeğin doğru yer olup olmadığını tartıştığımız yerdir (Eklentiler alternatifidir).

### 🌏 Çeviriler

Dil dosyaları ve çeviriler `app/Language/*` içinde saklanır. Güncellemelerden sonra lütfen bir Çekme İsteği oluşturun.

### 👥 Topluluk Desteği

  * Belgeler [https://docs.leantime.io](https://docs.leantime.io)
  * Topluluk Sohbeti [Discord](https://discord.gg/4zMzJtAq9z)
  * Hata raporu oluşturun [https://github.com/Leantime/leantime/issues/new](https://github.com/Leantime/leantime/issues/new)
  * Çeviriler [https://crowdin.com/project/leantime](https://crowdin.com/project/leantime)

-----

## ⚖️ LİSANS İstisnaları

Leantime, AGPLv3 lisansı altındadır.
Bu dosya, aşağıdaki istisnanın eklendiği Leantime Yazılımının bir parçasını oluşturur: `/app/Plugins` dizini içindeki eklentiler, kurumsal lisansımız da dahil olmak üzere diğer lisanslar altında lisanslanmış eklentiler içerebilir.

-----
