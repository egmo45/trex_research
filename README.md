 ## 1. Modern Yazılım Geliştirme Pratikleri

<details>
<summary><strong>🗃 Git nedir? GitHub nedir?</strong></summary>
<br>

### 🔹 Git
- Git, yazılım geliştirme sürecinde kullanılan **dağıtık bir versiyon kontrol sistemidir**.  
- Bir projede yapılan değişikliklerin geçmişini kayıt altına alır, farklı sürümleri saklar ve aynı projede çalışan kişilerin kodlarını düzenli bir şekilde birleştirmesine yardımcı olur.  
- İstenildiğinde eski sürümlere geri dönmek mümkündür, bu da geliştirme sürecinde büyük esneklik sağlar.  
---
### 🔻 GitHub
- GitHub, Git sistemini temel alan **bulut tabanlı bir platformdur**.  
- Geliştiriciler, projelerini internet üzerinde depolayabilir, paylaşabilir ve ekip arkadaşlarıyla iş birliği yapabilir.  
- Sadece kod depolamakla kalmaz; aynı zamanda görev takibi, hata raporlama ve proje yönetimi gibi araçlar da sunar.  
---
 **Detaylar:**  
- Git altyapıyı sağlar.  
- GitHub ise bu altyapıyı kullanıcı dostu bir ortamda sunarak yazılımcıların işini kolaylaştırır.  

<br>

</details>

<details> 

<summary><strong>📂 Temel Git komutları: init, clone, add, commit, push, pull, branch, merge..</strong></summary>
<br>

**1. Git İnit.**

###  Ne işe yarar?
- Yeni bir **Git deposu (repository)** oluşturur.  
- Yani bulunduğunuz klasörü **Git tarafından takip edilen bir proje** haline getirir. 

**Detaylar:**
-Komutu çalıştırdığında klasör içinde .git adında gizli bir klasör oluşturulur.
- Bu klasör, değişiklik geçmişini ve versiyonları saklar. 

---


###  Nerede Kullanılır?
-  git **init** aslında komut satırında (terminalde/komut isteminde) kullanılan bir komuttur. “Make Directory” kısaltmasıdır ve yeni klasör (dizin) oluşturmak için kullanılır.

 Windows’ta:

- cmd (Komut İstemi) veya PowerShell açıp yazılabilir.

Linux / MacOS’ta:

- Terminal açıp yazılabilir.



###  Detaylar:
- Bu komutu yazınca klasörün içinde **`.git`** adlı gizli bir klasör oluşur.  
- Bu klasör, tüm **geçmişi** ve **versiyonları** saklar.  

---

### 🟠 Örnek:
``` 
mkdir proje       # Yeni klasör oluştur
cd proje          # Klasöre gir
git init          # Git deposu başlat
```

**2. Git Clone**

 **Ne işe yarar?**
- Uzak bir depoyu (örneğin GitHub’daki proje) bilgisayarına indirir.
- Örneğin GitHub’daki bir projeyi bilgisayarına indirir. Böylece projeyi yerel ortamınızda inceleyebilir, geliştirebilir ve değişiklikler yapabilirsiniz.



**Detaylar:**
- Başkasının projesini geliştirmek ya da incelemek istediğinde kullanılır. Kişisel bilgisayarınızda bir kopyası olur.
- Yerel depo (local repository) = Sizin bilgisayarınızda oluşturulan proje kopyası 
- git clone, bu iki depoyu bağlar ve tüm dosyaları, commit geçmişini indirir.

---

 
###  🟠 Örnek: 
``` 
git clone https://github.com/kullanici/proje.git

- Bu komut, GitHub’daki proje adlı depoyu bilgisayarına indirir.
- İndirilen proje, kendi klasöründe aynı dizin yapısını ve tüm geçmiş commit’leri barındırır.
```
---

**3. Git Add**

### Ne işe yarar?

