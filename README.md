#Algoritma Warna PL
v. 2.1
7 September 2021

Berikut ini algoritma yg akan kita implementasi sebagai pembetulan algoritma Pedulilindungi. Hasil diskusi tambahan dengan Litbang dan P2P.


1. 🟢 Hijau: 
- Fully Vaccinated (2x vaksin, dan tidak ada data bahwa dia positif atau kontak erat) 
- 2x24 PCR result negatif OR 1x24 Antigen result negatif
2. 🟡 Kuning:
a.	Baru vaksin 1x (Kuning polos) tidak ada data bahwa dia positif atau kontak erat
b.	Penyintas < 3 bulan tidak ada data bahwa dia positif atau kontak erat
3. 🔴 Merah
a. Belum vaksin tidak ada data bahwa dia positif atau kontak erat
4. ⚫️ Hitam
a. Positif covid 
b. Kontak erat

Beberapa catatan:
1. Kalau terakhir kali positif > 14 hari -> otomatis negatif
2. Hasil Negatif dan positif di hari yang sama selalu di ambil yg positif  
Catatan tambahan:
a.	seluruh data individual checkin dan checkout di pergunakan untuk kebutuhan tracing selama 3 minggu ke depan. Setalah 3 minggu, semua data individual checkin dan checkout di delete permanen dari server
b.	Untuk komorbid permanen yg tidak bisa di vaksin membutuhkan surat keterangan dokter specialist dan test PCR / antigen diputuskan berdasarkan kebijakan perusahaan untuk karyawan
c.	Pengunjung mall, retail resto / public area , tamu pabrik hanya boleh hijau dan kuning
d.	Karyawan yg masuk ketempat kerja warna hijau kuning dan merah diperbolehkan masuk. 
e.	Warna merah masuk ke tempat kerja masih boleh dengan batas waktu 30 sept
f.	Jika dalam satu hari ada hasil positif dan negatif dari dua lab yang berbeda maka yang NAR kirim ke PL adalah yang positif
g.	Jika lab salah input dan mengupdate hasil positif menjadi negatif maka data update tetap bisa dikirim dari NAR ke PL selama diupdate sebelum sebelum batas rilis (jam 12 siang)
h.	Jika update lab dilakukan setelah batas jam rilis maka dianggap di update 1 hari setelahnya  
i.	10 hari sejak positive pertama masih dianggap positive. Walaupun ada hasil negative. 
j.	Hasil negatif sebelum 10 hari dari tanggal pengambilan sampel positif tidak akan dikirimkan dari NAR ke PL
k.	hari ke 11 s.d 14 dari positif pertama jika ada inputan test baru dgn hasil negative maka diambil negative dan data ini akan dikirimkan dari NAR ke PL
l.	Bila hari 11 s.d 14 hasil test masih positif maka masih dianggap positive
m.	Bila hari ke 11 s.d 14 tidak tes maka masih dianggap positif 
n.	14 hari setelah positif pertama akan dianggap otomatis negative di hari ke-15 dan di PL akan kembali ke kondisi awal
o.	Sampai 30 hari setelah negatif, setelah terkena positive, maka akan dianggap minimal sudah 1x suntik – setelah 30 hari akan kembali ke posisi awal (misalnya belum vaksin)
