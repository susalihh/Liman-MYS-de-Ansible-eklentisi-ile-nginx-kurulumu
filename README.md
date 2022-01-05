1) Playbook Oluşturma

Image description

Playbook sekmesinden "Dosya Oluştur" diyoruz

Image description

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

2) Hosts Ayarları

Image description

Hosts sekmesinde Grup Ekle diyoruz

Image description

Clientlarımızı ekleyeceğimiz bir grup adı ekliyoruz.

Image description

Daha sonra hosts sekmesinde eklediğimiz grup gözükecektir. Üzerine tıklayıp Client Ekle diyoruz ve client bilgilerini giriyoruz.

3) Playbook Çalıştırma

Image description

Playbook-2 sekmesinde oluşturduğumuz playbooku seçiyoruz ve çalıştır diyoruz

Image description

Playbooku yükleyeceğimiz hosts grubunu ve sudo şifresini girip çalıştır diyoruz.

Image description

İsteğe bağlı olarak log kaydedilebilir.

Image description

Client üzerinden nginx'in yüklendiğini ve aktif olduğunu görüntüleyebiliriz.