- Dosyaları staging area’ya ekler. Commit öncesi hangi dosyaların kaydedileceğini belirler.
- Git, dosyaları otomatik commit etmez; önce add ile hazırlamak gerekir.



**Detaylar:**
- Git, dosyaları otomatik commit etmez; önce add ile hazırlamak gerekir.
- Önce git add ile hangi değişikliklerin commit’e dahil olacağını belirlemelisiniz Bu sayede sadece istediğin dosyaları kaydedebilirsiniz.



###  🟠 Örnek: 
```
git add dosya.txt      # Sadece dosya.txt dosyasını ekler
git add .              # Tüm değişiklikleri ekler
git add *.js           # Tüm .js dosyalarını ekler
```

**4. Git Commit**

### Ne işe yarar? 

- Git commit, staging area’ya eklediğin dosyaları kalıcı olarak Git geçmişine kaydeder. Yani değişikliklerin bir “fotoğrafını” alır ve bu fotoğrafı mesaj ile açıklar.
- Commit mesajları kısa, açıklayıcı ve net olmalı. Örneğin "düzeltmeler" yerine "Kullanıcı giriş hatası düzeltildi" gibi mesajlar daha faydalıdır.

**Detaylar:** 

- Commit mesajı, değişikliğin ne yaptığını açıklamak için önemlidir git commit komutu, staging area’ya (git add ile eklediğin) dosyaları yerel Git deposuna kaydeder.
- Commit yaptıktan sonra, değişiklik geçmişini görmek ve istenirse eski sürümlere dönmek mümkün olur.


###  🟠 Örnek: 
```

git add index.html          # Dosyayı commit için hazırla
git commit -m "Ana sayfa eklendi"   # Değişiklikleri kaydet
```

---

**5. Git Push**

### Ne işe yarar? 

- Git commit komutu, staging area’ya (git add ile eklediğiniz) dosyaları yerel Git deposuna kaydeder.
- Yani bilgisayarındaki değişiklikler artık ekip arkadaşların veya internetten erişen herkes tarafından görülebilir.

**Detaylar:**  

- Yerel değişiklikleri commit ettikten sonra push yapabilirsiniz.
- Eğer uzak depoda yeni değişiklikler varsa, önce git pull ile güncelleme alman gerekebilir.
- Push yaparken hangi branch’e göndereceğini belirtmelisin. origin → uzak depo (remote) adı main → hangi branch’e göndereceğiniz

###  🟠 Örnek: 
```
git push origin main #Göndereceğin yer
```

---

**6. Git Pull**

### Ne işe yarar? 

- Git pull, uzak (remote) repodaki en son değişiklikleri indirir ve senin yerel projenle birleştirir.
- Yani başkaları GitHub’a yeni commit gönderdiğinde, senin bilgisayarına da bu değişiklikler gelsin diye kullanılır.

**Detaylar:**

- Git pull, aslında iki işlemi birden yapar:
- Git fetch → Uzak depodaki değişiklikleri indirir.
- Git merge → Bu değişiklikleri senin bulunduğun branch ile birleştirir.

###  🟠 Örnek: 
```
git pull origin main #Göndereceğin yer
```
---

**7. Git Branch**

### Ne işe yarar? 

- Git branch, Git projesinde farklı çalışma alanları (branch/şube) oluşturmanızı sağlar.
- Her branch, projeni ayrı bir yolda geliştirmene imkân verir.

**Detaylar:**

- Ana branch genelde main veya master olur.
- Farklı kişiler farklı branch’lerde çalışıp sonra bunları merge ile birleştirebilir. Ana projeyi bozmadan yeni özellikler geliştirebilirsiniz

###  🟠 Örnek: 
```
git branch #Branch’leri listele:
git branch yeni-ozellik #Yeni branch oluştur:
git checkout yeni-ozellik #Branch’e geçiş yap:
git checkout -b yeni-ozellik #Tek komutla branch oluşturup geçiş yap:
git push origin yeni-ozellik #Branch’i uzak depoya gönder:

```
---

