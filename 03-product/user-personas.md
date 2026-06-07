# User Personas

**Document:** User Personas
**Product:** Pawona
**Version:** 1.0 Draft
**Status:** Draft
**Owner:** Product Team
**Last Updated:** June 2026

---

# 1. Introduction

Dokumen ini mendefinisikan kelompok pengguna utama Pawona dan menjadi dasar seluruh keputusan produk, desain, AI, serta roadmap pengembangan.

Pawona tidak dirancang untuk semua orang yang memasak.

Fokus awal produk adalah pengguna yang secara rutin menghadapi tantangan dalam menentukan menu, mengelola bahan makanan, dan menyelesaikan proses memasak sehari-hari.

Seluruh fitur MVP harus dapat dipetakan ke kebutuhan salah satu persona utama yang dijelaskan dalam dokumen ini.

---

# 2. Persona Framework

Persona Pawona dibangun berdasarkan:

* Motivasi memasak
* Frekuensi memasak
* Tingkat kemampuan memasak
* Keterbatasan waktu
* Sensitivitas terhadap budget

Bukan berdasarkan usia atau demografi semata.

---

# 3. Primary Persona A

## The Household Planner

### Overview

Persona ini merupakan pengambil keputusan utama dalam dapur rumah tangga.

Mereka bertanggung jawab menentukan menu harian, mengelola bahan makanan, serta menjaga pengeluaran keluarga tetap terkendali.

---

### Typical Profile

* Ibu rumah tangga
* Orang tua muda
* Pengelola kebutuhan rumah tangga

---

### Daily Context

Setiap hari harus menjawab pertanyaan:

> "Hari ini masak apa?"

Mereka memasak secara rutin dan sering kali harus menyesuaikan menu dengan bahan yang tersedia.

---

### Pain Points

* Kehabisan ide masakan
* Bosan dengan menu yang sama
* Sulit memanfaatkan sisa bahan
* Pengeluaran dapur sulit dikontrol
* Terlalu banyak pilihan resep di internet

---

### Jobs To Be Done

Ketika saya memiliki bahan makanan di rumah,

Saya ingin mengetahui menu yang dapat dibuat,

Sehingga saya dapat menyiapkan makanan keluarga dengan cepat dan efisien.

---

### Success Criteria

* Menu ditemukan dengan cepat
* Bahan yang tersedia dapat dimanfaatkan
* Keluarga menyukai hasil masakan
* Pengeluaran dapur lebih terkontrol

---

### AI Expectations

* Rekomendasi menu yang relevan
* Alternatif bahan pengganti
* Estimasi biaya memasak
* Inspirasi menu harian

---

### Product Importance

Very High

---

### MVP Coverage

* AI Recipe Generator
* Shopping List
* Saved Recipes
* Personalized Recommendations

---

# 4. Primary Persona B

## The Busy Independent

### Overview

Pengguna yang hidup mandiri dan memiliki waktu terbatas untuk memasak.

Memasak bukan hobi utama mereka, tetapi kebutuhan sehari-hari.

---

### Typical Profile

* Anak kos
* Karyawan
* Fresh graduate
* Profesional muda

---

### Daily Context

Memiliki waktu terbatas.

Ingin makan lebih hemat dibanding membeli makanan setiap hari.

---

### Pain Points

* Tidak tahu menu sederhana yang bisa dibuat
* Tidak memiliki banyak bahan
* Waktu memasak terbatas
* Kurang percaya diri saat memasak

---

### Jobs To Be Done

Ketika saya ingin memasak dengan cepat,

Saya ingin mendapatkan resep sederhana dari bahan yang saya miliki,

Sehingga saya bisa makan dengan lebih hemat tanpa menghabiskan banyak waktu.

---

### Success Criteria

* Resep mudah diikuti
* Waktu memasak singkat
* Sedikit bahan tambahan
* Hasil masakan cukup baik

---

### AI Expectations

