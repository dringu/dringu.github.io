---
layout: post
title: Mengurai PDRB, Membaca Postur
date: 2025-04-04 19:40:00
featured: true
description: Mengulik Produk Domestik Regional Bruto (PDRB) untuk memahami struktur dan dinamika ekonomi wilayah.
tags: data probolinggo ekonomi
categories: data probolinggo
---

Mengikuti siaran langsung pelantikan kepala daerah di YouTube, tampak mereka berbaris rapi dengan derap langkah serempak memasuki Istana. Barangkali bukan hanya ayunan langkah yang kompak seirama, tetapi juga dalam semangat : niat baik untuk memajukan daerah. 

Namun, keseragaman niat tak selalu sejalan dengan tantangan yang akan dihadapi. Ikhtiar masing-masing kepala daerah untuk memajukan wilayahnya berangkat dari titik awal yang berbeda. Tiap daerah memiliki potensi yang beragam, sumber daya yang tidak setara, dan struktur ekonomi yang berbeda-beda.

Salah satu indikator yang dapat memberikan gambaran komprehensif tentang kondisi ekonomi suatu daerah adalah Produk Domestik Regional Bruto (PDRB). PDRB tidak hanya menunjukkan besaran ekonomi, tetapi juga struktur, dinamika pertumbuhan, dan potensi pengembangan suatu wilayah. Melalui penelaahan PDRB, kita dapat memahami tantangan khusus yang dihadapi setiap kepala daerah dalam upaya memajukan daerah dan meningkatkan kesejahteraan masyarakatnya.

