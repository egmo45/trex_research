 ## 1. 🗃 Modern Yazılım Geliştirme Pratikleri

<details>
<summary><strong> Git nedir? GitHub nedir?</strong></summary>
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

<summary><strong> Temel Git komutları: init, clone, add, commit, push, pull, branch, merge..</strong></summary>
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

## 2.🖥 .NET Ekosistemi

<details> 
<summary><strong>.NET nedir? Tarihçesi, amacı, neden kullanılır?</strong></summary>
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

- **Dezavantaj: Çok eski projeler için uyumluluk sorunları olabilir özellikle NET 5 ve öncesinde problem yaşanabilir**

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

<details>

<summary><strong>Senkron ve Asenkron Programlama</strong></summary>

## Senkron Programlama: 

- **Senkron programlama, bir işlem tamamlanmadan diğer işlemlerin başlamamasını gerektiren bir programlamadır. Bu tür bir programlama tarzında, bir işlem veya görev diğerlerinin önünde olmalı ve bu işlem tamamlanana kadar diğer işlemler beklemelidir. Bu durum, işlemlerin belirli bir sıraya göre gerçekleştirilmesini sağlar. Yani bir işlem tamamlanmadan diğer bir işleme geçiş olmaz. Ayrıca dezavantaj olarak bir işlem uzun sürerse, diğer işlemler onun tamamlanmasını beklemek zorunda kalır. Bu da programın genel performansını olumsuz etkileyebilir.**

###  🟠 Senkron Programlamaya Pythondan Örnek: 
```
import time

print("1. Adım: Veri indiriliyor...")
time.sleep(3)  # 3 saniye bekliyor
print("2. Adım: Veri işleniyor...")
time.sleep(2) # 2 saniye bekliyor
print("3. Adım: İşlem tamamlandı.")

# İşlemler göründüğü gibi tek tek çalışırlar bir işlem tamamlanmadan diğer bir işlem çalışmaz.

```

---

## Asenkron Programlama: 

- **Asenkron programlama, işlemlerin birbirini beklemeksizin eş zamanlı olarak çalıştığı bir programlama modelidir. Bu programlama tarzında işlemlerin birbirini beklemek gibi bir zorunluğu yokturidir. Bu yaklaşımda, her işlem kendi başına ve bağımsız bir şekilde çalışır. Ayrıca Bir işlem uzun sürüyorsa (örneğin dosya okuma, ağ isteği, veritabanı sorgusu vs.), program o işlem bitene kadar beklemez ve başka işleri yapmaya devam eder. Asenkron programlama, özellikle birden çok işlemi aynı anda yürütmek isteyen uygulamalar için oldukça faydalıdır. Ancak dezavantajı olarak İşlemler arasındaki koordinasyon ve hata yönetimi gibi konular meydana gelebilir ve kodda bir hata çıkarsa düzeltmek uzun zamanlar alabilir**


###  🟠 Asenkron Programlamaya Pythondan Örnek: 
```
import async

async def main():
    print("1. Adım: Veri indiriliyor...")
    await asyncio.sleep(3)  # 3 saniye bekle (asenkron)
    print("2. Adım: Veri işleniyor...")
    await asyncio.sleep(2)
    print("3. Adım: İşlem tamamlandı.")

asyncio.run(main())

# İşlemler duraklama olmadan çalışırlar veriler işlenir ve hemen sonuca varılır

```

--- 

### Asnyc, Await, Task ve ConfigureAwait Nedir? 

 **1 - Task Nedir?:**

- **Task .NET’te asenkron işlemin temsilcisidir. “Gelecekte bir değerin/işlemin tamamlanacağını” gösterir.**

- **Task → geriye değer döndürmeyen asenkron işlem.**

- **Task<T> → geriye T tipi bir değer döndüren asenkron işlem.**

<br>

**2 - Asnyc Nedir?:**

- **Bir metodu asenkron yapar ve await kullanılmasına izin verir.**