**8. Git Merge**

- Git merge, iki farklı branch’i birleştirmek için kullanılır. siz main branch’indesiniz. Karşı bilgisayar login-sistemi branch’inde çalışıyor. Onun yaptığı değişiklikleri ana projeye katmak için git merge yaparsınız.

**Detaylar:**

- Bir branch’te değişiklik yapılır.
- Başka branch’e geçilir.
- Git merge <branch-adı> yazılarak bu değişiklikler mevcut branch’e aktarılır.

###  🟠 Örnek: 
```
git branch
* main
  login-sistemi
git checkout main

```

</details> 

<details>
<summary><strong> Merge conflict nedir, nasıl çözülür?</strong></summary>
<br>

### Merge Conflict nedir?

- Merge conflict, iki farklı branch (şube) üzerinde aynı dosyanın aynı satırlarında farklı değişiklikler yapıldığında ortaya çıkar.

- Git, hangi değişikliğin doğru olduğunu kendi başına karar veremez. Bu durumda “çatışma” (conflict) oluşur.

### Merge Conflict neden olur?

- Aynı dosyanın aynı satırları iki branch’te farklı şekilde değiştirilmiş

- Bir branch’te bir dosya silinmiş, diğer branch’te değiştirilmiş.

- Büyük ve uzun süreli değişiklikler yapılmış, branch’ler güncel değil.

- Örneğin main branch’inde file.txt’in 5. satırı “Merhaba” olarak değiştirilmiş.

feature-branch’te aynı satır “Selam” olarak değiştirilmiş.

main branch’inde feature-branch ile merge yapılırsa, Git hangi satırı bırakacağını bilemez → merge conflict oluşur.

**Detaylar:**

- Siz branch-A üzerinde bir dosyayı değiştirdiniz Aynı dosya branch-B üzerinde de değişmiş.

- Git, bu değişiklikleri otomatik birleştiremiyor ve size çatışmayı (conflicti) bildiriyor.



##  Çözüm Adımları:


 **Git merge yaparken şöyle bir mesaj alırsınız:**

- Auto-merging file.txt
- CONFLICT (content): Merge conflict in file.txt
- Automatic merge failed; fix conflicts and then commit the result.

### Bu demek oluyor ki example.txt dosyasında iki farklı değişiklik çakışıyor.

- Hangi dosyalar çatışmış görmek için önce **git status** yazıyorsunuz.

- Çıktıda şöyle görürsünsünüz 

**both modified: example.txt** 

Yani hem sizin branch’ında hem diğer branch’ta değişiklik var.

### Önce Çatışmayı Fark Etmeliyiz

- git checkout main, git merge feature-branch

- Conflict işaretlerini sil <<<<<<<, =======, >>>>>>> satırlarını mutlaka silmelisin.

- HEAD → Senin bulunduğun branch (main)

- "=======" → ayırıcı

- feature-branch → diğer branch

**Git sizi uyarır:**

- CONFLICT (content): Merge conflict in file.txt
Automatic merge failed; fix conflicts and then commit the result.

 **Hangi değişikliği tutacağına karar ver**

- Sadece kendi değişikliğini tut → **diğerini sil**

- Sadece diğer branch’in değişikliğini tut → **kendi değişikliğini sil**

- İkisini birleştir → ikisini de düzenle

- Merge commit’i oluştur **git commit**

- Git otomatik mesaj olarak Merge branch 'feature-branch' into main yazar. Merge tamamlanmış olur.
</details>

<details>
<summary><strong>CI/CD nedir? Azure DevOps, GitHub Actions ile pipeline örnekleri</strong></summary>


**1. CI/CD Nedir?**

<br>
- CI (Continuous Integration / Sürekli Entegrasyon):

- Geliştiricilerin yaptıkları değişikliklerin sık sık merkezi bir repository’ye (GitHub, Azure Repos) entegre edilmesi ve otomatik olarak test edilmesi sürecidir. Amaç hataları erken yakalamak ve entegrasyon sorunlarını azaltmak.