Dalam catatan ini, kita akan menelusuri data PDRB kabupaten/kota di Jawa Timur untuk mendapatkan gambaran tentang variasi kondisi ekonomi antar daerah. Selanjutnya, kita akan mempersempit fokus pada Kabupaten Probolinggo untuk analisis yang lebih mendalam. Data yang digunakan diambil dari portal Badan Pusat Statistik (BPS): [jatim.bps.go.id](https://jatim.bps.go.id/) dan divisualisasikan menggunakan Python. Script kode Python untuk pengolahan data dapat diakses di _repository_ Github berikut: [github.com/dringu/pdrb](https://github.com/dringu/pdrb).

**Gambaran PDRB Kabupaten/Kota di Jawa Timur**

Untuk memahami perbedaan kondisi ekonomi antar daerah, kita akan menggunakan dua jenis data PDRB. PDRB atas dasar harga konstan (ADHK) 2010 digunakan untuk menganalisis pertumbuhan ekonomi riil dari tahun ke tahun tanpa terpengaruh inflasi. Sementara itu, PDRB atas dasar harga berlaku (ADHB) mencerminkan nilai ekonomi aktual pada suatu periode, akan digunakan untuk perbandingan antar daerah dalam satu waktu.

Tabel berikut menampilkan sampel data PDRB dari 8 kabupaten/kota di Jawa Timur yang dipilih untuk menunjukkan variasi besaran ekonomi—mulai dari yang terbesar (Kota Surabaya) hingga yang terkecil (Kota Blitar), serta beberapa daerah dengan nilai PDRB menengah termasuk Kabupaten Probolinggo:

**Tabel 1. PDRB Kabupaten/Kota Terpilih di Jawa Timur, 2015-2024 (Miliar Rupiah)**

|Kabupaten/Kota|2015|2020|2024|CAGR|
|---|---|---|---|---|
|**Kota Surabaya**|324,215.17|389,741.41|485,448.90|4.6%|
|**Sidoarjo**|112,012.86|134,576.10|169,867.80|4.7%|
|**Gresik**|81,380.44|96,966.33|119,274.40|4.3%|
|**Malang**|55,317.82|66,077.41|79,500.90|4.1%|
|**Probolinggo**|19,570.99|22,656.56|27,153.10|3.7%|
|**Bangkalan**|16,906.84|16,889.72|17,497.50|0.4%|
|**Pacitan**|9,019.54|10,630.02|12,775.80|3.9%|
|**Kota Blitar**|3,856.91|4,668.68|5,746.40|4.5%|

_Sumber: BPS Jawa Timur (diolah)_

Dari tabel di atas, kita dapat melihat kesenjangan ekonomi yang sangat signifikan antar daerah di Jawa Timur. Kota Surabaya, sebagai pusat ekonomi provinsi, memiliki nilai PDRB hampir 85 kali lebih besar dibandingkan Kota Blitar. Bahkan dengan Kabupaten Probolinggo yang berada di tingkat menengah, perbedaannya masih mencapai sekitar 18 kali lipat.

Kolom CAGR (_Compound Annual Growth Rate_) menunjukkan rata-rata pertumbuhan tahun majemuk selama periode 2015-2024. Perhitungan CAGR digunakan karena lebih akurat untuk menggambarkan tren pertumbuhan dalam rentang waktu yang relatif panjang. Menariknya, beberapa daerah dengan PDRB lebih kecil seperti Kota Blitar memiliki tingkat pertumbuhan yang relatif tinggi (4.5%), sementara Kabupaten Bangkalan hanya tumbuh 0.4% per tahun.

**Visualisasi Tren PDRB 2015-2024**

Visualisasi data keseluruhan dalam bentuk grafik dapat memberikan gambaran yang lebih utuh. Berikut grafik yang menampilkan besaran PDRB seluruh kabupaten/kota di Jawa Timur dalam rentang 1 dekade (2015-2024).

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/chart/PDRB_Probolinggo_Tetangga_Trend.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Gambar 1. Tren Besaran PDRB Kabupaten/Kota di Jawa Timur 2015-2024 (kiri: seluruh daerah; kanan: tanpa Surabaya dan Sidoarjo)
</div>

Dari grafik pertama (kiri), terlihat bahwa nilai PDRB Kota Surabaya dan Sidoarjo memiliki jarak yang sangat jauh dengan daerah lainnya dan tampak sebagai pencilan. Untuk memudahkan pengamatan terhadap daerah lainnya, grafik kedua (kanan) menampilkan tren PDRB tanpa kedua daerah tersebut.

Kedua grafik menampilkan nilai rata-rata PDRB Jawa Timur dengan garis biru putus-putus sebagai referensi perbandingan. Terlihat bahwa mayoritas daerah berada di bawah rata-rata provinsi, yang mengkonfirmasi adanya kesenjangan ekonomi yang signifikan antar wilayah.

Dari grafik kedua (tanpa Kota Surabaya dan Sidoarjo), empat daerah dengan nilai PDRB tertinggi berikutnya—Pasuruan, Gresik, Kota Kediri, dan Malang—memiliki jarak yang cukup jauh dari rata-rata provinsi. Sementara itu, Bojonegoro menunjukkan tren pertumbuhan yang lebih fluktuatif dibandingkan daerah lain, kemungkinan karena pengaruh dinamika industri migas di wilayah tersebut

**Dampak Pandemi COVID-19**

Pengamatan penting lainnya adalah adanya perlambatan pertumbuhan di sekitar tahun 2020 yang bertepatan dengan pandemi COVID-19, terutama untuk daerah dengan PDRB di atas rata-rata. Lekukan pada grafik tampak lebih jelas pada daerah dengan ekonomi lebih besar, sementara daerah dengan PDRB lebih rendah cenderung menunjukkan perubahan yang lebih halus.

Fenomena ini mengindikasikan bahwa struktur ekonomi daerah dengan PDRB lebih besar cenderung didominasi oleh sektor yang lebih sensitif terhadap guncangan eksternal, seperti jasa dan manufaktur. Sementara daerah dengan ekonomi lebih kecil yang umumnya bertumpu pada sektor pertanian relatif lebih tahan terhadap dampak pandemi.

Untuk melihat lebih jelas dampak COVID-19, berikut adalah grafik pertumbuhan tahunan PDRB kabupaten/kota di Jawa Timur:

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/chart/tren_pertumbuhan_jatim.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Gambar 2. Pertumbuhan Tahunan PDRB Kabupaten/Kota di Jawa Timur
</div>

Grafik di atas menggunakan metode perhitungan pertumbuhan tahunan (_year-on-year_), bukan CAGR, untuk menunjukkan fluktuasi tahunan dan memberikan gambaran pola volatilitas ekonomi daerah. Terlihat jelas bahwa hampir seluruh daerah mengalami kontraksi ekonomi pada tahun 2020 dengan tingkat yang bervariasi. Beberapa daerah seperti Kota Kediri mengalami penurunan hingga -6%, sementara Bojonegoro menunjukkan fluktuasi ekstrem dengan pertumbuhan sangat tinggi di tahun-tahun awal diikuti kontraksi yang dalam di masa pandemi.

Sedangkan untuk Kabupaten Probolinggo, memiliki tren pertumbuhan yang relatif stabil dan sejalan dengan rata-rata provinsi, meskipun dengan tingkat pertumbuhan yang sedikit di bawah rata-rata Jawa Timur untuk sebagian besar periode.

**Distribusi Spasial PDRB di Jawa Timur**

Untuk memberikan gambaran kekuatan ekonomi antar kabupaten/kota di Jawa Timur, berikut adalah peta *choropleth* yang menunjukkan distribusi PDRB (ADHB, 2024) secara spasial:

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/chart/Peta_PDRB_ADHB.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Gambar 3. Distribusi Spasial PDRB Kabupaten/Kota di Jawa Timur, 2024
</div>

Peta di atas menunjukkan konsentrasi ekonomi yang tinggi di kawasan Surabaya dan sekitarnya, serta Malang Raya. Sementara itu, kawasan Tapal Kuda termasuk Probolinggo dan daerah barat daya cenderung memiliki nilai PDRB lebih rendah (ditunjukkan dengan warna yang lebih terang). Distribusi spasial ini mencerminkan ketimpangan pembangunan ekonomi di Jawa Timur yang condong ke kawasan barat dan utara provinsi.

**Profil Ekonomi Kabupaten Probolinggo**

Kabupaten Probolinggo dengan PDRB sebesar 45,7 triliun rupiah (2024, ADHB) berada di posisi menengah di antara 38 kabupaten/kota di Jawa Timur. Dengan CAGR 3,7%, ukuran ekonomi Kabupaten Probolinggo tumbuh dibawah rata-rata provinsi (4,1%) selama 1 dekade terakhir (2015-2024).

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/chart/tren_probolinggo.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Gambar 4. Tren Pertumbuhan Ekonomi Kabupaten Probolinggo
</div>

Dari grafik di atas, terlihat bahwa tren pertumbuhan Kabupaten Probolinggo bergerak relatif stabil mengikuti pola provinsi, meskipun sempat mengalami kontraksi di masa pandemi COVID-19. Terbaru, pada tahun 2024, pertumbuhan ekonomi Kabupaten Probolinggo mencapai 4,8% (YoY), sedikit dibawah Jawa Timur sebesar [4,9%](https://jatim.bps.go.id/id/pressrelease/2025/02/05/1479/ekonomi-jawa-timur-tahun-2024-tumbuh-4-93-persenekonomi-jawa-timur-triwulan-iv-2024-tumbuh-5-03-persen--y-on-y-ekonomi-jawa-timur-triwulan-iv-2024-tumbuh--0-77-persen--q-to-q-.html) dan dibawah pertumbuhan nasional sebesar [5.03%](https://indonesia.go.id/kategori/ekonomi-bisnis/8991/perekonomian-indonesia-2024-tumbuh-sebesar-5-03-persen?lang=1).

**Struktur Ekonomi**

Untuk memahami lebih detail tentang karakteristik ekonomi Kabupaten Probolinggo, kita bisa merujuk pada data PDRB berdasarkan lapangan usaha. Data dimaksud dapat divisualisikan dalam chart berikut:

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/chart/Lapangan Usaha_Prob.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Gambar 5. Kontribusi Sektor Ekonomi terhadap PDRB Kabupaten Probolinggo, 2024
</div>

Grafik diatas menggunakan data PDRB Atas dasar harga berlaku (ADHB) tahun 2024, terlihat bahwa struktur ekonomi Kabupaten Probolinggo didominasi oleh tiga sektor utama:

1. Pertanian, Kehutanan, dan Perikanan - Menyumbang hampir 30% dari total PDRB
2. Industri Pengolahan/Manufaktur - Berkontribusi sekitar 27% terhadap PDRB
3. Perdagangan Besar dan Eceran - Menyumbang sekitar 13% dari PDRB

Ketiga sektor ini secara kumulatif menyumbang hampir 70% total PDRB Probolinggo. Komposisi ini mencerminkan karakteristik daerah yang masih bertumpu pada ekonomi berbasis sumber daya alam dengan transformasi bertahap menuju industri dan jasa.

Selanjutnya mari kita bandingkan struktur ini dengan Jawa Timur secara keseluruhan.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/chart/Figure_3.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Gambar 6. Perbandingan Struktur Ekonomi berdasarkan Lapangan Usaha: Jawa Timur vs Kabupaten Probolinggo
</div>

Dari perbandingan grafik di atas, terlihat beberapa perbedaan signifikan antara struktur ekonomi Kabupaten Probolinggo dengan Jawa Timur secara keseluruhan:
1. Proporsi sektor pertanian di Probolinggo (30%) jauh melampaui rata-rata provinsi (10%), menegaskan karakter agraris yang masih kuat.
2. Meskipun industri pengolahan/manufaktur merupakan sektor dominan baik di tingkat provinsi maupun di Kabupaten Probolinggo, kontribusinya di tingkat provinsi lebih besar (sekitar 30% vs 27% di Probolinggo).
3. Sektor jasa(seperti transportasi, informasi, keuangan, dan jasa lainnya) memiliki proporsi yang lebih kecil di Probolinggo dibandingkan rata-rata provinsi.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/chart/Figure_1.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Gambar 7. Perbandingan komposisi PDRB Kabupaten Probolinggo terhadap Jawa Timur, 2024
</div>

Perbedaan struktur ini mengindikasikan bahwa Kabupaten Probolinggo relatif masih berada pada tahap awal transformasi ekonomi dari pertanian menuju industri manufaktur dan jasa, dengan potensi besar untuk diversifikasi ekonomi di masa mendatang.

Ruang untuk pengembangan sektor manufaktur terlihat dari indikasi bahwa meskipun sektor ini memiliki kontribusi signifikan dalam PDRB (mencapai 27%), hal ini tidak diikuti dengan peningkatan kontribusi sektor jasa.

**Keterbandingan Wilayah Tetangga**

Untuk mendapatkan gambaran lebih komprehensif tentang posisi ekonomi Kabupaten Probolinggo, penting untuk membandingkannya dengan kabupaten/kota tetangga di kawasan Tapal Kuda dan sekitarnya.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/chart/tetangga 5 sektor utama.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Gambar 8. Perbandingan Lima Sektor Ekonomi Utama Antara Probolinggo dengan Daerah Tetangga
</div>

Beberapa karakteristik masing-masing Wilayah yang dapat dipahami dari chart diatas antara lain:
- **Pasuruan**: Sangat dominan di sektor Industri (60.4%) dan Konstruksi (10.8%), mencerminkan karakter daerah industri dengan pembangunan infrastruktur yang intensif.
- **Situbondo**: Mengandalkan Pertanian (30.5%) dan Industri (20.6%) dengan pola yang relatif serupa dengan Probolinggo.
- **Lumajang**: Struktur ekonomi didominasi Pertanian (32.8%) dan Industri (22.6%).
- **Jember**: Memiliki basis Pertanian (25.8%) dan Industri (20.9%) dengan proporsi yang lebih seimbang antar sektor.
- **Probolinggo**: Bertumpu pada Pertanian (32.3%) dan Industri (26.7%) dengan komposisi relatif seimbang.
- **Kota Probolinggo**: Menunjukkan karakter perkotaan dengan dominasi sektor Perdagangan (26.2%) dan Transportasi (16.1%).

Hal menarik yang perlu dicermati dari gambaran 5 sektor utama diatas adalah, sektor administrasi pemerintahan di Kabupaten Probolinggo masuk dalam 5 besar kontributor utama pembentuk PDRB.Ini menggambarkan struktur ekonomi Kabupaten Probolinggo yang masih kurang terdiversifikasi. Idealnya, setidaknya seperti daerah tetangga, kontribusinya dalam PDRB tidak melampaui sektor-sektor produktif. 

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/chart/Perbandingan sektor kunci.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Gambar 9. Visualisasi Komparatif Sektor-sektor Kunci Ekonomi Daerah di Kawasan Tapal Kuda
</div>

Sektor pertanian masih menjadi tulang punggung ekonomi di sebagian besar kabupaten di kawasan Tapal Kuda, terutama di Probolinggo (32.3%), Lumajang (32.8%), dan Situbondo (30.5%).
Industri terkonsentrasi sangat kuat di Pasuruan (60.4%), sementara di kabupaten lain berkisar antara 20-27% meski dengan kesenjangan yang signifikan dalam nilai absolut. 

**Catatan Akhir**

Berdasarkan struktur ekonomi yang ada dan perbandingan dengan daerah tetangga, Kabupaten Probolinggo memiliki potensi untuk:
- Melakukan transformasi struktural lebih lanjut dengan kontribusi sektor industri manufaktur yang sudah cukup signifikan (27%). Namun, masih diperlukan upaya untuk diversifikasi ekonomi dan pengembangan sektor jasa, sementara dalam nilai absolut, kesenjangan dengan Kabupaten Pasuruan tetap sangat besar.
- Memperkuat rantai nilai industri manufaktur, terutama yang berbasis sumber daya lokal
- Mengembangkan sektor jasa pendukung seperti logistik dan perdagangan untuk memaksimalkan posisi geografis Probolinggo di jalur utara-timur Jawa

Memahami karakteristik PDRB dan dinamika pertumbuhan ekonomi regional merupakan langkah awal yang penting dalam perumusan kebijakan pembangunan yang efektif dan tepat sasaran.