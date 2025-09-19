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

<summary><strong>Platformlar arası çalışabilir mi? (Windows, Linux, macOS)</strong></summary>

- **1. .NET Framework vs .NET Core vs .NET 5+**

- **.NET Framework: Sadece Windows için tasarlanmıştır. Windows uygulamaları (WPF, WinForms, ASP.NET Web Forms) çalıştırır.**

- **.NET Core: Microsoft’un platformlar arası çözümüdür. Windows, Linux ve macOS üzerinde çalışabilir. ASP.NET Core, konsol uygulamaları, web API’ler oluşturmak için uygundur.**

- **.NET 5, 6, 7, 8… (modern .NET): .NET Core’un devamı niteliğindedir ve tamamen platformlar arasıdır. Yeni projelerde tercih edilir.**

</details>



<details>

 <summary><strong>Ek Maddeler</strong></summary>

## Senkron Programlama: 

- **Senkron programlama, bir işlem tamamlanmadan diğer işlemlerin başlamamasını gerektiren bir programlamadır. Bu tür bir programlama tarzında, bir işlem veya görev diğerlerinin önünde olmalı ve bu işlem tamamlanana kadar diğer işlemler beklemelidir. Bu durum, işlemlerin belirli bir sıraya göre gerçekleştirilmesini sağlar. Yani bir işlem tamamlanmadan diğer bir işleme geçiş olmaz. Ayrıca dezavantaj olarak bir işlem uzun sürerse, diğer işlemler onun tamamlanmasını beklemek zorunda kalır. Bu da programın genel performansını olumsuz etkileyebilir.**

**Çalışma şekli Runtime (CLR): .NET uygulaması, Common Language Runtime üzerinde çalışır. .NET Core ve sonrası için bu runtime platform bağımsızdır. SDK ve Tooling: .NET CLI (dotnet build, dotnet run) ile aynı kod Windows, Linux ve macOS’ta derlenip çalıştırılabilir.**

### Kısaca özetlersek:

- **Windows için .NET Framework → Sadece Windows**

- **.NET Core / modern .NET → Platformlar arası (Windows, Linux, macOS)**

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

## 3. 🗄️ Backend Geliştirme Temelleri


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

## 4. 🖨 ASP.NET

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

<details>





<summary><strong>Middleware nedir, nasıl çalışır?</strong></summary>

### Middleware nedir?