- Kod entegrasyonunda oluşabilecek hataları erken yakalamak için CI kullanılır.

- Continuous Delivery (Sürekli Teslimat): Kod testlerden geçtikten sonra manuel onay ile production’a veya staging’e gönderilir CD kullanılır.

- CI, yazılım geliştirme sürecinde geliştiricilerin kod değişikliklerini sık sık merkezi bir repository’ye (GitHub, GitLab vb.) göndermesi ve bu değişikliklerin otomatik olarak test edilmesi sürecidir.

- CD (Continuous Delivery / Continuous Deployment / Sürekli Teslimat / Sürekli Dağıtım):

- Continuous Delivery: Kod, testlerden geçtikten sonra manuel onay ile production’a veya staging’e gönderilir.

- Continuous Deployment: Kod, testlerden geçtikten sonra otomatik olarak production’a gönderilir

- **Kısaca: CI kodu sürekli test eder, CD ise kodu sürekli dağıtır**

<br>

**CI/CD’nin avantajları:**

- Hataları erken yakalar.

- Geliştirme sürecini hızlandırır.

- Otomatik test ve dağıtım ile güvenilirlik artar.

- Takımlar arasında entegrasyonu kolaylaştırır.

- GitHub, Azure Repos / Azure DevOps, Netflix, Facebook, Instagram, Airbnb gibi bir çok uygulama ve araç CI/CD kullanır çünkü kod sürekli değişir ve hızlı deploy gerekir
<hr> 

### Azure DevOps ile Pipeline Örneği

### - İlk adım olarak:

**Trigger / Başlatma:**

- Ne yapar: Pipeline hangi olayla tetiklenecek belirlenir (örn. main branch’e push, pull request).

**Build / Derleme:**

- Ne yapar: Kodun çalışabilir hâle getirilmesi, derlenmesi veya paketlenmesi.

**Test:**

- Ne yapar: Unit test, integration test veya end-to-end testleri çalıştırır.

**Deploy / Dağıtım:**

- Ne yapar: Testleri geçen kodu staging veya production ortamına taşır.

**Notification / Bildirim**

- Ne yapar: Pipeline sonucu hakkında geliştiricilere bilgi verir (başarılı/başarısız).

**Aşağıdaki Örnek Bir GitHub Actions Pipeline Örneğidir.**

 ```

name: Python CI/CD

# 1. Tetikleyici (Trigger)
on:
  push:
    branches: [ main ]        # main branch’e push olunca çalışır
  pull_request:
    branches: [ main ]        # Pull request açıldığında çalışır

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest     # 2. Çalışma ortamı (VM)

    steps:
    # 3. Kodun çekilmesi
    - uses: actions/checkout@v3
      name: Step 1: Checkout code
      # Ne yapıyor: Repository’deki kodu pipeline ortamına kopyalar

    # 4. Python kurulumu
    - name: Step 2: Setup Python
      uses: actions/setup-python@v4
      with:
        python-version: '3.x'
      # Ne yapıyor: Pipeline ortamına Python 3.x yükler

    # 5. Bağımlılıkların yüklenmesi
    - name: Step 3: Install dependencies
      run: pip install -r requirements.txt
      # Ne yapıyor: Projenin çalışması için gerekli kütüphaneleri yükler

    # 6. Testlerin çalıştırılması
    - name: Step 4: Run tests
      run: pytest
      # Ne yapıyor: Kodun hatasız çalışıp çalışmadığını test eder (CI adımı)

    # 7. Deploy
    - name: Step 5: Deploy to server
      run: |
        scp -r ./app user@server:/var/www/app
        ssh user@server 'systemctl restart app'
      # Ne yapıyor: Testleri geçen kodu uzak sunucuya kopyalar ve uygulamayı restart eder (CD adımı)

```
<hr>

