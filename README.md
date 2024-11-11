# Program Penghitung Nilai Akhir Mahasiswa
Program ini untuk menghitung nilai akhir mahasiswa berdasarkan bobot nilai tugas, UTS, dan UAS yang telah ditentukan. Program ini juga menampilkan data mahasiswa dalam bentuk tabel.

# Deskripsi Program
Program ini dibuat menggunakan bahasa python dengan fitur:
-menyimpan dan menghitung nilai akhir mahasiswa
-nilai akhir dihitung berdasarkan bobot tertentu dari nilai tugas, UTS, dan UAS.
-Pengguna dapat memasukkan data mahasiswa, yang meliputi nama, NIM, nilai tugas, nilai UTS, dan nilai UAS,
-lalu program akan menghitung nilai akhir berdasarkan rumus yang sudah ditentukan. Semua data yang dimasukkan akan disimpan dalam bentuk list yang berisi dictionary untuk setiap mahasiswa.
-Setelah semua data dimasukkan, program akan menampilkan daftar data mahasiswa dalam bentuk tabel yang rapi.

# Flowchart Program


# Kode Program
```python
# Inisialisasi list untuk menyimpan data
data_mahasiswa = []

# Fungsi untuk menghitung nilai akhir
def hitung_nilai_akhir(tugas, uts, uas):
    return round((tugas * 0.3) + (uts * 0.35) + (uas * 0.35), 2)

# Input data mahasiswa
while True:
    nama = input("Nama: ")
    nim = input("NIM: ")
    tugas = int(input("Nilai Tugas: "))
    uts = int(input("Nilai UTS: "))
    uas = int(input("Nilai UAS: "))
    nilai_akhir = hitung_nilai_akhir(tugas, uts, uas)

    # Simpan data ke dalam dictionary
    data_mahasiswa.append({
        "Nama": nama,
        "NIM": nim,
        "Tugas": tugas,
        "UTS": uts,
        "UAS": uas,
        "Akhir": nilai_akhir
    })

    # Tanyakan apakah ingin menambah data lagi
    tambah = input("Tambah data (y/t)? ")
    if tambah.lower() != 'y':
        break

# Tampilkan data dalam bentuk tabel
print("\n| No | Nama     | NIM   | Tugas | UTS | UAS | Akhir |")
print("=" * 53)
for i, mhs in enumerate(data_mahasiswa, start=1):
    print(f"| {i:<2} | {mhs['Nama']:<8} | {mhs['NIM']:<5} | {mhs['Tugas']:<5} | {mhs['UTS']:<3} | {mhs['UAS']:<3} | {mhs['Akhir']:<5} |")
```

# Output program
```
PS C:\Users\AXIOO\Documents\KULIAH\tugas praktikum 5> python -u "c:\Users\AXIOO\Documents\KULIAH\tugas praktikum 5\praktikum5.py"
Nama: fitri
NIM: 312410085
Nilai Tugas: 70
Nilai UTS: 80
Nilai UAS: 90
Tambah data (y/t)? y
Nama: ramadhani
NIM: 312410085
Nilai Tugas: 85
Nilai UTS: 95
Nilai UAS: 100
Tambah data (y/t)? t

| No | Nama     | NIM   | Tugas | UTS | UAS | Akhir |
=====================================================
| 1  | fitri    | 312410085 | 70    | 80  | 90  | 80.5  |
| 2  | ramadhani | 312410085 | 85    | 95  | 100 | 93.75 |
PS C:\Users\AXIOO\Documents\KULIAH\tugas praktikum 5>
```

# Cara kerja
1. Program pertama kali menginisialisasi list kosong bernama data_mahasiswa untuk menyimpan data setiap mahasiswa.
2. Fungsi hitung_nilai_akhir digunakan untuk menghitung nilai akhir berdasarkan formula:
   \[
   \text{nilai akhir} = (\text{nilai tugas} \times 0.3) + (\text{nilai UTS} \times 0.35) + (\text{nilai UAS} \times 0.35)
   \]
3. Program meminta pengguna untuk memasukkan data nama, NIM, nilai tugas, UTS, dan UAS.
4. Setelah nilai akhir dihitung menggunakan fungsi hitung_nilai_akhir, semua data tersebut disimpan dalam dictionary dan ditambahkan ke dalam list data_mahasiswa.
5. Pengguna dapat memilih untuk menambahkan data mahasiswa lain atau mengakhiri proses input.
6. Setelah input selesai, program akan mencetak data mahasiswa dalam bentuk tabel dengan kolom nomor, nama, NIM, nilai tugas, UTS, UAS, dan nilai akhir.