![1__DMAUqUzSweBvJBY5C_q0Q](https://github.com/user-attachments/assets/bde0786f-5007-459c-a8c1-0dbd30ac9b24)

- **Basit bir web uygulamasında, istemciden gelen request’e karşılık olarak response gönderilmektedir Temel görevi, verilerin veya işlemlerin uçtan uca doğrudan gitmek yerine bu “ara katmandan” geçerek belirli kurallar, kontroller veya ek işlevlerden geçirilmesini sağlamaktır. Middleware uygulama ile donanım/sistem servisleri arasında çalışarak mesajlaşma, veri tabanı erişimi, dosya sistemine erişim gibi işlemleri kolaylaştırır. Birden fazla middleware arka arkaya çalışabilir (pipeline). Her biri gelen veriyi işleyebilir, değiştirebilir ya da sonraki adıma iletebilir. İstek cevap akışına bağlı olduğu için her türlü yazılım programında karşımıza çıkmaktadır.**



### Nasıl Çalışır?

![1_Cd1pj5NUN-3pz56nMzpNCQ](https://github.com/user-attachments/assets/7c847735-bc1e-45a6-97f1-822708b1e1ec)

<br>

- **Middleware’i gösterebilmek için basit bir loglama işlemi yapılır. Bir Web API projesi açılması gerekmektedir adım adım çalışması ve yazılması gerekmektedir. Önce istek(Request) sonra cevap(Response) gelir Kullanıcı tarayıcıdan veya istemciden bir istek gönderir İstek, uygulamanın ana iş mantığına (controller, handler) ulaşmadan önce bir dizi middleware’den geçer. İsteği inceleyebilir,durdurabilir,değiştirebilir,bir sonraki isteğe yönlendirebilir. Son middleware ise response oluşturur geri dönüş yolunda tekrar bütün middlewarelarden geçer üstüne yine birşeyler eklenip değiştirlebilir**

</details>


<details> 

<summary><strong>Dependency Injection (DI) nedir, neden önemlidir?</strong></summary>

### Depency Injection (DI) Nedir?

- **yazılım geliştirmede kullanılan bir tasarım desenidir. Amacı, bir sınıfın ihtiyaç duyduğu (bağımlı olduğu) nesneleri kendi içinde oluşturmaması, bunun yerine dışarıdan sağlanmasıdır. IoC'Yi uygulamak için kullanılan bir tasarım modelidir yani Design Pattern'dir Bağımlılıkların taklit edilmesine veya ortadan kaldırılmasına olanak tanıdığından test için çok yararlı bir tekniktir. Bağımlılığı azaltır Sınıflar birbirine sıkı sıkıya bağlı olmaz.Kodlar farklı ortamlarda tekrar tekrar kullanılabilmektedir Nesne dışarıdan (constructor, setter ya da method aracılığıyla) sağlanır. Böylece sınıf bağımlılıkları bilmez, sadece kullanır.**

### Neden Önemlidir?

- **DI Yazılım Dünyasında çok önemlidir, Çünkü kodlara esneklik test edilebilirlik ve sürdürülebilirlik sunmaktadır sınıflar sıkı sıkıya birbirine bağlanmalar Örneğin gerçek veritabanına bağlanmak yerine, test için sahte bir repository kullanabilir WEB Uygulamaları API'Ler gibi birçok alanda kullanılabilmektedir. Modern frameworklerin (ASP.NET Core, Spring, Angular, Django vb.) çoğu DI üzerine kuruludur. Bu sayede framework’ün sunduğu özellikler (middleware, filtre, controller bağımlılıkları) otomatik çözülür.**

### Katmanlar Nelerdir?

- **Yazılım geliştirme sürecinde, sistemlerin okunabilir, bakımı kolay, test edilebilir ve genişletilebilir olması en önemli hedeflerdendir. Bu amaçla en yaygın kullanılan yaklaşımlardan biri katmanlı mimari (layered architecture)dir. Katmanlı mimaride yazılım bileşenleri, belirli sorumluluklara sahip katmanlara ayrılır ve bu katmanlar arasında belirlenmiş ilişkiler bulunur. Sırasıyla Sunum Kullanıcıyla doğrudan etkileşim kurar. Verileri ekrana yansıtır ve kullanıcıdan gelen girişleri işler. İş Mantığı (Business Logic) Katmanı Uygulamanın kurallarını, iş akışlarını ve hesaplamalarını barındırır.Sunum katmanından gelen talepleri işler, veri katmanıyla iletişime geçer. Veri Erişim (Data Access) Katmanı Veritabanı veya diğer kalıcı depolama sistemleriyle etkileşime girer.SQL sorguları, ORM (Entity Framework, Hibernate vb.) yapıları burada yer alır. Veri Tabanı (Database) Katmanı Uygulamanın verilerini saklayan en alt katmandır. SQL, NoSQL veya dosya tabanlı olabilir.**


# DI Katmanları Diyagramı - Mermaid

```
mermaid
graph TD
    UI[UI Layer] -->|uses| Service[Service Layer]
    Service -->|depends on via DI| Repository[Repository Layer]
    Repository -->|accesses| Database[(Database)]

    subgraph Dependency Injection
        Service
        Repository
    end
```


###  🟠 DI Kullanımına Örnek: 

// UserService.cs
public class UserService
{
    private readonly INotificationService _notification;

    // Constructor Injection: bağımlılık buradan gelir
    public UserService(INotificationService notification)
    {
        _notification = notification;
    }

    public void Register(string username, string email)
    {
        // Kayıt işlemleri (DB vs.) burada olmalı; örnek için sadece bildirim:
        _notification.Send(email, $"Hoş geldin {username}!");
    }
}
```
```
---
</details>
<br>


## 5. 💾 Veritabanı ve ORM

<details>

<summary><strong>SQL Nedir?</strong></summary>

### SQL Nedir?

- **SQL, Structured Query Language (Yapılandırılmış Sorgu Dili) anlamına gelir. Veritabanlarıyla iletişim kurmak için kullanılan standart bir programlama dilidir. Amacı Veritabanındaki verileri oluşturmak, okumak, güncellemek ve silmek (CRUD: Create, Read, Update, Delete) için kullanılmaktadır.Kullanıldığı yerler: MySQL, PostgreSQL, SQL Server, Oracle gibi ilişkisel veritabanlarında kullanılır. Kısaca SQL, veritabanlarıyla iletişim kurmanın dili diyebiliriz.**



</details>


<details> 

<summary><strong>İlişkisel ve ilişkisel olmayan veri tabanları arasındaki farklar</strong></summary>

### İlişkisel Veritabanı (RDBMS - Relational Database Management System):

- **Veriler tablo (table) yapısında saklanır. Tablolar arası ilişkiler (relationship) tanımlanabilir.**

- **Örnek: MySQL, PostgreSQL, SQL Server, Oracle**

### İlişkisel Olmayan Veritabanı (NoSQL - Not Only SQL):

- **Veriler tablo yapısına bağlı olmadan, farklı formatlarda saklanabilir: belge (document), anahtar-değer (key-value), grafik (graph), sütun (column-family) vb.**

- **Örnek: MongoDB, Redis, Cassandra, Neo4j**


## Arasındaki Farklar Nelerdir:


### Sorgulama:

- **RDBMS: SQL kullanılır, güçlü sorgulama ve join yetenekleri vardır.**
NoSQL: SQL yerine API veya özel sorgu dili kullanılır (MongoDB → Mongo Query, Redis → komutlar).

### Ölçeklenebilirlik 

- **RDBMS: Dikey ölçeklenebilir (daha güçlü sunucu eklenir)**
- **NoSQL: Yatay ölçeklenebilir (sunucu sayısı artırılır)**

### Kullanım Alanları

- **RDBMS: Bankacılık, muhasebe, stok yönetimi, müşteri ilişkileri gibi yapısal ve tutarlı veriler.**
- **NoSQL: Sosyal medya, büyük veri, gerçek zamanlı veri, esnek içerik yönetimi.**

</details>

<details>

<summary><strong>ORM nedir? Entity Framework Core nedir?</strong></summary>

### ORM Nedir?

- **ORM, nesne yönelimli programlama (OOP) ile ilişkisel veritabanı (RDBMS) arasındaki köprüdür. Amaç Veritabanındaki tabloları sınıflar ve nesneler ile temsil etmek ve SQL yazma ihtiyacını azaltmaktır. SQL sorgularını doğrudan yazmak zorunda kalmazsınız Kod ile veritabanı arasında uyum sağlar CRUD işlemleri daha kolay ve hızlı yapılır Ancak Karmaşık sorgularda performans düşebilir ORM öğrenmek başlangıçta biraz zaman alabilir.**

### Entity Framework Core Nedir?


- **Microsoft tarafından geliştirilen, .NET için modern ORM aracıdır. Platformlar arası çalışır (Windows, Linux, macOS) Code-First ve Database-First yaklaşımlarını destekler LINQ (Language Integrated Query) ile veritabanı sorgulama sağlar Migration desteği ile veritabanı değişikliklerini yönetir Entity Framework Core: .NET için güçlüdür**




</details>


<details>

<summary><strong>LINQ nedir? En çok kullanılan LINQ ifadeleri</strong></summary>

### LINQ nedir?

- **LINQ (Language Integrated Query), yani Dil Entegre Sorgulama, .NET ortamında veri sorgulama ve işleme işlemlerini programlama dili içinde yapmamızı sağlayan bir özelliktir. LINQ sayesinde SQL benzeri sorguları C# veya VB.NET kodu içinde yazabilirsiniz, veritabanı, koleksiyon veya XML fark etmez. Başlıca temel özellikleri (Type-Safe) Hataları derleme zamanında yakalar. Birleşik sözdizimi Farklı veri kaynakları için aynı yöntemle sorgulama yapılabilir (veritabanı, liste, XML). Okunabilirlik Karmaşık döngüler ve koşullar LINQ ile daha kısa ve anlaşılır olur. ve Deferred Execution (Gecikmeli Çalışma): Sorgular, veriye ihtiyaç olana kadar çalıştırılmaz; performansı artırır.**


### En Çok Kullanılan LINQ Tipleri 

 **1. Where**

- **Ne yapar: Filtreleme yapar, belirli bir koşulu sağlayan öğeleri seçer.**

**2. Select**

- **Ne yapar: Koleksiyondan istediğiniz alanları seçer veya projeksiyon yapar.**

**3. OrderBy / OrderByDescending**

- **Ne yapar: Verileri artan veya azalan sırada sıralar.**

**4. First / FirstOrDefault**

- **Ne yapar: Koşulu sağlayan ilk öğeyi döndürür. Eğer yoksa:  First() → hata verir FirstOrDefault() → null veya varsayılan değer döner**


**5. . Single / SingleOrDefault**

- **Ne yapar: Sadece tek bir öğe döndürür. Birden fazla varsa hata verir.**



**6. Any**

- **Ne yapar: Koleksiyonda koşulu sağlayan öğe var mı kontrol eder**



**2. All**

- **Ne yapar: Tüm öğelerin belirli koşulu sağlayıp sağlamadığını kontrol eder.**


**7. Count**

- **Ne yapar: Koleksiyondaki öğe sayısını döndürür, koşul ile birlikte kullanılabilir.**


**8. GroupByr**

- **Ne yapar: Öğeleri belirli bir anahtara göre gruplar**


</details>

<details>

<summary><strong>Code-First ve Database-First yaklaşımı nedir?</strong></summary>

### Code-First (Kod Öncelikli) Yaklaşımı

- **Önce uygulama kodu yazılır; veritabanı bu koddan otomatik olarak oluşturulur. Kullanım Alanı daha çok yeni projelerde, veritabanı henüz yoksa veya kod odaklı geliştirme yapılırken tercih edilmektedir. Kod ile veritabanı arasında tam kontrol sağlar Migration (göç) desteği ile veritabanı versiyonları kolay yönetilir Test ve geliştirme süreçleri daha hızlıdır Ancak Karmaşık veritabanı yapılarında manuel ayarlamalar gerekebilir**

### Database-First (Veritabanı Öncelikli) Yaklaşımı

- **Önce var olan veritabanı tasarlanır; uygulamadaki sınıflar ve ORM modelleri veritabanından türetilir. Kullanım Alanı mevcut veritabanlarıyla çalışırken Kurumsal sistemlerde, büyük ve karmaşık tablolar mevcutsa kullanılmaktadır. Mevcut veritabanını hızlı bir şekilde uygulamaya adapte eder, Karmaşık tablolar ve ilişkiler için uygundur. Ancak Kod tarafında değişiklik yapmak daha zordur ve Migration yönetimi sınırlıdır**

### 🟠 Code-First vs DB-First karşılaştırması 

```
mermaid
graph LR
    subgraph Code-First
        A[Uygulama Sınıfları] -->|Migration| B[Veritabanı Oluşturulur]
        B --> C[CRUD İşlemleri]
    end

    subgraph Database-First
        D[Mevcut Veritabanı] -->|Reverse Engineering| E[Uygulama Sınıfları]
        E --> F[CRUD İşlemleri]
    end


### Açıklama:
- **Code-First:** Önce **kod yazılır**, migration ile veritabanı oluşturulur. Yeni projeler için uygundur.  
- **Database-First:** Önce **var olan veritabanı** vardır, sınıflar veritabanından türetilir. Mevcut projelere entegrasyon için uygundur.  
```
---

</details>

<details>

<summary><strong>Temel SQL sorguları: SELECT, INSERT, UPDATE, DELETE</strong></summary>

### SELECT:

- **Ne işe yarar: Veritabanındaki tablolardan veri okumak/sorgulamak için kullanılır.**
 
```
**SELECT column1, column2 
FROM TableName 
WHERE condition 
ORDER BY column;**
```

### INSERT:

- **Ne işe yarar: Tablolara yeni veri eklemek için kullanılır. **

```
INSERT INTO Users (Name, Age) 
VALUES ('Ahmet', 25);
```

### UPDATE:

- **Ne işe yarar: Tablolardaki mevcut veriyi güncellemek için kullanılır.**

```
UPDATE Users 
SET Age = 26 
WHERE Name = 'Ahmet';
```

### DELETE:

- **Tablolardan veri silmek için kullanılır.**

```
DELETE FROM Users 
WHERE Name = 'Ahmet';
```

</details>

<br>

## 6. 🛡 Güvenlik ve Performans

<details>

<summary><strong>Authentication vs Authorization nedir?</strong></summary>

### Authentication (Kimlik Doğrulama) Nedir?

- **Bir kullanıcının gerçekten iddia ettiği kişi olup olmadığını doğrulama işlemidir. Amacı Sisteme giriş yapan kişinin kimliğini teyit etmetir. Kullanıcı adı ve şifre ile,Tek seferlik kod (OTP) ile,Biyometrik doğrulama (parmak izi, yüz tanıma) ile yapılabilmektedir. Örnek Kullanıcı username: Mehmet, password: 1234 ile giriş yapıyor. Sistem bu bilgileri kontrol ediyor ve doğruysa kullanıcıyı doğruluyor.**

### Authorization (Yetkilendirme) Nedir?

- **Kimliği doğrulanan bir kullanıcının hangi kaynaklara veya işlemlere erişebileceğini belirleme işlemidir. Amacı Kullanıcının sisteme erişim haklarını kontrol etmek. Rol tabanlı yetkilendirme (Admin, User, Guest) İzin tabanlı yetkilendirme (Read, Write, Delete) yapılabilmektedir. Örnek Kullanıcı kimliği doğrulandıktan sonra sadece kendi profilini görebiliyor, ama başka kullanıcıların verilerini göremiyor. Admin rolündeki kullanıcı tüm verilere erişebiliyor.**

</details>

<details>

<summary><strong>JWT (JSON Web Token) nedir, nasıl çalışır?</strong></summary>

### JWT (JSON Web Token) Nedir?

- **JWT (JSON Web Token) modern web uygulamalarında kimlik doğrulama (authentication) ve yetkilendirme (authorization) için kullanılan, güvenli bilgi taşıyan, JSON tabanlı bir token formata verilen isimdir. Stateless (durumsuz) çalışır Sunucuda oturum (session) bilgisi tutmaya gerek yoktur.İstemciye verilen token ile her istek doğrulanır. Hem kimlik doğrulama (login) hem de yetkilendirme (rol/izin kontrolü) için kullanılır. Genellikle API güvenliği için tercih edilir.**


### JWT (JSON Web Token Nasıl Çalışır? 

- **JWT 3 parçadan oluşur ve . ile ayrılır: xxxxx.yyyyy.zzzzz. Önce Kullanıcı login olur. Sunucu doğru kimlik bilgilerini doğrular ve kullanıcıya bir JWT token üretip gönderir ve Kullanıcı bu token’ı her isteğin Authorization header’ında taşır. Sunucu gelen token’ı doğrular → Eğer geçerliyse kullanıcıya erişim izni verir. Platform bağımsızdır JSON destekleyen her yerde kullanılabilir. Dağıtık sistemler için uygun (özellikle microservices). Token içindeki payload şifreli değil, sadece encode edilir hassas bilgi tutulmamalıdır. Token süresi dolana kadar iptal edilemez. (stateless yapısından dolayı)**

**Header:** 

- **Algoritma ve token tipi bilgilerini içerir. Örneğin "alg": "HS256", "typ": "JWT"**

**Payload(Yük)**

- **Kullanıcıya ait bilgiler (id, rol, kullanıcı adı vs.) bulunur. Gizli değildir, base64 ile encode edilir. Örnek "userId": 1,  "name": "Fatih",  "role": "Admin",  "exp": 1734567890** 

**Signature (İmza)**

- **Header + Payload + Gizli Anahtar ile oluşturulur. Token’ın değiştirilmediğini garanti eder.**

</details>
 

<details>

<summary><strong>OAuth, OAuth2.0, OpenIddict, OpenID nedir? Aralarındaki ilişki</strong></summary>

### OAuth: 

- **Kullanıcının şifresini paylaşmadan, üçüncü taraf uygulamalara kendi hesabına sınırlı erişim vermesini sağlayan yetkilendirme protokolüdür. Mesela Bir siteye “Google hesabınla giriş yap” dediğinde, o siteye şifreni vermezsin; sadece Google hesabındaki belirli bilgilere erişim izni verirsin.**

### OAuth 2.0:

- **OAuth’un geliştirilmiş, günümüzde en yaygın kullanılan versiyonudur. Daha güvenli, daha esnek ve daha çok senaryoyu destekler. OAuth2 bir kimlik doğrulama (authentication) protokolü değil, yetkilendirme (authorization) protokolüdür.**

### OpenIddict:


- **NET ekosisteminde kullanılan, OAuth2.0 ve OpenID Connect protokollerini kolayca uygulamaya yarayan bir açık kaynak kütüphanedir. .NET Core / ASP.NET Core uygulamalarıyla uyumludur JWT (JSON Web Token) desteği bulunmaktadır. Authorization Server kurmak için kolay bir çözüm**

### OpenID:

- **Kimlik doğrulama (authentication) standardıdır. Kullanıcının tek bir hesapla (Google, Facebook, Microsoft vs.) başka sitelere giriş yapmasını sağlar. Mesela Kullanıcının tek bir hesapla (Google, Facebook, Microsoft vs.) başka sitelere giriş yapmasını sağlar. Forum sitesine üye olurken “Google ile giriş yap” seçeneğini tıklarsın. Burada OpenID devreye girer ve senin gerçekten sen olduğunu doğrular.**

 
### Aralarındaki İişkiler Nelerdir?

- **OAuth Yetkilendirme için çıktı. Anacı kullanıcının şifresini paylaşmadan, üçüncü taraf uygulamaya sınırlı erişim vermesini sağlamaktır. Ama sadece yetkilendirme yapar. Kullanıcının kim olduğunu doğrulamaz.**
 
- **OAuth 2.0  OAuth’un geliştirilmiş sürümüdür. Daha güvenli, daha esnek, modern sistemlere uygundur. Günümüzde “OAuth” dendiğinde aslında OAuth2.0 kastedilir.**

- **OpenID Kimlik doğrulama için çıktı. "Sen kimsin?" sorusuna cevap verir. Kullanıcının bir kimlik sağlayıcısı (Google, Microsoft vs.) üzerinden giriş yapmasını sağlar. OAuth ile birlikte kullanılabilir.**

- **OpenID Connect (OIDC)  Aslında OpenID + OAuth 2.0 birleşimidir. Modern sistemlerde kullanılan standarttır. OAuth2.0’ın yetkilendirme gücü + OpenID’nin kimlik doğrulama gücünü birleştirir. Günümüzde Google, Facebook, Microsoft login mekanizmaları aslında OpenID Connect kullanır.**

- **OpenIddict .NET dünyasında uygulaması. ASP.NET Core uygulamalarında OAuth2.0 + OpenID Connect protokollerini kolayca kullanmamızı sağlar. Yani bir "kütüphane / framework"tür, protokol değildir.**

### Kısaca : 

- **OAuth: Yetki (izin)**

- **OAuth 2.0: Modern OAuth**

- **OpenID: Kimlik (login)**

- **OpenID Connect: OAuth 2.0 + OpenID → Hem kimlik hem yetki**

- **OpenIddict: .NET için OIDC’nin implementasyonu**

</details>

<details>

<summary><strong>Performans artımı için ne yapılabilir? (AsNoTracking, IAsyncEnumerable, caching, profiling, redis)</strong></summary>

- **AsNoTracking: EF Core sorgularında değişiklik takibini (Change Tracking) devre dışı bırakır. Okuma amaçlı sorgularda (readonly) ciddi performans kazancı sağlar. Okuma ağırlıklı sorgularda EF Core’un değişiklik takibini kapat — bellek ve CPU kazanırsınız. : Veri üzerinde güncelleme yapmayacaksanız, ya da DTO’lara projekte edeceksen kullanmalısınız.
Dikkat: Daha sonra aynı nesneyle Update yapmak isterseniz önce Attach etmeniz gerekir.**

- **IAsyncEnumerable (await foreach): Büyük sorguları belleğe tamamen yüklemeden, parça parça asenkron tüketmeyi sağlar. Bellek kullanımı düşer ve pipeline tarzı işlem yapılırsa gecikme azalır. üyük tabloları işlerken OutOfMemory riskini azaltmaktadır. Ancak Veritabanı bağlantısı açık kalır; uzun işlemlerde timeout, bağlantı poolu etkilenebilir.**

- **Caching (MemoryCache, Distributed Cache, Redis): Cache-Aside (lazy): Önce cache kontrol et, yoksa DB’den çek, cache’e yaz. Write-through / Write-behind: Yazma işlemlerinde cache’i de güncelle. Expiration: Absolute vs sliding expiration. Redis avantajı oldukça etkilidir Çoklu sunucu/instance ortamında paylaşılan cache, yüksek performans sunar. Ancak Dikkat Cache invalidation (güncelliği sağlama) zor iştir doğru strateji, kısa TTL veya event ile temizleme.lidir**

- **Profiling : Amacı Gerçek darboğazı bulmak (DB, CPU, I/O, GC, ağ). Adımlar: Uygulama seviyesinde logging: EF Core SQL loglarını aç, yavaş sorguları yakala. SQL Profiler / PG tools: Sorgu planlarını, uzun süren sorguları, missing index problemlerini incele. NET Profiling: dotnet-trace, dotnet-counters, PerfView, Visual Studio Profiler, MiniProfiler. Load test: Kestirme testleri (k6, Apache Bench) ile gerçek dünya yükünü simüle et. Metrikler: Response time, CPU, memory, GC, DB latency, connection pool usage.**

- **5) Redis : Kullanım şekli çoktur: Distributed cache (cache aside), Session state (scale-out), Rate limiting / throttling, Pub/Sub (event dağıtımı), Short lived token veya temporary data vb. Redis verileri RAM’de tutar, bu yüzden çok hızlıdır (disk tabanlı veritabanlarına göre kat kat daha hızlı). In-memory çalışır: Veriler RAM’de tutulur → mikro saniye seviyesinde erişim sağlar. Key-Value Store’dur: Veri anahtar-değer çiftleri şeklinde saklanır.**

### Peformans İçin Önerilenler: 

- **Query-level optimizasyon — İndeksler ve Projection Veritabanı sorgularının çalışmasını hızlandırır; sorguların doğru sütunlara indekslenmesiyle full table scan’ler önlenir. SELECT * yerine sadece ihtiyaç duyulan sütunları (Select) çekmek I/O’yu azaltır.**

- **Sık okunan ve nadiren değişen veriyi bellekte tutarak DB çağrılarını ve gecikmeyi azaltır. Cache-aside (önce cache, yoksa DB, sonra cache’e yaz) en yaygın pattern’dır. Listeleme, ürün kataloğu, sık tekrar edilen konfigürasyon/veri için.**

- **EF Core’un değişiklik takibini kapatarak bellek ve CPU kullanımını azaltır; okuma ağırlıklı işlemlerde büyük kazanç sağlar. Veriler sadece okunacak, güncellenmeyecekse (DTO’lara projeksiyon gibi).**



</details>

## Ek:

<details>

<summary><strong>OWASP Top 10</strong></summary>

### Web uygulamalarında en yaygın güvenlik açıkları ve SQL Injection, XSS, CSRF, Broken Auth gibi başlıkların kısa tanımı:

 **Web uygulamalarında en yaygın güvenlik açıkları genelde OWASP (Open Web Application Security Project) tarafından listelenir. Bunlar geliştiricilerin en çok dikkat etmesi gereken, saldırganların en sık kullandığı zafiyetlerdir.**

- **1. SQL Injection (SQLi) Kullanıcıdan alınan veriler doğrudan SQL sorgularına eklenirse saldırgan veritabanına yetkisiz erişebilir. Kullanıcıdan alınan veriler doğrudan SQL sorgularına eklenirse saldırgan veritabanına yetkisiz erişebilir. Örn: "OR 1=1" gibi sorgu eklemeleriyle veritabanındaki tüm kayıtları çekme.**

- **2. XSS (Cross-Site Scripting) Kullanıcının tarayıcısında kötü niyetli JavaScript çalıştırma. Örn: Yorum alanına <script>alert("hack");</script> yazıp başka kullanıcıların oturum çerezlerini çalma.**

- **3. CSRF (Cross-Site Request Forgery) Kullanıcının haberi olmadan başka bir sitede oturumu kullanarak işlem yaptırma. Örn: Kullanıcı bankasına giriş yapmışken saldırgan linkine tıklatıp para transferi yaptırabilir.**

- **4. Broken Authentication (Kırık Kimlik Doğrulama) Zayıf şifreleme, tahmin edilebilir tokenler, çok faktörlü doğrulama eksikliği. Sonuç: Hesapların ele geçirilmesi.**

- **5. Sensitive Data Exposure (Hassas Veri Sızıntısı) Şifrelerin düz metin saklanması, TLS (HTTPS) kullanılmaması, API anahtarlarının açıkta bırakılması.**


### OWASP Top 10 – 2021

- **Broken Access Control (Yetki Kontrolü Açıkları) Kullanıcıların izin verilmemiş kaynaklara veya işlevlere erişebilmesi.**

- **Cryptographic Failures (Kriptografik Hatalar): Hassas verilerin yanlış ya da zayıf şifreleme ile saklanması veya iletilmesi.**

- **Injection (Enjeksiyon Açıkları): SQL, NoSQL, OS komutları gibi yerlere doğrulanmamış veri enjekte edilerek saldırı yapılması.**

- **Insecure Design (Güvensiz Tasarım): Sistem baştan yanlış tasarlandığı için güvenlik açıklarının doğrudan mimariye gömülü olması.**

- **Security Misconfiguration (Yanlış Güvenlik Yapılandırması): Varsayılan şifrelerin açık bırakılması, gereksiz servislerin çalıştırılması veya eksik güvenlik yamaları.**

- **Vulnerable and Outdated Components (Güvenlik Açığı Olan ve Güncel Olmayan Bileşenler): Eski kütüphaneler, frameworkler veya yazılımlar kullanılması.**

- **Identification and Authentication Failures (Kimlik Doğrulama Hataları): Zayıf şifre politikaları, çok faktörlü kimlik doğrulamanın olmaması veya oturum yönetimi hataları.**

- **Software and Data Integrity Failures (Yazılım ve Veri Bütünlüğü Hataları): İmzalanmamış yazılımların/bağımlılıkların yüklenmesi veya doğrulanmamış güncellemelerin kabul edilmesi.**

- **Security Logging and Monitoring Failures (Loglama ve İzleme Hataları): Güvenlik olaylarının kaydedilmemesi ya da saldırıların fark edilmemesi.**

- **Server-Side Request Forgery – SSRF (Sunucu Taraflı İstek Sahteciliği): Saldırganın, sunucuyu kendi adına başka sistemlere istek göndermeye zorlaması.**


</details>

<details>

<summary><strong>ASP.NET Core ile alınabilecek önlemler (örnek: model validation, input sanitization)</strong></summary>

### ASP.NET Core uygulamalarında güvenlik için alınabilecek önlemler, hem input validation hem de framework seviyesinde yerleşik mekanizmalarla desteklenir. İşte en yaygın ve etkili önlemler:

- **Model Validation (Model Doğrulama) :**

- **Kullanıcıdan gelen verilerin doğru formatta, gerekli alanların dolu ve limitlerin uygun olmasını sağlar. Kullanım: DataAnnotations ile model üzerinde kurallar tanımlanır.**

- **Input Sanitization (Girdi Temizleme) : Kullanıcının gönderdiği verileri zararlı kodlardan (XSS, HTML/JS injection) temizler. Razor view’de @Html.Encode(), veya paketler: Ganss.XSS**

- **Kullanıcının gönderdiği verileri zararlı kodlardan (XSS, HTML/JS injection) temizler. Razor view’de @Html.Encode(), veya paketler: Ganss.XSS**

- **Cross-Site Request Forgery saldırılarını engeller. : Formlar ve API istekleri için token doğrulama.**

- **Authentication & AuthorizationWT veya Cookie Authentication: Kullanıcı doğrulama ve yetki kontrolü sağlar. Policy/Role tabanlı yetkilendirme.**

</details>

<br>

## 7. 📊 Logging ve Hata Yönetimi

<details>

<summary><strong>Neden loglama yapılır? Log seviyesi nedir?</strong></summary>

### Neden loglama yapılır? 

 **Loglama, bir uygulamanın çalışma sürecinde gerçekleşen olayların kaydedilmesi işlemidir ve hem geliştirme hem de üretim ortamlarında kritik öneme sahiptir.**

- **Hata Tespiti ve Debug (Hata Ayıklama) Uygulama beklenmedik şekilde çalıştığında loglar sorunun kaynağını bulmayı kolaylaştırır.**

- **Performans Analizi İşlem sürelerini, yavaş endpoint’leri veya darboğazları izlemeye yardımcı olur.**

- **Güvenlik ve Denetim (Audit Trail) Kullanıcı hareketleri, erişimler, yetkisiz giriş denemeleri loglanarak saldırılar veya uyumluluk ihlalleri takip edilir.**

- **Operasyon ve İzleme Canlı sistemin sağlığı, servis durumları ve uyarılar loglarla takip edilir.**

- **Karmaşık Sistemlerde İzlenebilirlik (Traceability) Mikroservis veya dağıtık sistemlerde isteklerin akışı takip edilebilir.**

### Log Seviyesi Nedir? 

 **Log seviyesi, loglanacak mesajın önem derecesini belirten bir kategoridir.**

- **Trace : En ayrıntılı bilgi; genellikle debug ve geliştirme için.**

- **Debug : Hata ayıklamaya yardımcı detaylı bilgiler.**

- **Information : Normal çalışma sırasında önemli olaylar; örn. kullanıcı girişleri.**

- **Warning : Beklenmeyen durumlar, ama uygulama çalışmasını sürdürür.**

- **Error : Hata oluştu; uygulamanın bazı işlevleri etkilenmiş olabilir.**

- **Critical / Fatal : Kritik hatalar; uygulama çalışamaz veya önemli veri kaybı riski var.**

</details>

<details>

<summary><strong>ASP.NET Core'da logging altyapısı</strong></summary>

###  ASP.NET Core'da Logging Altyapısının İşleyişi : 

 **ASP.NET Core, gelişmiş ve esnek bir logging altyapısı sağlar. Hem framework tarafından hem de uygulama tarafından kullanılabilir ve farklı log sağlayıcılarıyla kolayca entegre edilebilir. İşte detaylar:**

- **Logging Servisi ve Dependency Injection : ASP.NET Core’da ILogger<T> interface’i ile logging yapılır. Servisler ve controller’lar DI (Dependency Injection) ile logger alır.**

- **Log Seviyeleri : ASP.NET Core, logları şöyle seviyelerde kaydedebilir Trace, Debug, Information , Warning, Error, Critical.**

- **Log Provider (Sağlayıcılar) : ASP.NET Core, logları farklı hedeflere gönderebilecek sağlayıcılar sunar: Console, Debugi EventSource/ Eventlog File / Third-Party**

- **Yapılandırma (appsettings.json) : Log seviyelerini ortam veya kategori bazında ayarlayabilirsiniz.**

</details>


<details>

<summary><strong>Global exception handling nasıl yapılır?</strong></summary>

### Middleware ile Global Exception Handling: 

 **Global exception handling, uygulamanın herhangi bir yerinde oluşabilecek hataları merkezi bir noktada yakalayarak yönetmek demektir. Bu, hem uygulamanın çökmesini önler hem de kullanıcıya veya log sistemine anlamlı bilgi göndermeyi sağlar. Global exception handling, uygulamanın herhangi bir yerinde meydana gelen hataların merkezi bir noktada yakalanması ve yönetilmesi sürecidir. Bu yöntemle: Global exception handling’in nasıl yapılacağı kullanılan platforma ve dile bağlıdır. Hadi genel olarak .NET ve JavaScript (Node.js/Express) üzerinden açıklayalım**

### **1. .NET (C#) Global Exception Handling**
- **ASP.NET Core’da**

**ASP.NET Core’da global exception handling için Middleware kullanılır.**

```
public class GlobalExceptionMiddleware
{
    private readonly RequestDelegate _next;
    private readonly ILogger<GlobalExceptionMiddleware> _logger;

    public GlobalExceptionMiddleware(RequestDelegate next, ILogger<GlobalExceptionMiddleware> logger)
    {
        _next = next;
        _logger = logger;
    }

    public async Task InvokeAsync(HttpContext context)
    {
        try
        {
            await _next(context); // Bir sonraki middleware veya request handler çalıştırılır
        }
        catch (Exception ex)
        {
            _logger.LogError(ex, "Unhandled exception occurred");
            context.Response.StatusCode = 500;
            context.Response.ContentType = "application/json";
            await context.Response.WriteAsync(new
            {
                StatusCode = 500,
                Message = "Internal Server Error"
            }.ToString());
        }
    }
}

// Startup.cs veya Program.cs
app.UseMiddleware<GlobalExceptionMiddleware>();

```
### **2. Node.js / Express Global Error Handling**

- **Express uygulamasında global error handler, middleware ile yapılır.**

```
const express = require("express");
const app = express();

app.use(express.json());

// Örnek route
app.get("/", (req, res) => {
    throw new Error("Something went wrong!");
});

// Global error handler middleware
app.use((err, req, res, next) => {
    console.error(err.stack);
    res.status(500).json({
        status: 500,
        message: "Internal Server Error"
    });
});

app.listen(3000, () => console.log("Server running on port 3000"));

```

</details>


<details>

<summary><strong>UseExceptionHandler ve ILogger nasıl kullanılır?</strong></summary>

### UseExceptionHandler ve ILogger nasıl kullanılır?

**1. UseExceptionHandler Nedir? ve Nasıl Kullanılır? : UseExceptionHandler, ASP.NET Core middleware’lerinden biridir ve uygulamada oluşan unhandled exception’ları yakalamak için kullanılır. Bu middleware, hata oluştuğunda kullanıcıya özel bir sayfa veya mesaj göstermenizi sağlar.**

- **Örnek bir controller’da kullanımı:**


```
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (!env.IsDevelopment())
    {
        // Üretim ortamında özel hata sayfası kullan
        app.UseExceptionHandler("/Home/Error");
        app.UseHsts();
    }

    app.UseHttpsRedirection();
    app.UseStaticFiles();
    app.UseRouting();
    app.UseAuthorization();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapControllerRoute(
            name: "default",
            pattern: "{controller=Home}/{action=Index}/{id?}");
    });
}


```

- **2. ILogger Nedir ve Nasıl Kullanılır? : ILogger, ASP.NET Core’un built-in logging framework’üdür. Hataları, uyarıları veya bilgi mesajlarını loglamak için kullanılır.**

- **Örnek bir controller’da kullanımı:**

```

public class HomeController : Controller
{
    private readonly ILogger<HomeController> _logger;

    public HomeController(ILogger<HomeController> logger)
    {
        _logger = logger;
    }

    public IActionResult Index()
    {
        _logger.LogInformation("Index action çağrıldı.");
        return View();
    }

    public IActionResult Error()
    {
        var exceptionFeature = HttpContext.Features.Get<IExceptionHandlerPathFeature>();
        if (exceptionFeature != null)
        {
            _logger.LogError(exceptionFeature.Error, 
                "Hata oluştu: {Path}", exceptionFeature.Path);
        }
        return View();
    }
}

``` 

</details>

<br>

## 8. 📦  Yazılım Geliştirme Prensipleri 

<details>

<summary><strong> SOLID prensipleri </strong></summary>

### 1. S – Single Responsibility Principle (SRP) / Tek Sorumluluk Prensibi :

- **Açıklama: Bir sınıfın yalnızca bir işi yapması ve yalnızca bir sorumluluğu olması gerekir.**

- **Örnek :**

```


//  Sorumlulukları ayır
class ReportSaver
{
    public void SaveReport() { /* kaydet */ }
}

class PDFGenerator
{
    public void GeneratePDF() { /* PDF oluştur */ }
}
```

### 2. O – Open/Closed Principle (OCP) / Açık/Kapalı Prensibi : 

- **Açıklama: Kod geliştirmeye açık, değişikliğe kapalı olmalıdır. Yani mevcut kodu bozmadan yeni özellik ekleyebilmeliyiz.**

- **Örnek :**

```
interface IShape
{
    double Area();
}

class Circle : IShape
{
    public double Radius { get; set; }
    public double Area() => Math.PI * Radius * Radius;
}

class Square : IShape
{
    public double Side { get; set; }
    public double Area() => Side * Side;
}

// Alan hesaplama değişmedi, yeni şekil eklemek kolay
```


### 3. L – Liskov Substitution Principle (LSP) / Liskov Yerine Geçme Prensibi :

- **Açıklama: Türetilmiş sınıflar, temel sınıfın yerine geçebilir ve beklenmeyen hatalara yol açmamalıdır.**

- **Örnek :**

```
class Bird
{
    public virtual void Fly() { }
}

class Eagle : Bird { }
class Ostrich : Bird
{
    public override void Fly() 
    {
        throw new NotImplementedException(); // LSP ihlali
    }
}
```
### 4. I – Interface Segregation Principle (ISP) / Arayüz Ayrımı Prensibi :

**Açıklama: Küçük ve spesifik arayüzler kullan, istemci gereksiz metodlarla yüklenmesin.**

**Örnek :**

```
interface IPrinter
{
    void Print();
    void Scan(); // Tarama gerekmeyen cihazlar için gereksiz
}

// Ayrıştırılmış arayüz
interface IPrinterDevice { void Print(); }
interface IScannerDevice { void Scan(); }
```

### 5. D – Dependency Inversion Principle (DIP) / Bağımlılıkların Tersine Çevrilmesi :

- **Açıklama: Yüksek seviyeli modüller, düşük seviyeli modüllere bağımlı olmamalı, her ikisi de arayüzlere bağımlı olmalı.**

- **Örnek :** 

```
// İyi Örnek
interface ILogger { void Log(string msg); }

class FileLogger : ILogger { public void Log(string msg) { } }

class UserService
{
    private readonly ILogger _logger;
    public UserService(ILogger logger) { _logger = logger; }
}
```
</details>

<details>

<summary><strong>Design Patterns: Singleton, Repository, Factory</strong></summary>

### 1. Singleton Pattern (Tekil Nesne Deseni) Nedir?

- **Bir sınıfın yalnızca bir tane örneğinin olmasını sağlar ve bu örneğe tüm uygulama genelinde erişim imkânı verir.** 

**Ne zaman kullanılır?**

- **Uygulama boyunca tek bir veritabanı bağlantısı olacaksa**

- **Konfigürasyon bilgilerini merkezi olarak yönetmek için**

- **Loglama işlemleri için**

```
public class Logger
{
    private static Logger _instance;
    private Logger() { }

    public static Logger Instance
    {
        get
        {
            if (_instance == null)
                _instance = new Logger();
            return _instance;
        }
    }

    public void Log(string message)
    {
        Console.WriteLine(message);
    }
}
```

### 2. Repository Pattern (Depo Deseni) Nedir?

- **Veri erişimini ve iş mantığını birbirinden ayırır. Uygulama, veri kaynağının nasıl olduğundan bağımsız olarak Repository üzerinden veri ile çalışır.**

**Ne zaman kullanılır?**

- **Veritabanı işlemlerini merkezi bir yerde toplamak istiyorsanız**

- **Kodun test edilebilirliğini artırmak istiyorsanız**

### 3. Factory Pattern (Fabrika Deseni) Nedir?

- **Nesne yaratmayı merkezi bir fabrikaya devreder. Yani hangi sınıfın oluşturulacağına karar vermek fabrikaya bırakılır.**

**Ne zaman kullanılır?**

- **Uygulama içerisinde farklı tipte nesneler yaratmanız gerekiyorsa**

- **Nesne oluşturma süreci karmaşıksa veya bağımlılıkları gizlemek istiyorsanız**

```
public class Logger
{
    private static Logger _instance;
    private Logger() { }

    public static Logger Instance
    {
        get
        {
            if (_instance == null)
                _instance = new Logger();
            return _instance;
        }
    }

    public void Log(string message)
    {
        Console.WriteLine(message);
    }
}
```

</details>

<details>

<summary><strong>Clean Code uygulama örnekleri</strong></summary>

### Clean Code Nedir? 


- **Clean Code (Temiz Kod) prensiplerinin pratik örneklerine bakalım. Bu örnekler, kodun okunabilir, anlaşılır ve bakımı kolay olmasını sağlar.**

- **1. Anlamlı İsimler Kullanmak : Kötü Örnek - int d; // gün sayısı İyi Örnek - int numberOfDays; Değişken, fonksiyon ve sınıf isimleri amacını açıkça belirtmeli.**

- **2. Fonksiyonları Küçük Tutmak** 

- **Örnekler :**

```

## Kötü Örnek :

void ProcessOrder(Order order) 
{
    ValidateOrder(order);
    CalculateDiscount(order);
    SaveOrder(order);
    SendConfirmationEmail(order);
}

İyi Örnek :

void ProcessOrder(Order order) 
{
    ValidateOrder(order);
    ApplyDiscount(order);
    PersistOrder(order);
    NotifyCustomer(order);
}
```

- **Fonksiyonlar tek bir iş yapmalı, birden fazla sorumluluk içermemeli.**

---

- **3. Yorumları Gereksiz Kullanma: **

**Örnekler :**

```

## Kötü Örnek :

// Bu fonksiyon siparişi kaydeder
void SaveOrder(Order order) { ... }

## İyi Örnek :

void PersistOrder(Order order) { ... }
```

- **Kod kendini açıklıyorsa yorum gereksizdir; yorumlar ancak karmaşık iş mantığını açıklamak için kullanılmalı.**

---

- **4. Magic Number’lardan Kaçınmak : **

**Örnekler :**

```
## Kötü Örnek :

if (userAge > 18) { ... }

## İyi Örnek :

const int LegalAge = 18;
if (userAge > LegalAge) { ... }
```

- **Sayılar veya stringler anlamlı sabitlerle ifade edilmeli.**

--- 

- **5. Anlamlı Sınıf ve Fonksiyon Yapısı :**

**Örnekler :**

```
## Kötü Örnek : 

class Utility
{
    void DoSomething() { ... }
    void DoAnotherThing() { ... }
}

## İyi Örnekclass OrderService
{
    void ValidateOrder(Order order) { ... }
    void CalculateDiscount(Order order) { ... }
}
```

- **Sınıflar tek sorumluluk ilkesine (Single Responsibility Principle) uygun olmalı.**
</details>

<details>

<summary>Ek:</summary>

## Yazılım Mimari Desenleri 

### **Layered, Clean Architecture, Microservices, Event-Driven, Hexagonal Architecture (Ports & Adapters) Nelerdir?**

- **1. Layered Architecture (Katmanlı Mimari) Nedir? : Uygulama farklı katmanlara ayrılır; genellikle şu katmanlar vardır: Presentation Layer: Kullanıcı arayüzü ve kullanıcı taleplerini işler. Business/Domain Layer: İş kurallarını ve mantığı içerir. Data Access Layer: Veritabanı veya dış sistemlerle iletişimi sağlar. Özellikleri Kısaca : Katmanlar üstten alta doğru iletişim kurar. Her katman kendi sorumluluğuna odaklanır. Anlaşılır ve standart bir yapı sağlar. Test edilebilir ve yönetimi kolaydır. Ancak Katmanlar arası sıkı bağımlılık büyük projelerde esnekliği azaltır.**

- **2. Clean Architecture (Temiz Mimari) Nedir? : Uygulamanın bağımlılıklarını içten dışa doğru düzenler. Domain (iş mantığı) en merkezde, framework ve dış sistemler en dıştadır Özellikleri Kısaca Domain bağımsızdır, dış sistemlere bağlı değildir. Kod test edilebilir ve sürdürülebilir olur. Uzun ömürlü ve karmaşık projelerde güçlü yapı sağlar. Bağımlılık yönetimi nettir. Ancak Başlangıçta karmaşık ve öğrenme eğrisi yüksektir.** 

- **3. Microservices (Mikroservisler) Nedir? : Uygulama, birbirinden bağımsız çalışan küçük servislerden oluşur. Her servis kendi veritabanına ve iş mantığına sahiptir. Özellikleri Kısaca Servisler birbirinden bağımsızdır. Her servis farklı teknoloji ile geliştirilebilir. Kolay ölçeklenir ve bağımsız deploy edilebilir. Takımların paralel çalışmasını destekler. Ancak Dağıtık sistem karmaşıklığı artar. Servisler arası iletişim ve veri tutarlılığı yönetimi gerekir.**

- **4. Event-Driven Architecture (Olay Tabanlı Mimari) Nedir? : Sistem bileşenleri olaylar (events) üzerinden iletişim kurar. Bir event oluştuğunda ilgili bileşenler bunu dinler ve tepki verir. Özellikleri Kısaca Asenkron iletişim vardır. Bileşenler gevşek bağlıdır Yüksek esneklik ve ölçeklenebilirlik sağlar. Gerçek zamanlı uygulamalar için uygundur. Ancak Hata ayıklama (debugging) zorlaşır. Event sıralama ve yönetimi karmaşık olabilir.**

- **5. Hexagonal Architecture (Ports & Adapters / Altıgen Mimari) Nedir? : Uygulamanın çekirdek domain’i dışa bağımlı değildir. Portlar dış sistemlerle iletişim için tanımlanır, adapterlar ise bu portları uygular. Özellikleri Kısaca Domain merkezlidir. Dış sistem bağımlılıkları soyutlanmıştır. Test edilebilir, değişime dayanıklı bir yapı sağlar. Domain izolasyonu güçlüdür. Ancak Tasarım başta karmaşık görünebilir. Küçük projelerde fazla olabilir.**
</details>

<details>

<summary><strong>Hangi senaryoda hangi mimari tercih edilir?</strong></summary>

### 1. Layered Architecture (Katmanlı) 

- **Tercih Edildiği Senaryolar : Küçük veya orta ölçekli uygulamalar Basit web uygulamaları veya CRUD sistemleri Takımların küçük ve deneyim seviyesinin orta olduğu projeler. Basit ve anlaşılır bir yapı isteyen, karmaşık dağıtık sistem gerektirmeyen projeler için uygun.**

### 2. Clean Architecture (Temiz Mimari) 

- **Tercih Edildiği Senaryolar : Uzun ömürlü ve büyük ölçekli projeler Domain mantığının korunması ve framework bağımsızlığı gereken projeler. Test edilebilirliği ve sürdürülebilirliği öncelikli projeler Karmaşık iş kuralları ve uzun süreli bakım gerektiren enterprise uygulamaları için ideal.**


### 3. Microservices (Mikroservisler) 

- **Tercih Edildiği Senaryolar: Büyük ölçekli sistemler Takımların bağımsız geliştirme ve deploy yapması gereken projeler Yüksek ölçeklenebilirlik ve farklı teknolojilerle servislerin geliştirilmesi gereken projeler. Dağıtık, büyüyen ve bağımsız servislerin kritik olduğu sistemler için uygun.**

### 4. Event-Driven Architecture (Olay Tabanlı) 

- **Tercih Edildiği Senaryolar: Gerçek zamanlı veri işleme gereken sistemler (finans, oyun, IoT) Asenkron ve gevşek bağlı bileşenlerin tercih edildiği sistemler Sistemlerin birbirine bağımlılığının minimum olması gereken durumlar. Olay tabanlı, esnek ve asenkron sistemler için ideal.**

### 5. Hexagonal Architecture (Ports & Adapters / Altıgen)

- **Tercih Edildiği Senaryolar: Domain mantığının dış bağımlılıklardan izole edilmesi gereken projeler Test edilebilirliğin yüksek öncelik olduğu sistemler Farklı dış sistemlerle entegrasyon gereken projeler. Domain izolasyonu ve test edilebilirlik öncelikli orta veya büyük ölçekli projeler için uygundur.**


</details>