- **Async koymak kodu otomatik olarak paralel çalıştırmaz; sadece await ile birlikte asenkron akışı sağlar.**

 <br>

**3 - Await Nedir?**

- **Await bir Task’in tamamlanmasını asenkron olarak bekleyen bir koddur**

- **Beklerken çağıranı bloklamaz; method geri kalan kodu task bitince devam ettirir.**

- **await kullanan method derhal tamamlanmaz çağırana Task döner. Çağıran kod await ederse, akış orada bekler ama thread bloklanmaz.**

---

**Dipnot: Thread hakkında ufak bir bilgi** 

- **Thread’ler program kodu, data, dosyalar gibi işletim sistemi kaynaklarını ortak kullanır. Eğer bir process, birden fazla thread’e sahipse; birden fazla görevi eş-zamanlı yapabilir.**

- **Her thread’in kendi call stack’i vardır (yani kendi yürütme sırası)**

---

**4 - ConfigureAwait Nedir?:**

- **ConfigureAwait Herhangi bir veya Task<T> nesnesinde, anahtar sözcüğün bir görevi beklerken nasıl davranacağını yapılandırmak için kullanılabilen bir yöntemdir adında bir Boole parametresi alır ve sonraki devamın, awaitgörevi başlatan bağlamla aynı bağlamda çalışıp çalışmayacağını belirler.**

- **Kısacası: Await ile bir Task beklerken, ConfigureAwait(bool) çağırarak await sonrasında kodun hangi context’te (thread veya senkronizasyon bağlamında) devam edeceğini belirlersin.**

</details>
<br>
<br>

## 🗄️ Backend Geliştirme Temelleri


<details> 

<summary><strong>Backend Nedir? Frontend ile Farkları</strong></summary>

- **Web Dünyasında iki tane yüz vardır Backend ve Frontend. Web Sitelerinin Görünen ve Görünmeyen Yüzleri olarak web sitelerinin nasıl oluştuğunu anlamamıza yardımcı olur sırasıyla Back-End ve Front-Endi inceleyeceğiz**


###  Frontend: İnternetin Görünen Yüzü: 

- **Hepimiz Facebook,Instagram,X(Twitter),Youtube, Netflix gibi daha bir çok uygulama kullanıyoruz ve bu web sitelerde uygulamalarda gördüğümüz şeylerin hepsi Frontend sayesinde yapılıyor Tıpkı bir resim gibi, Front-End de web sitesinin ilk izlenimini oluşturur ve kullanıcı deneyimini şekillendirir. Renkler, yazı tipleri, düzen, animasyonlar ve etkileşimli öğeler, Front-End tasarımının temel unsurlarıdır.**

- **Frontend Programları Nelerdir:**

- **HTML: Bir resmin taslağını oluşturur gibi Web Sitesinin temelini atar oluşturur bazı temel renkler yapar ve siteyi boyutlandırır bir taslak görevi görür.**

- **CSS: Resmin taslağı hazırlanınca içine çizim yapmak kalır Bunuda CSS Yapar yani (Cascading Style Sheets),  adını verdiğimiz güçlü bir teknoloji vardır. HTML, web sayfalarının iskeletini oluştururken; CSS bu iskeleti süsleyen, renklendiren, düzenleyen ve kullanıcı dostu hale getiren yapı taşını sağlar.**

- **JAVASCRIPT: Web dünyasında kullanıcıların gördüğü ve etkileşimde bulunduğu her şeyin arkasında JavaScript (JS) yatar . HTML sayfanın iskeletini, CSS tasarımı sağlarken; JavaScript, web sayfalarını dinamik ve etkileşimli hale getirir. Bu makalede, JavaScript’in frontend’de nasıl kullanıldığını ve web geliştirmedeki önemini detaylı bir şekilde ele alacağız.**

