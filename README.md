# Liman MYS'de Ansible eklentisi ile NGİNX kurulumu

**1) Playbook Oluşturma**

![](https://github.com/susalihh/Liman-MYS-de-Ansible-eklentisi-ile-nginx-kurulumu/blob/main/a1.png)

Playbook sekmesinden "Dosya Oluştur" diyoruz

![](https://github.com/susalihh/Liman-MYS-de-Ansible-eklentisi-ile-nginx-kurulumu/blob/main/a2.png)

Dosya Adı: Oluşturacağımız playbook dosyasının ismini giriyoruz.

Dosya İçeriği: Oluşturacağımız playbook dosyasının içeriğini giriyoruz.

- hosts: all
  become: yes
  tasks:
    - name: ensure nginx is at the latest version
      apt: name=nginx state=latest
    - name: start nginx
      service:
        name: nginx
        state: started

**2) Hosts Ayarları**

![](https://github.com/susalihh/Liman-MYS-de-Ansible-eklentisi-ile-nginx-kurulumu/blob/main/a3.png)

Hosts sekmesinde Grup Ekle diyoruz

![](https://github.com/susalihh/Liman-MYS-de-Ansible-eklentisi-ile-nginx-kurulumu/blob/main/a4.png)

Clientlarımızı ekleyeceğimiz bir grup adı ekliyoruz.

![](https://github.com/susalihh/Liman-MYS-de-Ansible-eklentisi-ile-nginx-kurulumu/blob/main/a5.png)

Daha sonra hosts sekmesinde eklediğimiz grup gözükecektir. Üzerine tıklayıp Client Ekle diyoruz ve client bilgilerini giriyoruz.

**3) Playbook Çalıştırma**

![](https://github.com/susalihh/Liman-MYS-de-Ansible-eklentisi-ile-nginx-kurulumu/blob/main/a6.png)

Playbook-2 sekmesinde oluşturduğumuz playbooku seçiyoruz ve çalıştır diyoruz

![](https://github.com/susalihh/Liman-MYS-de-Ansible-eklentisi-ile-nginx-kurulumu/blob/main/a7.png)

Playbooku yükleyeceğimiz hosts grubunu ve sudo şifresini girip çalıştır diyoruz.

![](https://github.com/susalihh/Liman-MYS-de-Ansible-eklentisi-ile-nginx-kurulumu/blob/main/a8.png)

İsteğe bağlı olarak log kaydedilebilir.

![](https://github.com/susalihh/Liman-MYS-de-Ansible-eklentisi-ile-nginx-kurulumu/blob/main/a9.png)

Client üzerinden nginx'in yüklendiğini ve aktif olduğunu görüntüleyebiliriz.
