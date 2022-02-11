# Algoritma Warna Pedulilindungi
v. 2.2\
14 September 2021\
Update: 11 Februari 2022 by @auliazahrina\
\
Berikut ini algoritma yg akan kita implementasi sebagai pembetulan algoritma Pedulilindungi. Hasil diskusi tambahan dengan Litbang dan P2P.


1. 🟢 Hijau: 
- Fully Vaccinated (2x vaksin, dan tidak ada data bahwa dia positif atau kontak erat) 
- 3x24 jam PCR result negatif OR 1x24 jam Antigen result negatif
2. 🟡 Kuning:
- Baru vaksin 1x dan tidak ada data bahwa dia positif atau kontak erat
- Penyintas < 3 bulan tidak ada data bahwa dia positif atau kontak erat
3. 🔴 Merah
- Belum vaksin tidak ada data bahwa dia positif atau kontak erat
4. ⚫️ Hitam
- Positif covid 
- Kontak erat
- Karantina pelaku perjalanan luar negeri

---

Beberapa catatan:
- seluruh data individual checkin dan checkout di pergunakan untuk kebutuhan tracing selama 3 minggu ke depan. Setalah 3 minggu, semua data individual checkin dan checkout di delete permanen dari server</li>
- Untuk komorbid permanen yg tidak bisa di vaksin membutuhkan surat keterangan dokter spesialis dan test PCR / antigen diputuskan berdasarkan kebijakan perusahaan untuk karyawan</li>
- Pengunjung mall, retail resto / public area , tamu pabrik hanya boleh hijau dan kuning</li>
- Karyawan yg masuk ketempat kerja warna hijau kuning dan merah diperbolehkan masuk. </li>
- Warna merah masuk ke tempat kerja masih boleh dengan batas waktu 30 sept</li>
<ol type="a">
<li>Jika dalam satu hari ada hasil positif dan negatif dari dua lab yang berbeda maka yang NAR kirim ke PL adalah yang positif</li>
<li>Hari ke-1 sampai hari ke-5 masih dianggap positif. Walaupun ada hasil negatif.</li>
<li>Jika ada hasil negatif pada hari ke-1 sampai hari ke-5, maka hasil negatif tidak akan dikirimkan dari NAR ke PL.</li>
<li>Hari ke-6 s.d 10 dari positif pertama jika ada hasil tes PCR negatif sebanyak 2x yang berjarak 24 jam, maka status akan kembali seperti semula.</li>
<li>Bila hari ke-6 s.d 10 hasil tes masih positif maka masih dianggap positif</li>
<li>Bila hari ke-6 s.d 10 tidak tes maka masih dianggap positif</li>
<li>Jika kasus konfirmasi tidak melakukan tes, maka status akan kembali seperti semula pada hari ke-11.</li>
<li>Sampai dengan 30 hari setelah positif pertama, maka hasil positif tidak akan pernah dianggap sebagai re-infeksi</li>
<li>Sampai 90 hari setelah negatif, maka akan dianggap sebagai status 1x suntik – setelah 90 hari akan kembali ke posisi awal (misalnya belum vaksin)</li>
<li>Untuk semua data positif yg ada di PJTLI yg sudah diapprove, maka statusnya adalah positif (hitam)</li>
<li>Data yang terkonfirmasi covid, tapi tidak ada hasil test lab (dimasukkan oleh Dinkes dan PHEOC) termasuk yang akan dianggap positif</li>
<li>Data NIK dari Silacak (program tracing) akan dikategorikan sebagai kontak erat</li>
  <li>Jika kontak erat melakukan tes antigen atau PCR dengan hasil negatif, maka status akan kembali seperti semula sesuai tanggal hasil tes negatif.</li>  
  <li>Jika kontak erat tidak melakukan tes, maka status akan kembali seperti semula pada hari ke-11</li>
</ol>
