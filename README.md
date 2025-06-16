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
        <li><a href="#-kurtarma-moduna-girme">🚨 Kurtarma Moduna Girme</a></li>
        <li><a href="%EF%B8%8F-tiny-pxe-server-ayarları">🖥️ Tiny PXE Server Ayarları</a></li>
      </ul>
    </li>
    <li>
      <a href="#-debrickstock-yazılıma-dönme">🔃 Debrick/Stock Yazılıma Dönme</a>
      <ul>
        <li><a href="#-flashlama-i̇şlemi">⚡ Flashlama İşlemi</a></li>
        <li><a href="#-i̇şlem-sonrası">✅ İşlem Sonrası</a></li>
      </ul>
    </li>
    <li>
      <a href="#-sorun-giderme">🫠 Sorun Giderme</a>
    </li>
    <li>
      <a href="#%EF%B8%8F-kaynaklar">🗃️ Kaynaklar</a>
    </li>
  </ol>
</details>

# ✨ Başlarken

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

# 🔃 Debrick/Stock Yazılıma Dönme

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

# 🗃️ Kaynaklar
  - [Blog: @yucellmustafa/mi4a-gigabit-debrick](https://blog.yucellmustafa.com.tr/2023/05/27/mi4a-gigabit-debrick)
  - [YouTube: @yucellmustafa/mi4a-gigabit-debrick](https://www.youtube.com/watch?v=F7kfNIsIu5U)
   
-----------
🎀 Rehberimizi okuduğunuz için teşekkür ederiz!  
⭐ İçeriği faydalı bulduysanız desteklemek için **Star** verebilirsiniz.  
