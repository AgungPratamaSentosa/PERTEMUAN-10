# PERTEMUAN-10
<H1>PRAKTIKUM10</H1>

```python
from prettytable import PrettyTable

def hitung_nilai_akhir(tugas, uts, uas):
    nilai_akhir = 0.3 * tugas + 0.35 * uts + 0.35 * uas
    return nilai_akhir

def tambah_data(data_mahasiswa):
    nama = input("Masukkan nama mahasiswa: ")
    nim = input("Masukkan NIM mahasiswa: ")
    tugas = float(input("Masukkan nilai tugas: "))
    uts = float(input("Masukkan nilai UTS: "))
    uas = float(input("Masukkan nilai UAS: "))
    nilai_akhir = hitung_nilai_akhir(tugas, uts, uas)
    data_mahasiswa[nama] = {"NIM": nim, "Tugas": tugas, "UTS": uts, "UAS": uas, "Nilai Akhir": nilai_akhir}
    print("Data mahasiswa berhasil ditambahkan.")

def ubah_data(data_mahasiswa):
    nama = input("Masukkan nama mahasiswa yang akan diubah datanya: ")
    if nama in data_mahasiswa:
        tugas = float(input("Masukkan nilai tugas baru: "))
        uts = float(input("Masukkan nilai UTS baru: "))
        uas = float(input("Masukkan nilai UAS baru: "))
        nilai_akhir = hitung_nilai_akhir(tugas, uts, uas)
        data_mahasiswa[nama] = {"Tugas": tugas, "UTS": uts, "UAS": uas, "Nilai Akhir": nilai_akhir}
        print("Data mahasiswa berhasil diubah.")
    else:
        print("Nama mahasiswa tidak ditemukan.")

def hapus_data(data_mahasiswa):
    nama = input("Masukkan nama mahasiswa yang akan dihapus datanya: ")
    if nama in data_mahasiswa:
        del data_mahasiswa[nama]
        print("Data mahasiswa berhasil dihapus.")
    else:
        print("Nama mahasiswa tidak ditemukan.")

def tampilkan_data(data_mahasiswa):
    tabel = PrettyTable()
    tabel.field_names = ["Nama", "NIM", "Tugas", "UTS", "UAS", "Nilai Akhir"]

    for nama, nilai in data_mahasiswa.items():
        tabel.add_row([nama, nilai["NIM"], nilai["Tugas"], nilai["UTS"], nilai["UAS"], nilai["Nilai Akhir"]])

    print("\nDaftar Nilai Mahasiswa:")
    print(tabel)


def cari_data(data_mahasiswa):
    nama = input("Masukkan nama mahasiswa yang akan dicari: ")
    if nama in data_mahasiswa:
        tabel = PrettyTable()
        tabel.field_names = ["Nama", "Tugas", "UTS", "UAS", "Nilai Akhir"]
        nilai = data_mahasiswa[nama]
        tabel.add_row([nama, nilai["Tugas"], nilai["UTS"], nilai["UAS"], nilai["Nilai Akhir"]])
        print("\nData mahasiswa ditemukan:")
        print(tabel)
    else:
        print("Nama mahasiswa tidak ditemukan.")

#Program utama
data_mahasiswa = {}

while True:
    print("\nMenu Pilihan:")
    print("1. Tambah Data")
    print("2. Ubah Data")
    print("3. Hapus Data")
    print("4. Tampilkan Data")
    print("5. Cari Data")
    print("6. Keluar")

    pilihan = input("Masukkan pilihan (1-6): ")

    if pilihan == "1":
        tambah_data(data_mahasiswa)
    elif pilihan == "2":
        ubah_data(data_mahasiswa)
    elif pilihan == "3":
        hapus_data(data_mahasiswa)
    elif pilihan == "4":
        tampilkan_data(data_mahasiswa)
    elif pilihan == "5":
        cari_data(data_mahasiswa)
    elif pilihan == "6":
        print("Program selesai.")
        break
    else:
        print("Pilihan tidak valid. Masukkan angka 1-6.")
 ```