**Aşağıdaki ise bir Azure DevOps Örneğidir**
 ```
name: Python CI/CD

# 1. Tetikleyici (Trigger)
on:
  push:
    branches: [ main ]       # main branch’e push olunca tetiklenir
  pull_request:
    branches: [ main ]       # Pull request açıldığında da tetiklenir

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest    # 2. Hangi işletim sistemi üzerinde çalışacak

    steps:
    # 3. Repo kodunu çek
    - uses: actions/checkout@v3
      name: Step 1: Checkout code
      # Ne yapıyor: Repository’deki kodu pipeline ortamına kopyalar

    # 4. Python kurulumu
    - name: Step 2: Setup Python
      uses: actions/setup-python@v4
      with:
        python-version: '3.x'
      # Ne yapıyor: Pipeline ortamına Python 3.x kurar

    # 5. Bağımlılıkları yükleme
    - name: Step 3: Install dependencies
      run: pip install -r requirements.txt
      # Ne yapıyor: Projenin çalışması için gerekli kütüphaneleri yükler

    # 6. Testleri çalıştır
    - name: Step 4: Run tests
      run: pytest
      # Ne yapıyor: Kodun düzgün çalışıp çalışmadığını kontrol etmek için testleri çalıştırır (CI adımı)

    # 7. Deploy
    - name: Step 5: Deploy to server
      run: |
        scp -r ./app user@server:/var/www/app
        ssh user@server 'systemctl restart app'
      # Ne yapıyor: Testler başarılıysa kodu uzak sunucuya kopyalar ve uygulamayı restart eder (CD adımı)

```

**Arasındaki Farklar:**

- Azure genellikle Genellikle büyük projelerde kullanılır, Build, Test, Deploy adımları portal üzerinden görselleştirilebilir. CI ve CD pipeline’ları aynı yerde veya ayrı ayrı olabilir.

- GitHub Actions ise Repo tabanlıdır, pipeline dosyası repo içinde bulunur, GitHub event’leri ile pipeline tetiklenir (push, pull request, issue açma, release vb.). Daha küçük veya açık kaynak projeler için hızlı ve kolaydır.

## .NET Projesinde Nasıl Uygulanabilir? 

- **Siz bir ASP.NET Core web uygulaması geliştiriyorsunuz. Bu uygulama banka işlemleri yapan bir sistem. Her gün yeni özellikler ekliyorsunuz ve kodu GitHub’a push ediyorsunuz. Ama her seferinde “Acaba deploy ederken hata çıkar mı?” diye endişeleniyorsunu<. İşte CI/CD bu noktada devreye giriyor ve size “otomatik testçi ve deploy asistanı” gibi yardım ediyor.**

**Adım Adım:**

- **1. Adım: Siz kodunuzu GitHub’daki main branch’ine push ediyorsunuz.  GitHub Actions veya Azure DevOps bunu görüyor ve diyor ki: “yeni kod geldi Hadi bakalım test edelim ve deploy edelim.”**

- **2. Adım: Pipeline ortamı bir Windows veya Linux makinesi açıyor. dotnet build komutu çalışıyor:  hatasız derlenip derlenmediğine bakıyor. Eğer bir hata varsa, hemen size bildiriyor ve pipeline duruyor.**

- **3. Adım: Pipeline, dotnet test komutunu çalıştırıyor Unit testler, integration testler devreye giriyor. Örneğin para transferi fonksiyonu doğru çalışıyor mu kontrol ediliyor. Eğer testler başarısızsa pipeline kodu yapmıyor Böylece hatalı kod merge veya deploy edilmiyor**

- **4. Adım: Kod testlerden geçtiyse pipeline, dotnet publish komutunu çalıştırıyor. Uygulaman artık sunucuya taşınmaya hazır bir paket hâline geliyor.**

- **5. Adım: Pipeline, kodu sunucuya kopyalıyor (scp veya Azure deploy task). Sunucuda uygulama restart ediliyor (systemctl restart myapp veya IIS restart). Artık yeni özellikler canlı ortamda kullanıcıların kullanımına sunuluyor.**

