# OM1 - Türkçe Kullanım Kılavuzu

![OM_Banner_X2 (1)](https://github.com/user-attachments/assets/853153b7-351a-433d-9e1a-d257b781f93c)

<p align="center">  <a href="https://arxiv.org/abs/2412.18588">Teknik Makale</a> |  <a href="https://docs.openmind.org/">Dokümantasyon</a> |  <a href="https://x.com/openmind_agi">X</a> | <a href="https://discord.gg/VUjpg4ef5n">Discord</a> </p>

**OpenMind'ın OM1'i, geliştiricilerin dijital ortamlarda ve fiziksel robotlarda multimodal yapay zeka ajanları oluşturmasını ve dağıtmasını sağlayan modüler bir yapay zeka çalışma ortamıdır**. Humanoid robotlar, telefon uygulamaları, web siteleri, dört ayaklı robotlar ve TurtleBot 4 gibi eğitim robotlarını destekler. OM1 ajanları, web verileri, sosyal medya, kamera görüntüleri ve LIDAR gibi çeşitli girdileri işleyebilir; hareket, otonom navigasyon ve doğal konuşmalar gibi fiziksel eylemleri gerçekleştirebilir. OM1'in amacı, kolayca yükseltilebilen ve farklı fiziksel form faktörlerine uyacak şekilde (yeniden)yapılandırılabilen, insan odaklı yetenekli robotlar oluşturmayı kolaylaştırmaktır.

## OM1'in Yetenekleri

* **Modüler Mimari**: Basitlik ve kusursuz entegrasyon için Python ile tasarlanmıştır.
* **Veri Girişi**: Yeni veri ve sensörleri kolayca işler.
* **Eklentiler Aracılığıyla Donanım Desteği**: API uç noktaları ve `ROS2`, `Zenoh` ve `CycloneDDS`'ye özgü robot donanım bağlantıları için eklentiler aracılığıyla yeni donanımları destekler. (Tüm yeni geliştirmeler için `Zenoh` öneriyoruz).
* **Web Tabanlı Hata Ayıklama Ekranı**: Kolay görsel hata ayıklama için WebSim (http://localhost:8000/ adresinde mevcuttur) ile sistemi çalışırken izleyin.
* **Önceden Yapılandırılmış Uç Noktalar**: Sesten Konuşmaya, OpenAI'nin `gpt-4o`, DeepSeek ve her hizmet için önceden yapılandırılmış uç noktalarla birden fazla Görsel Dil Modelini (VLM) destekler.

## Mimari Genel Bakış
![Artboard 1@4x 1 (1)](https://github.com/user-attachments/assets/14e9b916-4df7-4700-9336-2983c85be311)

## Başlangıç - Merhaba Dünya

OM1'e başlamak için Spot ajanını çalıştıralım. Spot, web kameranızı kullanarak nesneleri yakalayıp etiketler. Bu metin açıklamaları daha sonra `OpenAI 4o`'ya gönderilir ve `hareket`, `konuşma` ve `yüz` eylem komutları döndürür. Bu komutlar, temel zamanlama ve diğer hata ayıklama bilgileriyle birlikte WebSim üzerinde görüntülenir.

### Paket Yönetimi ve Sanal Ortam

[`uv` paket yöneticisine](https://docs.astral.sh/uv/getting-started/installation/) ihtiyacınız olacak.

### Repository'yi Klonlama

```bash
git clone https://github.com/openmind/OM1.git
cd OM1
git submodule update --init
uv venv