- **JavaScript’in Frontend’deki Rolü: Javascript hem Frontend hemde Backendde kullanılabilir ama konumuz Frontend olduğu için bugün Frontend kısmına bakacağız: JavaScript, sayfada HTML elementlerini değiştirme, ekleme veya silme işlemlerini yapabilir. Örneğin bir kullanıcı butona tıkladığında başlığın değişmesi veya yeni bir içerik kutusunun eklenmesi JS ile sağlanı Form gönderimleri, buton tıklamaları, fare hareketleri veya klavye girişleri JS ile yakalanır ve işlenir. Bu sayede web sayfaları yalnızca statik görünmekten çıkar ve kullanıcıya etkileşimli deneyim sunar JavaScript, CSS stillerini değiştirebilir ve animasyonlar ekleyebilir. Örneğin fare üzerine gelindiğinde arka plan renginin değişmesi veya butonların kayarak açılması JS ile yapılır.**


###  Backend: İnternetin Görünmeyen Yüzü: 

- **Hepimiz Facebook,Instagram,X(Twitter),Youtube, Netflix gibi daha bir çok uygulama kullanıyoruz ve bu web sitelerde uygulamalarda görmediğimiz şeylerin hepsi Backend ile yapılıyor, Backend web sitesinin perde arkasında çalışan, kullanıcıların doğrudan göremediği ancak sitenin işlevselliğini sağlayan kısmıdır. Veri tabanı yönetimi, sunucu tarafı mantığı, API entegrasyonları ve güvenlik gibi kritik görevleri yerine getirir. BackEnd, web sitesinin beyni ve kalbi olarak düşünülebilir.**

- **Backend Programları Nelerdir:** 

- **Python: Python, sadeliği ve güçlü kütüphaneleri ile backend dünyasında oldukça popülerdir ve öğrenilmeside kolay bir dildir çoğu yazılımcı için başlangıç dili olarak kabul edilebilir Backendde yaptığı çalışmar ise API geliştirme ve veri yönetimi,Kullanıcı doğrulama ve yetkilendirme Sunucu tarafı iş mantığı,Veri analizi ve otomasyon işlemleri vs..** 

- **PHP: Eski bir dil ve ancak halen daha çok popüler ve Web Siteleri Dünyasının %70'i Web Sitelerinde PHP kullanmaktadırYaptığı İşler Web formları ve veri tabanı işlemleri,Sunucu tarafı iş mantığı,CMS ve blog sistemleri (WordPress, Joomla gibi) Hosting ve barındırma açısından geniş destekleri bulunmakta ve MySQL programı ile çok uyumlu çalışması ile mükemmel bir Backend uygulamasıdır**

- **Java: Javai özellikle büyük ölçekli ve kurumsal uygulamalarda backend’de tercih edilir. PHP gibi eski bir dildir ancak halen daha günümüzde kullanılır Kurumsal uygulamalardan mobil uygulamalara, oyunlardan web servislerine kadar çok geniş bir kullanım alanına sahiptir. Veri Tabanı Yönetimi, API Geliştirme ve Özellikle backend geliştirme dünyasında Java, güvenilirliği ve ölçeklenebilirliği nedeniyle yaygın olarak tercih edilir.**

</details>


<details> 

<summary><strong>Web sunucusu nedir? API nedir? API türleri</strong></summary>

### WEB Sunucusu Nedir?:

