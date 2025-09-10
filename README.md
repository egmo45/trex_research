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
 **Kısacası:**  
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

**Kısacası:**
-Komutu çalıştırdığında klasör içinde .git adında gizli bir klasör oluşturulur.
- Bu klasör, değişiklik geçmişini ve versiyonları saklar. 

---


###  Nerede Kullanılır?
-  git **init** aslında komut satırında (terminalde/komut isteminde) kullanılan bir komuttur. “Make Directory” kısaltmasıdır ve yeni klasör (dizin) oluşturmak için kullanılır.

 Windows’ta:

- cmd (Komut İstemi) veya PowerShell açıp yazılabilir.

Linux / MacOS’ta:

- Terminal açıp yazılabilir.



###  Kısacası
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



**Kısacası:**
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



**Kıcasası:**
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

**Kısacası:** 

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

**Kısacası:** 

- Eğer uzak depoda yeni değişiklikler varsa, önce git pull ile güncelleme alman gerekebilir.
- origin → uzak depo (remote) adı main → hangi branch’e göndereceğiniz



**Kısacası:** 

- Yerel değişiklikleri commit ettikten sonra push yapabilirsiniz.
- Eğer uzak depoda yeni değişiklikler varsa, önce git pull ile güncelleme alman gerekebilir.
- Push yaparken hangi branch’e göndereceğini belirtmelisin.

###  🟠 Örnek: 

</details>
