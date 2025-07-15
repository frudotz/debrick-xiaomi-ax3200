# Xiaomi AX3200 için Debrick/Yazılım Kurtarma Rehberi

Bu rehberimizde Xiaomi AX3200 cihazınızı stock firmware'e döndürmek (debrick) için gereken adımlar yer almaktadır.  
Cihazınız boot olmuyorsa veya stock yazılıma geri dönmek istiyorsanız aşağıdaki yönergeleri takip edebilirsiniz.  
*Yazılım değişiklikleri cihazı garanti dışı bırakabilir, oluşabilecek tüm komplikasyonlar sizin sorumluluğunuzdadır.*  
*Konu ile ilgili hiçbir sorumluluk kabul etmiyoruz. Rehberimizi kaynak göstererek paylaşmanız önemle rica olunur.* 🙏

<p align="left">
  <a href="https://discord.gg/k6y5MBKCPW"><img src="https://img.shields.io/badge/Discord-Yardım İçin-blue?logo=discord&logoColor=white"/></a>
</p>

<details>
  <summary>📋 İçindekiler</summary>
  <ol>
    <li>
      <a href="#-başlarken">✨ Başlarken</a>
      <ul>
        <li><a href="#-gereksinimler">📦 Gereksinimler</a></li>
        <li><a href="#-kuruluma-hazırlık">🪄 Kuruluma Hazırlık</a></li>
        <li><a href="#-kurtarma-moduna-girme">🚨 Kurtarma Moduna Girme</a></li>
        <li><a href="#%EF%B8%8F-tiny-pxe-server-ayarları">🖥️ Tiny PXE Server Ayarları</a></li>
      </ul>
    </li>
    <li>
      <a href="#-debrickstock-yazılıma-dönme---i̇ndir">🔃 Debrick/Stock Yazılıma Dönme - </a><a href="https://github.com/frudotz/debrick-xiaomi-ax3200/releases/download/StockYaz%C4%B1l%C4%B1mDebrick/ax3200-mt7622b-stock-debrick.zip">İndir</a>
      <ul>
        <li><a href="#-flashlama-i̇şlemi">⚡ Flashlama İşlemi</a></li>
        <li><a href="#-i̇şlem-sonrası">✅ İşlem Sonrası</a></li>
      </ul>
    </li>
    <li>
      <a href="#-sorun-giderme">🫠 Sorun Giderme</a>
    </li>
    <li>
      <a href="#-katkıda-bulun--bağış">🤝 Katkıda Bulun / Bağış</a>
    </li>
    <li>
      <a href="#%EF%B8%8F-kaynaklar">🗃️ Kaynaklar</a>
    </li>
  </ol>
</details>

# ✨ Başlarken

### ⚙️ Cihaz Özellikleri
- CPU: 1350 Mhz MediaTek MT7622B
- RAM: 256 MB
- FLASH: 128 MB
- 2.4 GHz: MediaTek MT7622B
- 5 GHz: MediaTek MT7915E
- Ethernet: 4x1000 Mbps LAN/WAN

### 📦 Gereksinimler