- **Web sunucusu, HTTP(Hypertext Transfer Protocol)veya HTTPS(HTTP Secure) protokolü üzerinden gelen istekleri alan, işleyen ve yanıt veren bir yazılım veya donanım sistemidir. HTML,CSS,JS gibi yazılım dillerinin oluşturdukları istekleri alır ve geri gönderir diğer  Kısaca API, yazılımların birbirine “konuşma dili” olarak düşünülebilir.kaynakların içerğini yollar eğer yollayamazsa hata kodları verir(İsteğe karşılık 200 OK, 404 Not Found veya 500 Internal Server Error gibi HTTP durum kodları döndürür.) Bu iletişim süreci şu şekilde işler. istemcinin belirli bir URL (Uniform Resource Locator) ile iletişim talep etmesiyle başlar. Bu istek, sunucuya HTTP protokolü kullanılarak iletilir. Ardından talep istenilen sonuca varırsa geri karşılık olarak istemciye geri yolla rHTTPS ile veri şifreleme yaparGüvenlik duvarları ve erişim kontrolü hazırlar Ayrıca Backend uygulamaları (Python, Java, C#, PHP) genellikle web sunucusu üzerinden çalıştırılır. Kullanıcı tarayıcıdan bir istek gönderdiğinde web sunucusu, backend uygulamasına iletir ve gelen veriyi kullanıcıya sunar.**


### API Nedir:

- **Günümüz yazılım dünyasında uygulamalar ve servisler birbirleriyle sürekli iletişim halindedir. Bu iletişimi sağlayan köprülerden biri API (Application Programming Interface – Uygulama Programlama Arayüzü)’dür. API, farklı yazılımların birbirleriyle güvenli ve standart bir şekilde veri alışverişi yapmasını sağlar.Geliştiriciye hazır fonksiyon ve metodlar sunar. Uygulama veya sistemlerin birbirine doğrudan müdahale etmeden iletişim kurmasını sağlar. Kullanım alanı evrenseldir Web ve Mobil Uygulamalarda Backend ile frontend arasındaki veri akışı API üzerinden sağlanır. Üçüncü Parti Servisler: Örn. Google Maps, Twitter, ödeme sistemleri (PayPal, Stripe) API ile entegre edilir. Uygulamalar ayrı ayrı geliştirilip API üzerinden birbirine bağlanabilir. Aynı API, farklı uygulamalar tarafından tekrar tekrar kullanılabilir.**



### API Türleri Nelerdir:

 **Herkese Açık API’ler (Public APIs)**

- **Herkesin erişimine açık, dokümantasyonu bulunan API’ler. Örn: Google Maps API, OpenWeather API Başka bir ifadeyle, Public API’ler, bir işletmenin iç sistemleri veya hizmetleri ile dış paydaşlar arasında bağlantı kurarak iş birliğini teşvik ederler hizmetleri veya verileri etrafında daha geniş bir ekosistem oluşturmasına olanak tanır.**

<br>

 **Partner API’ler**

- **Yalnızca şirket ortaklarına açılan bir API'dir yarı kapalı yarı açık gibi düşünülebilir bu API bağlantısı resmi lisanslara sahip bir bağlantıdır. Genel API'lere göre çok daha sağlamdır bu yüzden hem iş yeri hemde lisanslı çalışanlar için daha güvenli ve emniyetli bir iletişim ağı sunar**

<br>

**Dahili API’ler (Internal APIs)**

- **Dahili API’ler (Internal APIs,Private APIs olarakta geçer)  yalnızca işletmelerin dahili kullanımı için paylaşılır. Bu yüzden de sadece işletme sınırları içinde erişilir. Genel veya iş ortağı API’lerinin aksine dışarıdan bir tarafın erişimine tamamen kapalıdır dış saldırılara daha kapalı ve güvenlidir Dış geliştirici ekosistemine kapalıdır, ürün yayılımını artırmaz.**

<br>

**Bileşik API'ler (Composite API's)**

- **Birden fazla servisi birleştirip tek uç noktadan erişim sunan API’lerdir. Arada köprü görevi görür ve iletişim ağı sağlar genelde bu tür API'ler farklı uygulamalardan veri ihtiyacı olduğu zaman veya bir müdahale olması gerektiği zaman kullanılır Bu sayede geliştiriciler gelen verileri tek tek yönetebilirler**



</details>

<details>

<summary><strong>HTTP nedir? HTTP metodları: GET,POST,PUT,DELETE</strong></summary>

### HTTP Nedir?