* Resep cepat
* Resep murah
* Langkah yang sederhana
* Panduan memasak yang jelas

---

### Product Importance

Very High

---

### MVP Coverage

* Recipe Generation
* Cooking Mode
* Ingredient Scan
* Cooking Assistant

---

# 5. Secondary Persona C

## The Culinary Explorer

### Overview

Pengguna yang menikmati proses memasak dan tertarik mencoba makanan baru.

---

### Typical Profile

* Pecinta kuliner
* Home cook
* Food enthusiast

---

### Daily Context

Memasak sebagai aktivitas yang menyenangkan.

Tidak selalu memiliki tekanan waktu atau budget.

---

### Pain Points

* Sulit menemukan resep autentik
* Kurang memahami asal-usul makanan
* Sulit menemukan variasi menu daerah

---

### Jobs To Be Done

Ketika saya ingin mencoba sesuatu yang baru,

Saya ingin menemukan resep dan cerita kuliner yang menarik,

Sehingga saya dapat memperluas pengalaman memasak saya.

---

### Success Criteria

* Menemukan resep unik
* Belajar hal baru
* Mengenal kuliner Nusantara

---

### AI Expectations

* Rekomendasi eksploratif
* Informasi budaya
* Variasi resep daerah

---

### Product Importance

Medium

---

### MVP Coverage

Minimal

Sebagian besar kebutuhan persona ini akan dilayani pada fase Growth dan Ecosystem.

---

# 6. Future Persona D

## The Family Nutrition Manager

### Overview

Pengguna yang sangat memperhatikan kesehatan dan nutrisi keluarga.

---

### Typical Profile

* Orang tua muda
* Pengguna yang sadar kesehatan
* Pengguna dengan kebutuhan diet tertentu

---

### Pain Points

* Sulit menyusun menu sehat
* Tidak memahami kandungan nutrisi
* Membutuhkan rekomendasi makanan yang sesuai kebutuhan keluarga

---

### Product Importance

Future

Persona ini belum menjadi target utama MVP.

---

# 7. Persona Prioritization

| Persona                  | Priority | MVP Focus |
| ------------------------ | -------- | --------- |
| Household Planner        | P1       | Yes       |
| Busy Independent         | P1       | Yes       |
| Culinary Explorer        | P2       | Partial   |
| Family Nutrition Manager | P3       | Future    |

---

# 8. Product Implications

Persona menentukan prioritas produk.

---

## Karena Household Planner adalah persona utama

Maka Pawona harus:

* memulai dari bahan yang tersedia
* menampilkan estimasi biaya
* mendukung perencanaan sederhana

---

## Karena Busy Independent adalah persona utama

Maka Pawona harus:

* cepat digunakan
* memiliki cooking mode sederhana
* meminimalkan jumlah input

---

## Karena Culinary Explorer bukan fokus MVP

Maka fitur seperti:

* komunitas
* konten budaya mendalam
* eksplorasi daerah

tidak menjadi prioritas awal.

---

# 9. Design Implications

UI harus:

* sederhana
* cepat dipahami
* tidak membutuhkan pembelajaran panjang

Pengguna utama Pawona bukan pengguna teknis.

---

# 10. AI Implications

AI harus mampu:

* memahami bahan lokal Indonesia
* memahami keterbatasan budget
* memahami konteks rumah tangga
* memberikan rekomendasi yang praktis

Bukan sekadar menghasilkan resep yang kreatif.

---

# 11. Summary

Pawona berfokus pada dua persona utama:

1. Household Planner
2. Busy Independent

Kedua persona ini memiliki kebutuhan yang berbeda tetapi berbagi masalah yang sama:

Mereka ingin mengetahui apa yang dapat dimasak dari bahan yang tersedia dengan cara yang cepat, mudah, dan hemat.

Seluruh MVP Pawona dirancang untuk membantu kedua persona tersebut mencapai tujuan mereka dengan bantuan AI yang memahami konteks dapur mereka.