![Screenshot (17)](https://github.com/sentosa2505/PERTEMUAN-10/assets/148040303/bd26548d-ebba-4f16-89cd-f090263c335b)

<H1>flowchart</H1>

![WhatsApp Image 2023-11-26 at 21 21 09](https://github.com/sentosa2505/PERTEMUAN-10/assets/148040303/af7dbadb-bd3c-414a-950a-72f0518613e1)

<P>PENJELASAN</P>

Penjelasan dari flowchart:

1. **Mulai**: Program dimulai.
2. **Inisialisasi Data**: Menginisialisasi kamus kosong `data_mahasiswa` untuk menyimpan data mahasiswa.
3. **Loop Pemilihan Menu**: Memulai loop tak terbatas untuk secara berulang menampilkan menu dan menunggu input pengguna.
4. **Tampilkan Menu**: Menampilkan opsi menu kepada pengguna.
5. **Input Pengguna**: Mendapatkan pilihan pengguna (1-6) sebagai input.
6. **Opsi Menu**:
   - **1: Tambah Data**: Memanggil fungsi `tambah_data` untuk menambahkan data mahasiswa baru ke dalam kamus.
   - **2: Ubah Data**: Memanggil fungsi `ubah_data` untuk mengubah data mahasiswa yang sudah ada di dalam kamus.
   - **3: Hapus Data**: Memanggil fungsi `hapus_data` untuk menghapus data mahasiswa yang sudah ada di dalam kamus.
   - **4: Tampilkan Data**: Memanggil fungsi `tampilkan_data` untuk menampilkan data semua mahasiswa dalam format tabel.
   - **5: Cari Data**: Memanggil fungsi `cari_data` untuk mencari dan menampilkan data mahasiswa tertentu.
   - **6: Keluar**: Mencetak "Program selesai" dan keluar dari loop, mengakhiri program.
   - **Pilihan Tidak Valid**: Jika pengguna memasukkan pilihan selain 1-6, tampilkan "Pilihan tidak valid. Masukkan angka 1-6."
7. **Selesai**: Program berakhir.

Flowchart ini memberikan gambaran tingkat tinggi tentang bagaimana program mengalir dan tindakan apa yang diambil berdasarkan input pengguna.

<H1>KONTAK</H1>

```python
from prettytable import PrettyTable

#Buat dictionary daftar kontak
daftar_kontak = {
    'Ari': '081234567',
    'Dina': '087654321',
}

#Tampilkan kontaknya Ari
print(f"Kontak Ari: {daftar_kontak.get('Ari', 'Kontak tidak ditemukan')}")

#Tambah kontak baru dengan nama Riko, nomor 087654544
daftar_kontak['Riko'] = '087654544'
print("Kontak Riko ditambahkan.")

#Ubah kontak Dina dengan nomor baru 088999776
if 'Dina' in daftar_kontak:
    daftar_kontak['Dina'] = '088999776'
    print("Nomor kontak Dina diubah.")
else:
    print("Kontak Dina tidak ditemukan.")

#Tampilkan semua Nama
print("Semua Nama:")
for nama in daftar_kontak.keys():
    print(nama)

#Tampilkan semua Nomor
print("\nSemua Nomor:")
for nomor in daftar_kontak.values():
    print(nomor)

#Tampilkan daftar Nama dan nomornya menggunakan pretty table
tabel_kontak = PrettyTable()
tabel_kontak.field_names = ["Nama", "Nomor"]
for nama, nomor in daftar_kontak.items():
    tabel_kontak.add_row([nama, nomor])

print("\nDaftar Nama dan Nomor:")
print(tabel_kontak)

#Hapus kontak Dina
if 'Dina' in daftar_kontak:
    del daftar_kontak['Dina']
    print("\nKontak Dina dihapus.")
else:
    print("\nKontak Dina tidak ditemukan.")
```

![Screenshot (18)](https://github.com/sentosa2505/PERTEMUAN-10/assets/148040303/899d221a-397d-46c1-9e8a-9772d5f2050f)