- **HTTP, açılımıyla HyperText Transfer Protocol, internet üzerinde istemci (client) ile sunucu (server) arasında iletişim sağlayan iletişim protokolüdür. Bir tarayıcıdan www.ornek.com yazdığınızda, tarayıcı (istemci) sunucuya bir HTTP isteği (request) gönderir. ve HTTP cevap (response) gönderir bu cevapta genelde HTML,JSON,resim,video gibi veriler olur. Yani HTTP WEB dünyasının dili diyebiliriz HTTP'de her istek bağımsız ilerler HTTP önceki şeyleri hatırlamaz stataless(durumsuz) bir protokole sahiptir kimlik doğrulama benzeri işlerde hepimizin hemen hemen aşina olduğu çerezler(cookies),token,session gibi ek yöntemleri sık sık kullanır**

### HTTP Metodları Nelerdir?

 **GET : Sunucudan veri çekmek için kullanılan bir metoddur URL üzerinden bir parametre gönderir belirtilen URL'den veriyi almak için kullanılır kısaca GET metodu Sunucudan veriyi çekmek için tarayıcıdan gönderilen bir isteği temsil ede***

###  🟠 GET Metodu Örnek: 
```
GET /sayfa?parametre1=deger1&parametre2=deger2 HTTP/1.1
Host: www.ikea.com

```
---

**POST : Belirtilen URL’e yeni bir kaynak eklemek için kullanılır sunucudan veri ister sadece verileri okur değiştirmez aynı POST’u tekrar edersen, tekrar veri eklenir  GET’ metodundan farklı olarak, POST verileri URL üzerinden değil, genellikle HTTP gövdesi içinde taşınır. Genellikle veritabanına bir veri eklemek için kullanılmakadır**

###  🟠 POST Metodu Örnek: 
```
POST /form HTTP/1.1
Host: www.bayramalacam.com
Content-Type: application/x-www-form-urlencodedusername=bayram&password=1
```

---

**PUT : Amacı başlıca Sunucudaki kaynağı tamamen güncellemek veya oluşturmak. belirtilen URL’deki var olan kaynağın tamamını veya bir kısmını güncellemek için kullanabilir Idempotent(Bir işlemi aynı şekilde tekrar tekrar yapmanın sonucu değişmiyorsa, o işlem idempotenttir.) bir metoddur**

###  🟠 PUT Metodu Örnek: 
```
PUT /user/update/2 HTTP/1.1
Host: www.bayramalacam.com
Content-Type: application/json{
"username": "bayram",
"password": "12345"
}
```

---


**DELETE : Amacıda isminden anlaşılacağı gibi Sunucudan kaynağı silmektir Idempotenttir aynı DELETE tekrar edilirse zaten silinmiş olur, hata vermez.**

###  🟠 DELETE Metodu Örnek: 
```

DELETE /user/delete/2 HTTP/1.1
Host: www.bayramalacam.com

```
--- 


</details>


<details>

<summary><strong>RESTful Servislerin Çalışma Mantığı</strong></summary>

### REST ve RESTful Web Servis Kavramı:

**1. REST Nedir?**

- **REST (Representational State Transfer) oy Fielding tarafından 2000’lerde tanımlanmış bir mimari stildir protokol olmamakla birlikte amacı Web üzerinde kaynaklara (resources) erişimi standart ve basit yöntemlerle yapmaktır Kısacası 2000 yılında bir sunucu ve istemci arasında hızlı ve kolay iletişimi sağlamak amacıyla ortaya cıkmış bir servis yapısıdır. Http protokolü ile çalışır. Açılımı Representational State Transfer dır.**

<br>

**2. RESTful Web Servis Nedir?**

- **RESTful Web Servis kısaca özetlemek gerekirse REST prensiplerine göre tasarlanmış web servisi diyebiliriz HTTP metodlarıyla kaynaklarını yöneten bir API'dir GET,POST,PUT,DELETE gibi bir çok metodu kullanır URI ile kaynaklarını tanımlar veri formatı olarak genelde JSON veya XML kullanmaktadır Stateless ve idempotent kurallarına uymaktadır**

