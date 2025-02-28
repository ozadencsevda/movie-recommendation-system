# IMDB Film Öneri Sistemi

![Film Öneri](https://img.shields.io/badge/Proje-Film%20%C3%96neri-blue)
![Python](https://img.shields.io/badge/Python-3.6%2B-brightgreen)
![Pandas](https://img.shields.io/badge/Pandas-1.0%2B-orange)

IMDB puanlama verilerini kullanarak işbirlikçi filtreleme tabanlı bir film öneri sistemi. Bu proje, kişiselleştirilmiş film önerileri oluşturmak için gelişmiş veri filtreleme teknikleri ve Tekil Değer Ayrışımı (SVD) uygular.

## Proje Genel Bakış

Bu öneri sistemi, kullanıcı-film etkileşimlerini analiz ederek kullanıcıların film tercihleri arasındaki örüntüleri ve benzerlikleri bulmayı amaçlar. SVD ile dönüştürülmüş veriler üzerinde K-En Yakın Komşular yaklaşımı kullanarak, sistem benzer kullanıcıların beğendiği ancak hedef kullanıcının henüz izlemediği filmleri önerebilir.

## Özellikler

- **Veri Temizleme ve Ön İşleme**: Kaliteli öneriler sağlamak için yetersiz puanı olan kullanıcıları ve filmleri filtreler
- **Keşifsel Veri Analizi**: Puanlama dağılımlarını, kullanıcı etkinlik modellerini ve zamansal eğilimleri görselleştirir
- **Boyut Azaltma**: Seyrek kullanıcı-film matrisini sıkıştırmak için Truncated SVD kullanır
- **İşbirlikçi Filtreleme**: KNN ile kullanıcı tabanlı işbirlikçi filtreleme uygular
- **Ağırlıklı Öneriler**: Kullanıcılar arasındaki benzerlik puanlarına dayalı öneriler hesaplar

## Teknik Uygulama

Sistem şu ana adımları izler:

1. **Veri Yükleme ve İnceleme**: IMDB puanlama verileri yüklenir ve temel istatistikler analiz edilir
2. **Veri Filtreleme**: Yetersiz puanlama etkinliği olan kullanıcılar ve filmler çıkarılır
3. **Matris Oluşturma**: Kullanıcı-film puanlamaları seyrek bir matrise dönüştürülür
4. **SVD Dönüşümü**: Boyutsallık laneti problemini çözmek için matris SVD ile dönüştürülür
5. **KNN Modeli**: Benzer kullanıcıları bulmak için K-En Yakın Komşular algoritması uygulanır
6. **Öneri Oluşturma**: Benzer kullanıcıların puanlarına ve benzerlik skorlarına dayalı öneriler oluşturulur

## Kurulum

```bash
# Repoyu klonlayın
git clone https://github.com/kullaniciadi/imdb-film-oneri-sistemi.git
cd imdb-film-oneri-sistemi

# Gerekli paketleri yükleyin
pip install -r requirements.txt
```

## Kullanım

```python
# Projeyi çalıştırmak için
python imdbmovierecommendation.py
```

## Veri Seti

Bu proje, kullanıcıların filmlere verdikleri puanları içeren IMDB veri setini kullanmaktadır. Veri seti aşağıdaki formatta yapılandırılmıştır:

- `userId`: Kullanıcı kimliği
- `movieId`: Film kimliği
- `rating`: Kullanıcının filme verdiği puan (0.5-5 arası)
- `timestamp`: Puanlamanın yapıldığı zaman

## Gelecek Güncellemeler

Aşağıdaki geliştirmeler gelecek versiyonlarda eklenecektir:

- **Derin Öğrenme Modelleri**: Önerilerin doğruluğunu artırmak için sinir ağı tabanlı modeller
- **İçerik Tabanlı Filtreleme**: Film türlerini, oyuncuları ve yönetmenleri kullanarak içerik tabanlı filtreleme ekleme
- **Model Eğitimi ve Değerlendirme**: Modelin performansını ölçmek için kapsamlı değerlendirme metrikleri
- **Web Kullanıcı Arayüzü**: Kullanıcıların kendi beğenilerini girerek kişiselleştirilmiş öneriler alabilecekleri bir web arayüzü
- **Gerçek Zamanlı Güncelleme**: Yeni kullanıcı puanlamalarına göre modeli güncellemek için bir sistem
- **Daha Gelişmiş Filtreleme Teknikleri**: Hibrit öneri sistemleri ve matris faktörizasyon tekniklerinin uygulanması

## Katkıda Bulunma

Katkıda bulunmak isterseniz:

1. Bu repoyu forklayın
2. Yeni bir özellik dalı oluşturun (`git checkout -b yeni-ozellik`)
3. Değişikliklerinizi commit edin (`git commit -m 'Yeni özellik eklendi'`)
4. Dalınıza push yapın (`git push origin yeni-ozellik`)
5. Pull request oluşturun

## Lisans

Bu proje [CC0: Public Domain Lisansı](LICENSE) altında lisanslanmıştır. Detaylar için LICENSE dosyasına bakınız.

## İletişim

Proje hakkında sorularınız için bana e-posta ile ulaşabilirsiniz: [sevdatanozadenc@gmail.com](mailto:sevdatanozadenc@gmail.com)