- MiWifi Stock Yazılımı - ([Global](http://cdn.awsde0-fusion.fds.api.mi-img.com/xiaoqiang/rom/rb01/miwifi_rb01_firmware_bbc77_1.0.71_INT.bin) - [Çin](https://cdn.cnbj1.fds.api.mi-img.com/xiaoqiang/rom/rb03/miwifi_rb03_firmware_83db5_1.0.57.bin)) - (Releases dosyasında mevcut)
- TinyPXE ([Releases](https://github.com/frudotz/openwrt-xiaomi-ax3200/releases/download/OpenWRTKurulum/ax3200-mt7622b-openwrt-kurulum.zip) dosyasında)  

## 📥 Kurulum dosyalarını [indirmek için tıklayın.](https://github.com/frudotz/openwrt-xiaomi-ax3200/releases/download/OpenWRTKurulum/ax3200-mt7622b-openwrt-kurulum.zip)  

### 🪄 Kuruluma Hazırlık

- Gerekli kurulum dosyalarını indirin ve uygun bir dizine çıkartın.  
- Windows üzerinde **Denetim Masası > Ağ ve İnternet > Ağ Bağlantıları** yolunu izleyin.
    - Ethernet adaptörünüzün **IPv4 ayarlarını** aşağıdaki gibi yapılandırın:  
      - IP adresi: `192.168.1.100`  
      - Alt ağ maskesi: `255.255.255.0`  
      - Varsayılan ağ geçidi: `Boş Bırakın`  
- Cihazı LAN portu üzerinden bilgisayarınıza bağlayın.

<p align="left">
  <img width="auto" height="490" src="https://github.com/frudotz/debrick-xiaomi-ax3200/blob/main/IMGs/1.png">
</p>

### 🚨 Kurtarma Moduna Girme

- Cihazın **güç kablosunu çıkarın**.
  - **Reset tuşuna basılı tutarak** güç kablosunu tekrar takın.
- LED **turuncu renkte yanıp sönmeye** başladığında reset tuşunu bırakın.
  - Birkaç saniye sonra LED **sabit turuncu** yanacaktır.
> Ağ bağlantısının kurulduğunu denetim masası üzerinden teyit edebilirsiniz.

### 🖥️ Tiny PXE Server Ayarları

- `Tiny PXE Server` uygulamasını başlatın.
- `Option 54` karşısında `192.168.1.100` yazdığından emin olun.
  - Ayarları şu şekilde yapılandırın:
      - En üstteki tikli tüm seçeneklerin tikini kaldırın.
      - `Boot File` alanında `C0A81F32.img` dosyasını seçin.
      - Altındaki tikli seçeneğin tikini kaldırın.
- Sağ üstten `Online` butonuna tıklayın.

<p align="left">
  <img width="auto" height="512" src="https://github.com/frudotz/debrick-xiaomi-ax3200/blob/main/IMGs/2.png">
</p>

# 🔃 Debrick/Stock Yazılıma Dönme - [İndir](https://github.com/frudotz/debrick-xiaomi-ax3200/releases/download/StockYaz%C4%B1l%C4%B1mDebrick/ax3200-mt7622b-stock-debrick.zip)

### ⚡ Flashlama İşlemi

- Başarılı bir bağlantıdan sonra log ekranında şu tür bir kayıt görünecektir:

<p align="left">
  <img width="auto" height="512" src="https://github.com/frudotz/debrick-xiaomi-ax3200/blob/main/IMGs/3.png">
</p>

- Kısa bir süre içinde cihazın LED'i **mavi renkte yanıp sönmeye** başlayacaktır.  
- Bu noktada cihazı güçten kesip yeniden başlattığınızda **MiWifi kurulum arayüzü** açılacaktır.

### ✅ İşlem Sonrası

- Ethernet ayarlarınızı tekrar **otomatik IP alacak şekilde** yapılandırın.
- MiWiFi arayüzüne eriştikten sonra Tiny PXE Server'da `Offline` butonuna tıklayın ve uygulamayı kapatın.

# 🫠 Sorun Giderme

- **Farklı bir IP adresi görüyorsanız:**
    - Bilgisayarınızdaki diğer ağları (Wi-Fi, sanal adaptörler vs.) devre dışı bırakın.

- **Bootloader moduna giremiyorsanız:**
    - Tiny PXE Server'ı kapatın.
    - Cihazı güçten kesip yeniden reset tuşuna basılı tutarak başlatmayı deneyin.

- **Hatalı işlem sonucu aşağıdaki gibi bir hata alırsanız işlemlere baştan başlayın:**

<p align="left">
  <img width="auto" height="512" src="https://github.com/frudotz/debrick-xiaomi-ax3200/blob/main/IMGs/4.png">
</p>

# 🤝 Katkıda Bulun / Bağış
  - Yanlış gördüğünüz veya eklemek istediğiniz şeyleri PR/Issue açarak iletebilirsiniz.  
  - Rehberimizi faydalı bulduysanız [🍻 bir bira ısmarlayarak](https://coff.ee/frudotz) bana destek olabilirsiniz.

# 🗃️ Kaynaklar
  - [Blog: @yucellmustafa/mi4a-gigabit-debrick](https://blog.yucellmustafa.com.tr/2023/05/27/mi4a-gigabit-debrick)
  - [YouTube: @yucellmustafa/mi4a-gigabit-debrick](https://www.youtube.com/watch?v=F7kfNIsIu5U)
   
-----------
🎀 Rehberimizi okuduğunuz için teşekkür ederiz!  
⭐ İçeriği faydalı bulduysanız desteklemek için **Star** verebilirsiniz.  