<br>

### Çalışma Mantığı:

- **İstemci : kısaca kullanıcya hizmet verir ve veri gösterir işlem yapmaz sadece sunucuda olan veriyi kullanıcıya gösterrir. Web tarayıcısı, mobil uygulama veya başka bir servis olabilir. Örnek olarak Google,Firefox Mobil olarak ise IOS,Android örnek gösterilebilir. Sunucu değişse bile istemci sorunsuz çalışır**

- **Sunucu : Veriyi saklar işler ve istemciye kullanıcıya sunması için ayarlar iş mantığı ve veri yönetiminden sorumludur İstemci bir konuda veri istediğinde ona sunmakla görevli olandır Sunucu DB'den gerekli veriyi çeker ve kullanıcıya gösterir**

- **HTTP Çalışması : RESTful servislerde istemci ile sunucu arasındaki iletişim HTTP üzerinden olur bu yüzden HTTP çok önemli bir rol alır. İlk adım olarak istemci isteği oluşturur ardından URL belirlenir hangi kaynağa erişmek istediğini belirler HTTP metodu ne yapmak istediğini belirtir (GET,POST,DELETE,PUT) İkinci Adımda sunucu isteği alır ve yorumlar URL ve HTTP metoduna göre hangi kaynak olacağının hedefini belirler gerekirse DB'ye erişir veya iş mantığını çalıştırır Üçüncü Adımda ise sunucu reponse(yanıtı) gönderir Örn: HTTP statü kodu vs..**

- **DİPNOT : RESTful servisler stateless çalışır. Her HTTP isteği bağımsızdır, sunucu önceki isteği hatırlamaz. Yani Sunucu, istemcinin daha önce ne yaptığını bilmez; gerekli tüm bilgiyi her istekte istemci gönderir. HTTP isteği sunucuya "Ben bunu yapmak istiyorum." demesidir ancak Stateless sunucu öncekileri hatırlamaz her istek bağımsızdır** 

</details>

<details>

<summary><strong>JSON veri formatı ve kullanım amacı</strong></summary> 

### JSON Nedir ve Kullanım Amaçları Nelerdir? 
 
- **JSON'un açılımı JavaScript Object Notation demektir Amacı ise veriyi insan ve makine tarafından okunabilir şekilde taşımak. Çoğu programlama dili tarafından kolaylıkla anlaşılabilmektedir metin tabanlı ve hafif bir formata sahiptir JSON bir dosya veya bir kod değildir verileri depolamak veya aktarmar, iletmek gibi amaçlarla kullanılan basit bir formattır. JSON genellikle WEB uygulamaları ve sunucular arasında veri göndermek için kullanılır. Birçok dilde özellikle popüler olan C#,Python,Kotlin,PHP,Javascripit gibi bir çok dilde anlaşılmasını basitleşriri makinelerin ve insanların okumasını sağlayarak kodu veya dosyayı evrenselleştirir.**

### 🟠 JSON Veri Örneği:

```
{
  "id": 101,
  "name": "Bruce Wayne",
  "email": "bruce@example.com",
  "isActive": true,
  "age": 25,
  "skills": ["JavaScript", "Python", "HTML"],
  "address": {
    "street": "Batcave.",
    "city": "Gotham City",
    "zip": "34000"
  }
```

### Açıklaması : 

- **"id": 101, Number tipindedir Kullanıcıya verilen numara**
- **"name": "Bruce Wayne", String tipinde. Kullanıcının Adı ve Soyadı**
- **"email": "bruce@example.com", String tipinde. Kullanıcının Emaili**
- **"isActive": true, Boolean tipinde. Kullanıcının hesabı aktif mi, değil mi.**
- **"age": 25, Number tipinde, Kullanıcının Yaşı**
- **"skills":("Javascript", "Python", "HTML"), Array tipinde Kullanıcının özellikleri ve bildiği diller.**
- **"adress":Object (iç içe nesne). Kullanıcının adres bilgilerini kapsar: "Street": "Batcave" "City": "Gotham City" "Zip": "3400"**
</details>

