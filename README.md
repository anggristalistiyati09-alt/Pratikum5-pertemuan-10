# Pratikum5-pertemuan-10
  data_mahasiswa = {}

  def hitung_nilai_akhir(tugas, uts, uas):
      return (tugas * 0.3) + (uts * 0.35) + (uas * 0.35)

  def tambah_data():
      nim = input("Masukkan NIM: ")
      if nim in data_mahasiswa:
          print("NIM sudah ada.")
          return
      nama = input("Masukkan Nama: ")
      tugas = float(input("Masukkan Nilai Tugas (0-100): "))
      uts = float(input("Masukkan Nilai UTS (0-100): "))
      uas = float(input("Masukkan Nilai UAS (0-100): "))
      nilai_akhir = hitung_nilai_akhir(tugas, uts, uas)
      data_mahasiswa[nim] = {
          'nama': nama,
          'tugas': tugas,
          'uts': uts,
          'uas': uas,
          'nilai_akhir': nilai_akhir
      }
      print("Data berhasil ditambahkan.")

  def ubah_data():
      nim = input("Masukkan NIM yang akan diubah: ")
      if nim not in data_mahasiswa:
          print("NIM tidak ditemukan.")
          return
      print(f"Data saat ini untuk {data_mahasiswa[nim]['nama']}:")
      tugas = float(input("Masukkan Nilai Tugas baru (0-100): "))
      uts = float(input("Masukkan Nilai UTS baru (0-100): "))
      uas = float(input("Masukkan Nilai UAS baru (0-100): "))
      nilai_akhir = hitung_nilai_akhir(tugas, uts, uas)
      data_mahasiswa[nim]['tugas'] = tugas
      data_mahasiswa[nim]['uts'] = uts
      data_mahasiswa[nim]['uas'] = uas
      data_mahasiswa[nim]['nilai_akhir'] = nilai_akhir
      print("Data berhasil diubah.")

  def hapus_data():
      nim = input("Masukkan NIM yang akan dihapus: ")
      if nim not in data_mahasiswa:
          print("NIM tidak ditemukan.")
          return
      del data_mahasiswa[nim]
      print("Data berhasil dihapus.")

  def tampilkan_data():
      if not data_mahasiswa:
          print("Belum ada data mahasiswa.")
          return
      print(f"{'NIM':<10} | {'Nama':<20} | {'Tugas':<7} | {'UTS':<7} | {'UAS':<7} | {'Nilai Akhir':<11}")
      print("-" * 70)
      for nim, data in data_mahasiswa.items():
          print(f"{nim:<10} | {data['nama']:<20} | {data['tugas']:<7.2f} | {data['uts']:<7.2f} | {data['uas']:<7.2f} | {data['nilai_akhir']:<11.2f}")

  def cari_data():
      nim = input("Masukkan NIM yang dicari: ")
      if nim not in data_mahasiswa:
          print("NIM tidak ditemukan.")
          return
      data = data_mahasiswa[nim]
      print(f"NIM: {nim}")
      print(f"Nama: {data['nama']}")
      print(f"Nilai Tugas: {data['tugas']}")
      print(f"Nilai UTS: {data['uts']}")
      print(f"Nilai UAS: {data['uas']}")
      print(f"Nilai Akhir: {data['nilai_akhir']:.2f}")

  def main():
      while True:
          print("\nMenu Pilihan:")
          print("1. Tambah Data")
          print("2. Ubah Data")
          print("3. Hapus Data")
          print("4. Tampilkan Data")
          print("5. Cari Data")
          print("6. Keluar")
          pilihan = input("Masukkan pilihan (1-6): ")

          if pilihan == '1':
              tambah_data()
          elif pilihan == '2':
              ubah_data()
          elif pilihan == '3':
              hapus_data()
          elif pilihan == '4':
              tampilkan_data()
          elif pilihan == '5':
              cari_data()
          elif pilihan == '6':
              print("Keluar dari program.")
              break
          else:
              print("Pilihan tidak valid. Masukkan angka 1-6.")

  if __name__ == "__main__":
      main()
      
  # menghasilkan seperti ini
  <img width="200" height="195" alt="image" src="https://github.com/user-attachments/assets/4a008e30-7033-481c-8e40-3f7f3ed55590" />
  
  # flowchartnya seperti ini
  ![WhatsApp Image 2025-11-23 at 22 06 25](https://github.com/user-attachments/assets/1150140c-5385-4277-91a9-300e8f59dedb)
  
  # penjelasan
Berikut adalah penjelasan fungsi-fungsi utama dalam kode tersebut:
data_mahasiswa = {}: Ini adalah dictionary kosong yang berfungsi sebagai database sementara untuk menyimpan data mahasiswa. Kunci (key) dari dictionary ini adalah NIM mahasiswa.
def hitung_nilai_akhir(tugas, uts, uas):: Fungsi ini menghitung nilai akhir mahasiswa berdasarkan nilai tugas (bobot 30%), UTS (bobot 35%), dan UAS (bobot 35%).
def tambah_data():
: Fungsi ini memungkinkan pengguna untuk memasukkan data mahasiswa baru (NIM, nama, nilai tugas, UTS, dan UAS).
Fungsi ini memeriksa apakah NIM yang dimasukkan sudah ada dalam data_mahasiswa. 
Jika sudah, akan menampilkan pesan kesalahan.
Setelah data dimasukkan, fungsi ini memanggil hitung_nilai_akhir untuk mendapatkan nilai akhir dan menyimpannya dalam dictionary.
def ubah_data():
: Fungsi ini memungkinkan pengguna untuk mengubah data mahasiswa yang sudah ada.
Fungsi ini meminta NIM yang akan diubah dan memeriksa apakah NIM tersebut ada dalam data_mahasiswa. Jika tidak, akan menampilkan pesan kesalahan.
ubah_data():
Fungsi ini meminta pengguna untuk memasukkan nilai tugas, UTS (Ujian Tengah Semester), dan UAS (Ujian Akhir Semester) yang baru untuk mahasiswa tertentu.
Nilai yang dimasukkan diubah menjadi tipe data float.
Fungsi ini memanggil fungsi lain bernama hitung_nilai_akhir (yang tidak terlihat di gambar) untuk menghitung nilai akhir berdasarkan nilai tugas, UTS, dan UAS yang baru.
Nilai tugas, UTS, UAS, dan nilai akhir yang baru kemudian diperbarui dalam kamus data_mahasiswa untuk NIM (Nomor Induk Mahasiswa) yang sesuai.
Pesan "Data berhasil diubah." akan dicetak setelah pembaruan selesai.
hapus_data():
Fungsi ini meminta pengguna untuk memasukkan NIM mahasiswa yang ingin dihapus datanya.
Fungsi ini memeriksa apakah NIM yang dimasukkan ada dalam data_mahasiswa.
Jika NIM tidak ditemukan, pesan "NIM tidak ditemukan." akan dicetak dan fungsi berhenti.
Jika NIM ditemukan, data mahasiswa dengan NIM tersebut akan dihapus dari kamus menggunakan perintah del.
Pesan "Data berhasil dihapus." akan dicetak setelah penghapusan selesai.
tampilkan_data():
Fungsi ini memeriksa apakah kamus data_mahasiswa kosong.
Jika kosong, pesan "Belum ada data mahasiswa." akan dicetak dan fungsi berhenti.
Jika ada data, fungsi ini mencetak header tabel yang rapi untuk kolom NIM, Nama, Tugas, UTS, UAS, dan Nilai Akhir.
Fungsi ini kemudian melakukan iterasi melalui semua entri dalam data_mahasiswa dan mencetak detail setiap mahasiswa dalam format baris tabel yang rapi.
Format pencetakan menggunakan f-string Python untuk perataan teks dan pemformatan angka desimal. 
Fungsi cari_data(): Meminta input NIM, memeriksa keberadaan NIM dalam data_mahasiswa, dan mencetak detail mahasiswa (NIM, Nama, Nilai Tugas, UTS, UAS, Nilai Akhir) jika ditemukan.
Fungsi main(): Menampilkan menu pilihan (1-6) dan memproses input pengguna untuk memanggil fungsi manajemen data yang sesuai.
Struktur Menu: Menu tersebut mencakup opsi untuk "Tambah Data", "Ubah Data", "Hapus Data", "Tampilkan Data", "Cari Data", dan "Keluar".
Kode tersebut menunjukkan struktur kontrol if/elif/else yang digunakan untuk menangani pilihan menu dari pengguna.
Terdapat enam pilihan yang tersedia, masing-masing memanggil fungsi yang berbeda seperti tambah_data(), ubah_data(), hapus_data(), tampilkan_data(), dan cari_data().
Pilihan '6' digunakan untuk keluar dari program, sedangkan pilihan lainnya akan menampilkan pesan kesalahan jika tidak valid.
Di bagian bawah, terdapat blok if _name_ == "_main_": yang merupakan titik masuk standar untuk menjalankan skrip Python dengan memanggil fungsi main().

