# Todo Uygulaması

Bu, Vue.js, Laravel, MySQL ve TailwindCSS kullanılarak geliştirilmiş basit ve duyarlı bir Todo uygulamasıdır. Uygulama, kullanıcıların görevler eklemesine, düzenlemesine, silmesine ve tamamlandı olarak işaretlemesine olanak tanır. Tasarım tamamen duyarlıdır ve hem masaüstü hem de mobil cihazlarda iyi çalışır.

## Özellikler

- Todo ekleme, güncelleme, silme ve tamamlama.
- Masaüstü ve mobil cihazlar için duyarlı tasarım.
- Görevlerin satır içi düzenlenmesi.
- Görev durumu gerçek zamanlı olarak güncellenir.
- Moment.js kullanılarak tarih formatlama.

## Kullanılan Teknolojiler

- **Frontend:** Vue.js, TailwindCSS
- **Backend:** Laravel
- **Veritabanı:** MySQL
- **Stil:** TailwindCSS
- **Tarih Formatlama:** Moment.js

## Gereksinimler

Başlamadan önce, aşağıdaki araçların yüklü olduğundan emin olun:

- [Node.js](https://nodejs.org/) (v12 veya üstü)
- [npm](https://www.npmjs.com/get-npm) veya [Yarn](https://yarnpkg.com/)
- [Composer](https://getcomposer.org/)
- [MySQL](https://www.mysql.com/)
- [PHP](https://www.php.net/) (v8.0 veya üstü)
- [Laravel](https://laravel.com/)
- Geliştirme sunucusu için [XAMPP](https://www.apachefriends.org/tr/index.html) veya [MAMP](https://www.mamp.info/en/downloads/)

### XAMPP veya MAMP Kurulumu

- **XAMPP:** [Apache Friends](https://www.apachefriends.org/index.html) sitesinden XAMPP'ı indirip kurun. XAMPP, yerel geliştirme ortamı için gerekli olan Apache ve MySQL sunucularını içerir. Kurulumdan sonra XAMPP Kontrol Paneli üzerinden Apache ve MySQL servislerini başlatın.
  
- **MAMP:** [MAMP Resmi Sitesi](https://www.mamp.info/en/downloads/) üzerinden MAMP'ı indirip kurun. MAMP, Mac kullanıcıları için ideal bir geliştirme ortamı sağlar. MAMP'i kurduktan sonra uygulamayı başlatın ve `Start Servers` butonuna tıklayarak Apache ve MySQL sunucularını çalıştırın.

## Kurulum

Uygulamayı yerel makinenizde kurmak ve çalıştırmak için aşağıdaki adımları izleyin:

### 1. Depoyu Klonlayın

```bash
git clone https://github.com/veyselsokel/todo-app.git
cd todo-app
```

### 2. Backend Bağımlılıklarını Yükleyin

Laravel bağımlılıklarını yüklemek için Composer'ı kullanın:

```bash
composer install
```

### 3. Frontend Bağımlılıklarını Yükleyin

Vue.js bağımlılıklarını yüklemek için npm veya Yarn'ı kullanın:

```bash
npm install
# veya
yarn install
```

### 4. Ortam Değişkenlerini Ayarlayın

`.env.example` dosyasını `.env` olarak kopyalayın ve yerel kurulumunuza uygun ortam değişkenlerini güncelleyin:

```bash
cp .env.example .env
```

`.env` dosyasındaki veritabanı bilgilerinizi güncelleyin:

```
DB_DATABASE=veritabanı_adınız
DB_USERNAME=veritabanı_kullanıcı_adınız
DB_PASSWORD=veritabanı_parolanız
```

### 5. Uygulama Anahtarını Oluşturun

```bash
php artisan key:generate
```

### 6. Veritabanı Migrasyonlarını Çalıştırın

Veritabanı tablolarını ayarlamak için aşağıdaki komutu çalıştırın:

```bash
php artisan migrate
```

### 7. Frontend Varlıklarını Derleyin

Frontend varlıklarını derlemek için aşağıdaki komutu kullanın:

```bash
npm run dev
# prod için
npm run build
```

### 8. Uygulamayı Çalıştırın

Laravel geliştirme sunucusunu başlatın:

```bash
php artisan serve
```

Uygulamaya erişmek için tarayıcınızda `http://127.0.0.1:8000/` adresine gidin.

## Kullanım

### Todo Ekleme

- Görev adını giriş alanına yazın ve "Ekle" butonuna tıklayın.
- Görev listeye bir onay kutusu (checkbox), bir "Düzenle" butonu ve bir "Sil" butonu ile birlikte eklenir.

### Todo Düzenleme

- Bir görevi düzenlemek için "Düzenle" butonuna tıklayın.
- Görev başlığını düzenleyin ve değişiklikleri kaydetmek için "Kaydet" butonuna tıklayın. Kaydetmekten vazgeçerseniz "İptal" butonuna tıklayın.

### Todo Silme

- Bir görevi listeden kaldırmak için "Sil" butonuna tıklayın.

### Todo Tamamlama

- Bir görevi tamamlamak için görevin yanındaki onay kutusuna tıklayın.
- Görev başlığı üzeri çizili hale gelir ve tamamlandığını gösterir.

## Lisans

Bu proje MIT Lisansı altında lisanslanmıştır. Ayrıntılar için [LICENSE](LICENSE) dosyasına bakın.

## Katkıda Bulunma

Bu depoyu forklayıp, pull request göndererek katkıda bulunabilirsiniz.