<details>

<summary><strong>SOAP ve GraphQL nedir Rest'ten Farkları.</strong></summary>

### API Protokol Türleri Nelerdir?:

- **API (Application Programming Interface – Uygulama Programlama Arayüzü), uygulamaların birbirleriyle veri alışverişi yapmasını sağlayan bir köprüdür. Ancak tüm API’ler aynı şekilde çalışmaz; farklı protokoller ve standartlar kullanırlar. Bu nedenle API’ler çeşitli türlere ayrılır.**

### 1. REST API (Representational State Transfer)

- **HTTP protokolü üzerine kurulmuş, veri alışverişini genellikle JSON veya XML formatında gerçekleştiren API türüdür. Stateless bir duruma sahiptir yani kullanıcının durumunu saklamaz CRUD (Create, Read, Update, Delete) işlemleri için uygundur Basit, esnek ve yaygın kullanılır **

### 2. SOAP API (Simple Object Access Protocol)

- **Türkçesi Basit Nesne Erişim Protokolü, dağıtık yapıda bulunan web servislerinin iletişimi gerçekleştirmek üzere kullanılan Sunucu XML tabanlı, sıkı kurallara sahip, güvenli veri transferi sağlayan API türüdür. Daha fazla güvenlik ve hata yönetimi sağlar Kurumsal ve banka uygulamalarında tercih edilir Katı kuralları**

### 3. GraphQL API 

- **Facebook tarafından geliştirilen bu API açık kaynaklı bir veri sorgulama ve işleme dili ve bu sorguları yerine getirmek için yazılmış bir uygulamadır istemcinin veriyi tam anlamıyla çekmesini sağlar. Esnek ve istemciye özel bir veri sunar Fazla veya eksik veri çekme derdi yoktur İstemci “hangi alanları istiyorum” diye sorgu yazar. Veri JSON olarak response yapar**


---

### Arasındaki Farklar ve Detaylar:

# SOAP, REST ve GraphQL Karşılaştırma Tablosu

| Özellik             | SOAP                                | REST                                | GraphQL                              |
|---------------------|-------------------------------------|-------------------------------------|---------------------------------------|
| Protokol            | Katıdır XML tabanlı mesajlaşma     | HTTP üzerinden JSON/XML destekler   | Tek endpointi vardır genelde JSON      |
| Veri Formatı        | XML                                | JSON, XML, YAML, Text               | JSON                                  |
| Esneklik            | Katı kurallı                       | Daha esnek                          | Çok esnek, sadece istenilen veri gelir|
| Performans          | Görece yavaş (XML + fazlalık)      | Orta seviye                         | Yüksek (gereksiz veri yok)            |
| Güvenlik            | WS-Security, yüksek güvenlik       | HTTPS, OAuth, JWT gibi ek çözümler  | HTTPS, JWT gibi çözümler              |
| Kullanım Alanı      | Bankacılık, finans, devlet sistemleri | Web servisleri, mobil API’ler      | Modern web ve mobil uygulamalar    |
| Öğrenme Eğrisi      | Zor                                | Orta                                | Başlangıçta zor ama esnek             |
</details>

<br>
<br>

## 🖨 ASP.NET

<details> 

<summary><strong>ASP.NET ve ASP.NET Core nedir? Avantajları, farkları</strong></summary>

### ASP.NET Nedir?

- **Microsoft’un geliştirdiği bir web uygulama çatısı (framework). 2002’den itibaren .NET Framework üzerine inşa edilmiştir. C#, VB.NET gibi dillerle çalışır WEB Forms, MVC, Web API gibi farklı mimarileri destekler. Yalnızca Windows üzerinde çalışır. Avantajları sırasıyla Visual Studio ile güçlü geliştirme ortamı sunmaktadır. Hazır kütüphanesi ve kontrolleri sayesinde çok tercih edilir Geniş topluluk ve uzun yıllar kullanılmış olmanın tecrübesi vardır**