- **6. Adım: Adım: Bildirim CI/CD pipeline sonucu sana bildiriliyor: Başarılı veya Hatalı.”**


<br>
</details>

<details> 
<summary><strong>Ek Maddeler</strong></summary>

### SDLC (Software Development Life Cycle / Yazılım Geliştirme Yaşam Döngüsü) Nedir?

- SDLC, bir yazılımın fikirden başlayıp kullanıcıya ulaşana kadar geçen tüm geliştirme sürecini sistematik şekilde yöneten bir yaşam döngüsüdür.

- Amacı Yazılımın kaliteli, hatasız ve zamanında teslim edilmesini sağlamak ve Riskleri ve maliyetleri azaltmaktır Kısaca: SDLC, “yazılımın doğumundan emekli olana kadar geçen süreç” diyebiliriz.

### SDLC Aşamaları: 

**- 1 Planlama:**

- Ne yapılacak, neden yapılacak belirlenir. Kaynaklar, zaman çizelgesi ve maliyet planlanır.
- **Örnek: Bir banka uygulaması geliştirmek için hedefler ve gereksinimler belirlenir.**

**- 2 Requirements Analysis / Gereksinim Analizi:**

- Kullanıcı ve sistem gereksinimleri toplanır ve dokümante edilir.
- **Örnek: Kullanıcıların mobil bankacılıkta ne yapmak istediği analiz edilir (para transferi, bakiye kontrol, ödeme)**

**- 3 Design / Tasarım:**

- Yazılımın mimarisi ve tasarımı yapılır, UI/UX tasarımı, veri tabanı yapısı, modüller belirlenir.
- **Örnek: Mobil bankacılık uygulamasının ekran tasarımları ve veri tabanı şeması hazırlanır.**

**4 - Implementation / Kodlama:**

- Yazılımın asıl kodlanması bu aşamada yapılır. Modüller geliştirilir ve birleştirilir.
- **Örnek: Bankacılık uygulaması için Python, Java veya Swift ile kod yazılır.**

**5 - Testing / Test:**

- Yazılımın hatasız çalışıp çalışmadığı test edilir. Unit test, integration test, system test gibi testler uygulanır.
- **Örnek: Para transferi fonksiyonu hatasız çalışıyor mu test edilir.**

**6 - Deployment / Yayına Alma:**

- Canlı ortamda kurulum yapılır, Yazılım kullanıcıya sunulur.
- **Örnek: Mobil uygulama App Store ve Play Store’a yüklenir**

**7 - Maintenance / Bakım:**

- Yazılım kullanıldıkça güncellenir, hatalar düzeltilir, yeni özellikler eklenir.
- **Örnek: Bankacılık uygulamasına yeni güvenlik özellikleri eklenir veya hata düzeltmeleri yapılır.**

**Özet Olarak:**

## SDLC, bir yazılım projesini planlamadan bakıma kadar tüm aşamalarda sistematik yönetme metodudur.

- Planla → Analiz et → Tasarla → Kodla → Test et → Yayınla → Bakım yap

- CI/CD gibi pipeline sistemleri, SDLC’nin Implementation ve Deployment aşamalarını otomatikleştirmeye yardımcı olur.
<br>
<hr>


### 1. Agile/Scrum/Kanban metodolojileri 

**- Agile, yazılım geliştirmede çevik, esnek ve iteratif bir yaklaşımdır.**

**Temel Özellikleri:**

- Küçük adımlarla ve kısa iterasyonlarla geliştirme yapılır, Sürekli kullanıcı geri bildirimi alınır.
- Değişikliklere hızlı adapte olunur.
-Takım içi iletişim ve işbirliği ön plandadır.

### Örnek: Bir mobil uygulama geliştiriyorsunuz. Agile ile 2 haftalık kısa sprintler halinde her seferinde küçük özellikleri tamamlayıp kullanıcıya sunuyorsunuz. Kullanıcı geri bildirimiyle bir sonraki sprint’i şekillendiriyorsunuz.
<br>

