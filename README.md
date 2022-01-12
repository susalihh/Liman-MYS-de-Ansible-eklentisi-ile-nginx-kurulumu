# Liman MYS'de Ansible eklentisi ile NGİNX kurulumu

Ansible eklentisi ile NGINX'in kurulumunu ve Ansible playbook'un nasıl yazılacağını inceleyeceğiz.
Başlamadan önce, Liman'a Ansible eklentisini eklemiş olmamız gerekir.

Ansible eklentisinin kurulum için:
https://dev.to/liman/ansible-yonetim-eklentisi-4ina

Ansible eklentisini başarılı bir şekilde eklediysek nginx kurmaya başlayalım.

**1) Playbook Oluşturma**

Playbook'lar, Ansible'ın yapılandırma, dağıtım ve düzenleme işlevlerini kaydeder ve yürütür. Uzak sistemlerimizin uygulamasını istediğiniz bir politikayı veya genel bir BT sürecindeki bir dizi adımı tanımlayabilirler. 

![](https://github.com/susalihh/Liman-MYS-de-Ansible-eklentisi-ile-nginx-kurulumu/blob/main/img/p1.png)

Playbook sekmesinden "Dosya Oluştur" diyoruz

![](https://github.com/susalihh/Liman-MYS-de-Ansible-eklentisi-ile-nginx-kurulumu/blob/main/img/a2.png)

Dosya Adı: Oluşturacağımız playbook dosyasının ismini giriyoruz.

Dosya İçeriği: Oluşturacağımız playbook dosyasının içeriğini giriyoruz.

```yml
- hosts: all
  become: yes
  tasks:
    - name: ensure nginx is at the latest version
      apt: name=nginx state=latest
    - name: start nginx
      service:
        name: nginx
        state: started
```

**2) Hosts Ayarları**

Ansible, envanter olarak bilinen bir liste veya listeler grubu kullanarak aynı anda altyapıdaki birden çok yönetilen düğüme veya "ana bilgisayara" karşı çalışır. Envanter Ansible'ın karşı karşıya gelmesini istediğimiz ana bilgisayarları veya grupları seçmek için kullanılır. 

![](https://github.com/susalihh/Liman-MYS-de-Ansible-eklentisi-ile-nginx-kurulumu/blob/main/img/p2.png)

Hosts sekmesinde Grup Ekle diyoruz

![](https://github.com/susalihh/Liman-MYS-de-Ansible-eklentisi-ile-nginx-kurulumu/blob/main/img/a4.png)

Clientlarımızı ekleyeceğimiz bir grup adı ekliyoruz.

![](https://github.com/susalihh/Liman-MYS-de-Ansible-eklentisi-ile-nginx-kurulumu/blob/main/img/a5.png)

Daha sonra hosts sekmesinde eklediğimiz grup gözükecektir. Üzerine tıklayıp Client Ekle diyoruz ve client bilgilerini giriyoruz.

**3) Playbook Çalıştırma**

![](https://github.com/susalihh/Liman-MYS-de-Ansible-eklentisi-ile-nginx-kurulumu/blob/main/img/p3.png)

Playbook sekmesinde oluşturduğumuz playbook'un üzerine tıklayıp çalıştırabiliriz veya sağ tıklayıp görüntüleme, düzenleme, çalıştırma ve silme gibi diğer fonksiyonları da kullanabiliriz.

![](https://github.com/susalihh/Liman-MYS-de-Ansible-eklentisi-ile-nginx-kurulumu/blob/main/img/a7.png)

Playbooku çalıştır dedikten sonra playbooku uygulayacağımız hosts grubunu ve sudo şifresini girip çalıştır diyoruz.

![](https://github.com/susalihh/Liman-MYS-de-Ansible-eklentisi-ile-nginx-kurulumu/blob/main/img/a8.png)

İsteğe bağlı olarak log kaydedilebilir.

![](https://github.com/susalihh/Liman-MYS-de-Ansible-eklentisi-ile-nginx-kurulumu/blob/main/img/a9.png)

Client üzerinden nginx'in yüklendiğini ve aktif olduğunu görüntüleyebiliriz.