<br>

### ASP.NET Core Nedir?

- **Microsoft’un 2016’da çıkardığı yeni nesil ASP.NET sürümüdür. Baştan sıfırdan yazılmıştır ancak açık kaynak ve platform bağımsızdır. Windows, Linux, macOS üzerinde çalışabilir. Hem web uygulamaları hem RESTful API’ler geliştirmek için kullanılır. Daha hafif, hızlı ve modülerdir. Avantajları sırasıyla Cross platform olmasıASP.NET’e göre çok daha hızlı olması İhtiyacın olan paketleri NuGet'ten ekleyebilmek gereksiz yük yok. GitHub'ta oldukça topluluk katkısı bulunmakta**


# ASP.NET vs ASP.NET Core — Karşılaştırma Tablosu

---

## Karşılaştırma Tablosu

| Özellik            | ASP.NET (.NET Framework) | ASP.NET Core                                            |
| ------------------ | ------------------------ | ------------------------------------------------------- |
| **Çıkış Yılı**     | 2002                     | 2016                                                    |
| **Çalışma Ortamı** | Sadece Windows           | Windows, Linux, macOS                                   |
| **Performans**     | Daha ağır                | Çok daha hızlı ve hafif                                 |
| **Açık Kaynak**    | Hayır                    | Evet                                                    |
| **Mimari**         | Monolitik                | Modüler                                                 |
| **Sunucu**         | IIS’e bağımlı            | Kendi Kestrel sunucusu var; IIS/NGINX/Apache ile uyumlu |
| **Gelecek**        | Yeni özellikler sınırlı  | Microsoft’un odak noktası, aktif gelişiyor              |

---

</details>

<details> 

<summary><strong>MVC nedir, ne için kullanılır?</strong></summary>

### MVC Nedir?

- **MVC aslında yazılım geliştirmede kullanılan bir mimari desendir (Model – View – Controller). Özellikle web uygulamaları ve masaüstü yazılımlarında tercih edilir. Amacı, uygulamanın farklı sorumluluklarını ayırarak daha düzenli, bakımı kolay ve test edilebilir bir yapı kurmaktır.  MVC 3 katmandan oluşmaktadır ve katmanları birbirinden bağımsız (birbirini etkilemeden) olarak çalışmaktadır.**

- **Model : Uygulamanın veri katmanıdır. Veritabanı işlemleri, iş kuralları, veriyle ilgili mantık burada bulunur ve veri erişim (data access) işlemleri de bu bölümde gerçekleştirilmektedir.**

- **View : Kullanıcıya gösterilen arayüzdür. HTML, CSS, JavaScript (veya başka UI teknolojileri) bu kısımda yer alır. İşin sadece “gösterme” kısmıyla ilgilenir. Front-End olarak çalışır. Bu bölümde projenin kullanıcılara sunulacak olan HTML dosyaları gibi şeyler görünür.**,

- **Controller : Kullanıcıdan gelen istekleri karşılar. İstekleri Model ile View arasında köprü görevi görerek yönetmektedir Örneğin Bir kullanıcı form doldurup gönderdiğinde, controller bu isteği alır, Model’e gönderir, işlenmiş veriyi View’a iletir.**

<br>

### MVC Ne İçin Kullanılır?

- **MVC Başlıca Kodun daha düzenli olması her şey tek yerde değil, ayrı ayrı katmanlarda. Bakım kolaylığı sağlar Test edilebilirliği artırır yeniden kullanabilirlik sağlar Web geliştirmede: ASP.NET MVC, Django (Python), Ruby on Rails, Spring MVC (Java).Masaüstü uygulamalarda: JavaFX, bazı .NET WPF projelerinde sık sık görülür.**

</details>