### 2. Scrum Metodolojisi: 

**- Scrum, Agile’ın bir uygulama şeklidir. Takım bazlı, belirli rolleri ve süreçleri olan bir framework sunar.**

**Temel Özellikleri:**

- Sprint: Genellikle 1-4 hafta süren geliştirme döngüsü
- Product Owner: Ürün gereksinimlerini belirler
- Scrum Master: Takımın sürece uygun çalışmasını sağlar, engelleri kaldırır
- Development Team: Kodlayan ve test yapan ekip
- Artifacts: Product Backlog, Sprint Backlog, Increment

### Örnek: Takım bir Sprint Planning toplantısı yapar → 2 haftalık yapılacaklar belirlenir Günlük Daily Scrum toplantısı yapılır → herkes ne yaptığını ve engelleri paylaşır Sprint sonunda demo yapılır ve kullanıcı geri bildirimi alınır

<br>
<hr>

### 3. Kanban Metodolojisi:

**- Kanban, Agile prensiplerini kullanır ama akışı görselleştirmeye ve iş yükünü dengelemeye odaklanır.**

**Temel Özellikleri:**

- Kanban Board: İşlerin durumunu gösteren görsel tablo (örn. To Do / In Progress / Done)

- Work In Progress (WIP) Limit: Aynı anda yapılacak iş sayısını sınırlar

- Continuous Flow: İşler durmaksızın akış halinde ilerler

### Örnek: Bir web geliştirme projesinde Kanban board oluşturursunuz: To Do → Yapılacak işler In Progress → Üzerinde çalışılan işler Done → Tamamlanan işler Her geliştirici bir işi alır ve tamamlayana kadar devam eder, board ile iş akışı net görülür.

</details>
<br>
<br>

## 2. .NET Ekosistemi

<details> 
<summary><strong>🖥.NET nedir? Tarihçesi, amacı, neden kullanılır?</strong></summary>
<br>
 
- **.NET, Microsoft tarafından geliştirilmiş bir yazılım geliştirme platformudur. Amacı Windows, web, mobil ve bulut uygulamaları geliştirmeyi kolaylaştırmak. Özellik: Farklı programlama dilleri ve cihazlar için ortak bir altyapı sağlar. Özetle .NET, geliştiricilere güçlü ve esnek bir yazılım geliştirme ortamı sunar.**
<br>

### .NET Tarihçesi

### İlk başta Başlangıçta Windows odaklıydı (.NET Framework) Sonra cross-platform ve açık kaynak hâline geldi (.NET Core) Günümüzde tek ve modern platform (.NET 5+) olarak kullanılıyor Aşağıdaki ise detaylı tarihçesi:

- 2000: **.NET ilk kez Microsoft, .NET Framework projesini tanıttı. Amacı ise Windows uygulamaları, web uygulamaları ve servisler için ortak bir platform oluşturmaktı.**

- 2001: **.NET Framework 1.0 Olarak Resmi olarak piyasaya sürüldü. Temel özellikler: Windows Forms, ASP.NET, ADO.NET gibi bileşenler Sadece Windows platformunu destekliyordu.**

- 2003: **2003 – .NET Framework 1.1 Duyrulmuştu, Güncellemeler: Web servisleri geliştirme desteği, mobil uygulama temelleri.**

- 2005: **.NET Framework 2.0 Çıktı Yeni özellikler: Generics, ASP.NET 2.0, Windows Forms iyileştirmeleri.**

- 2006: **2008 – .NET Framework 3.5 LINQ (Language Integrated Query) eklendi WCF (Windows Communication Foundation) ve WPF (Windows Presentation Foundation) destekleri geliştirildi**

- 2010: **.NET Framework 4.0 Parallel programming ve performans iyileştirmeleri Gelişmiş web servis desteği**

