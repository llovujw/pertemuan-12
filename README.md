# Pertemuan ke 12

## Profil
| Variable | Isi |
| -------- | --- |
| **Nama** | Intan Virginia Aulia Putri |
| **NIM** | 312310657 |
| **Kelas** | TI.23.A.6 |
| **Mata Kuliah** | Bahasa Pemrograman |

### Tugas Praktikum
Buat program sederhana dengan mengaplikasikan penggunaan class. Buatlah class untuk menampilkan daftar nilai mahasiswa, dengan ketentuan:
- Method `tambah()` untuk menambah data
- Method `tampilkan()` untuk menampilkan data
- Method `hapus(nama)` untuk menghapus data berdasarkan nama
- Method `ubah(nama)` untuk mengubah data berdasarkan nama
- Buat diagram class, flowchart dan penjelasan programnya pada README.md
- Commit dan push repository ke github
``` Python
class mahasiswa():
    def __init__(self):
        self.nama = []
        self.nim = []
        self.uts = []
        self.uas = []
        self.tugas = []


    # Menambahkan data inputan 
    def tambah(self):
        print("Tambah data\n")
        nama    = input("Nama           : ")
        self.nama.append(nama)
        nim     = int(input("NIM            : "))
        self.nim.append(nim)
        uts     = int(input("Nilai UTS      : "))
        self.uts.append(uts)
        uas     = int(input("Nilai UAS      : "))
        self.uas.append(uas)
        tugas   = int(input("Nilai Tugas    : "))
        self.tugas.append(tugas)


    # Menampilkan seluruh data 
    def lihat(self):
        for i in range(len(self.nama)):
            print(f"\nData ke -{i+1}")
            print(f"Nama Mahasiswa: {self.nama[i]}")
            print(f"NIM Mahasiswa : {self.nim[i]}")
            print(f"Nilai UTS     : {self.uts[i]}")
            print(f"Nilai UAS     : {self.uas[i]}")
            print(f"Nilai TUGAS   : {self.tugas[i]}")
                
        # Menghapus inputan nama
    def hapus(self, nama):
        print("Hapus data inputan")
        nama = (input("\nMasukan Nama berdasarkan inputan : "))
        if nama in self.nama:
            print("Data {0} berhasil di hapus".format(nama))
            index = self.nama.index(nama)
            del self.nama[index]
            del self.nim[index]
            del self.uts[index]
            del self.uas[index]
            del self.tugas[index]
        else:
            print("NAMA {0} TIDAK ADA!".format(nama))
    
        # Mengubah data nama inputan
    def ubah(self, nama):
        nama = input("Nama yang ingin di ubah : ")
        if nama in self.nama:
            index = self.nama.index(nama)
            self.nim[index]     = int(input("NIM            : "))
            self.uts[index]     = int(input("Nilai UTS      : "))
            self.uas[index]     = int(input("Nilai UAS      : "))
            self.tugas[index]   = int(input("Nilai Tugas    : "))

            print("\nData {0} berhasil di ubah".format(nama))
        else:
            print("NAMA {0} TIDAK ADA!".format(nama))


print("="*20)
print("|PROGRAM INPUT DATA|")
print("="*20)

data = mahasiswa()

while True: 
    print()
    menu = input("[(T)ambah, (L)ihat, (H)apus, (U)bah, (K)eluar] : ")
    print("~"*78)
    print()

    if menu.lower() == 't':
        data.tambah()

    elif menu.lower() == 'l':
        if data.nama:
            data.lihat()
        else:
            print("BELUM ADA DATA!, pilih [T/t] untuk menambah data")       

    elif menu.lower() == "h":
        data.hapus(data.nama)


    elif menu.lower() == "u":
        data.ubah(data.nama) 

    elif menu.lower() == "k":
        print("Program selesai, Terima Kasih :) ")
        break

    else:
        print("\n INPUT {} TIDAK ADA!, Silakan pilih [T/L/H/U/K] untuk menjalankan program!".format(menu))
```
Penjelasan
1. Class `mahasiswa`:
    - Kelas ini memiliki konstruktor (__init__) yang digunakan untuk inisialisasi objek. Setiap objek memiliki atribut nama, nim, uts, uas, dan tugas yang bersifat list untuk menyimpan data mahasiswa.
2. Metode `tambah(self)`:
    - Metode ini digunakan untuk menambahkan data mahasiswa baru ke dalam objek.
    - Pengguna diminta memasukkan nama, NIM, nilai UTS, nilai UAS, dan nilai Tugas.
    - Data tersebut kemudian ditambahkan ke dalam list yang sesuai.
3. Metode `lihat(self)`:
    - Metode ini digunakan untuk menampilkan seluruh data mahasiswa dalam objek.
    - Data mahasiswa ditampilkan dalam bentuk loop dengan menggunakan indeks.
    - Setiap detail mahasiswa (nama, NIM, nilai UTS, UAS, dan Tugas) ditampilkan.
4. Metode `hapus(self, nama)`:
    - Metode ini digunakan untuk menghapus data mahasiswa berdasarkan nama dari objek.
    - Pengguna diminta memasukkan nama mahasiswa yang ingin dihapus.
    - Jika nama tersebut ada dalam list nama, data mahasiswa tersebut dihapus dari semua list yang bersesuaian.
5. Metode `ubah(self, nama)`:
    - Metode ini digunakan untuk mengubah data mahasiswa berdasarkan nama dari objek.
    - Pengguna diminta memasukkan nama mahasiswa yang ingin diubah.
    - Jika nama tersebut ada dalam list nama, data mahasiswa tersebut diubah dengan nilai yang baru.
6. Objek `data`:
    - Objek ini dibuat dari kelas `mahasiswa` dan digunakan untuk menyimpan dan mengelola data mahasiswa.
7. Menu Utama:
    - Program memiliki loop utama yang terus berjalan sampai pengguna memilih untuk keluar.
    - Setiap iterasi loop, pengguna diminta untuk memilih aksi seperti tambah, lihat, hapus, ubah, atau keluar.
    - Aksi yang dipilih dijalankan sesuai dengan metode yang telah didefinisikan dalam objek `data`.

#### Tampilan output
![img 1](screenshot/ss2.png)
![img 1](screenshot/ss3.png)
![img 1](screenshot/ss4.png)
![img 1](screenshot/ss5.png)
