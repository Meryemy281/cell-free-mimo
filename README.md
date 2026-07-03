# Cell-Free Massive MIMO Sistem Analizi

İstanbul Teknik Üniversitesi Elektronik ve Haberleşme Mühendisliği bitirme tezi
kapsamında geliştirilen, NVIDIA Sionna RT tabanlı cell-free massive MIMO
simülasyon kodları.

## Genel Bakış

Bu çalışma, Münih şehir senaryosunda ışın izleme (ray tracing) yöntemiyle
modellenen bir kanal üzerinde, dağıtık (cell-free) ve merkezi (collocated)
MIMO mimarilerinin başarımını karşılaştırır. ZF ve MRT precoding, LDPC kanal
kodlaması ve SDMA/FDMA/TDMA çoklu erişim şemaları incelenir.

## Gereksinimler

- Python 
- Sionna 
- TensorFlow
- NumPy, Matplotlib, Pandas


## Dosyalar

| Dosya | Açıklama |
|-------|----------|
| `main_code.jpynb` | Ana cell-free simülasyonu: 16 AP, çok kullanıcı; per-SNR, per-location, per-AP-count, SDMA/FDMA/TDMA analizleri |
| `centralized_comparison.jpynb` | Merkezi (collocated) massive MIMO referans senaryosu; cell-free UE yerleşimini kullanır |
| `SDMA_compare.jpynb` | SDMA (ZF) için 2 ve 4 kullanıcı başarım karşılaştırması |
| `sdma_code.jpynb` | LDPC kanal kodlamalı ZF; kodlanmış ve kodlanmamış BER karşılaştırması |
| `ue_positions.npy` | Sabit UE konumları (tekrarlanabilirlik için) |

## Çalıştırma Sırası

Önce `main_code.jpynb` çalıştırılmalıdır; bu betik `ue_positions.npy`
dosyasını üretir/kullanır. `centralized_comparison.jpynb` bu dosyaya bağımlıdır,
bu yüzden ondan sonra çalıştırılmalıdır.

## MATLAB Kodları

`matlab/` klasöründe, teorik (Rayleigh sönümlemeli) kanal üzerinde MIMO
detektör/precoder başarımını inceleyen MATLAB Live Script (`.mlx`) dosyaları
bulunur. Bu kodlar, Sionna tabanlı ray-tracing simülasyonlarına tamamlayıcı
bir referans oluşturur.

| Dosya | Açıklama |
|-------|----------|
| `uplink.mlx` | Uplink; ZF combining ile farklı alıcı anten sayılarında (4×4, 4×8, 4×16) BER karşılaştırması |
| `downlink.mlx` | Downlink; ZF precoding ile farklı verici anten sayılarında BER karşılaştırması |
| `comparison_uplink.mlx` | Uplink 4×8; ZF ve LMMSE detektörlerinin başarım karşılaştırması |
| `comparison_downlink.mlx` | Downlink 8×4; ZF ve LMMSE precoding karşılaştırması |

> Not: `.mlx` dosyaları MATLAB Live Script formatındadır ve GitHub üzerinde
> önizlenemez; açmak için MATLAB gereklidir.

## Yazar

Meryem Yılmaz — İstanbul Teknik Üniversitesi