- 2016: **.NET Core 1.0 Cross-platform (Windows, Linux, Mac) için modern platform Açık kaynak olarak sunuldu**

- 2019 – **.NET Core 3.1 Masaüstü uygulamaları (WinForms, WPF) ve konsol uygulamaları için destek Uzun süreli destek yapıldı ve (LTS) sürümü çıktı**

- 2021 ve sonrası: **NET 6, .NET 7, .NET 8… Modern uygulamalar için performans iyileştirmeleri, bulut ve mobil entegrasyonları ASP.NET Core, Blazor, MAUI gibi teknolojilerle gelişmiş uygulama geliştirme**


</details>

<details> 
<summary><strong>.NET Framework, .NET Core ve .NET 7/8+ farkları</strong></summary>

### 1. .NET Framework:

- **Platform: Sadece Windows**

- **Açık Kaynak: Hayır (kapalı kaynak)**

- **Kullanım: Windows Forms, WPF, ASP.NET Web Forms Masaüstü uygulamaları ve Kurumsal Windows uygulamaları**

- **Performans: Orta seviye, Windows’a optimize**

- **Güncelleme: Yeni özellik ekleme yavaş, Microsoft tarafından destekleniyor**

- **Avantaj: Windows uygulamaları ve eski projeler için stabil**

- **Dezavantaj: Cross-platform değil, modern uygulamalar için sınırlı**
<br>

### 2 .NET Core:

- **Platform: Cross-platform (Windows, Linux, Mac)**

- **Açık Kaynak: Evet (GitHub üzerinden)**

- **Kullanım: Modern web uygulamaları, API, mikroservisler Örneğin ASP.NET Core Web API Cross-platform CLI araçları Docker ve Kubernetes uygulamaları**

- **Performans: Daha hızlı, hafif ve modüler**

- **Güncelleme: Hızlı geliştirme, sürümler sık güncelleniyor**

- **Avantaj: Platform bağımsız, konteyner ve bulut dostu**

- **Dezavantaj: Bazı eski Windows özelliklerini desteklemez**
<br>

### 3. .NET 5 / 6 / 7 / 8+:

- **Platform: Cross-platform, modern ve birleşik**

- **Açık Kaynak: Bulunuyor.**

- **Kullanım: Web, masaüstü, mobil, bulut, IoT, oyun geliştirme vs.**

- **Performans: Yüksek performans, modern optimizasyonlar eskiye göre çok daha kaliteli**

- **Güncelleme: Tek platformda tüm özellikler birleşik, düzenli LTS sürümleri geliyor geleceği daha çok parlak**

- **Avantaj: .NET Framework ve .NET Core birleşti → tek platform Modern uygulamalar için optimize  MAUI ile cross-platform mobil ve masaüstü desteği**

- **Dezavantaj: Çok eski projeler için uyumluluk sorunları olabilir özellikle NET 5 ve sonrasında problem yaşanabilir**

<br>

### 3. Platformlar arası çalışabilir mi? (Windows, Linux, macOS):

**1. NET Framework:** 

- **Çalışma Alanı: Sadece Windowsla sınırlı**

- **Linuxi macOS'ta doğrudan çalışmaz. Esasen Windowsa bağlıdır**

<br>

**2. NET Core:**

- **Çalışma Alanı: Windows,Linux,macOS sadece Windows ile sınırlı değil** 

- **Microsoft, .NET Core’u cross-platform olarak tasarladı.**

- **Konsol uygulamaları, Web API’ler ve ASP.NET Core projeleri bu üç platformda da aynı şekilde çalışır.**

<br>

**3..NET 5 / 6 / 7 / 8+:**

- **Tamamen cross-platformdur**

- **Windows, Linux ve macOS üzerinde resmi destek alır.**

- **Masaüstü (WinForms, WPF) kısmı sadece Windows’a özgü kalmıştır, ama diğer alanlarda (Web, Blazor, MAUI, konsol, API, IoT) tüm platformlarda çalışır.**


</details>
