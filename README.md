# Pratikum6
# Latihan Menggunakan Function dan Lambda pada python dan membuat program crud sederhana

RIDHO AKBAR PRATAMA

312210294

TI.22.B1

# Repository ini dibuat sebagai nilai tugas Bahasa Pemrograman
1. Pertama buat folder Pratikum6.py lalu di tambah file dengan nama Latihan.py dan Tugas.py

![Screenshot (209)](https://user-images.githubusercontent.com/115474016/205481251-5d460fed-33c2-4aca-87a9-a0bf1a17d946.png)

2. lalu buka file latihan.py dengan perintah soal nya seperti ini
![Screenshot (211)](https://user-images.githubusercontent.com/115474016/205481635-40af7a04-59f7-45d0-902e-64a21b47a397.png)

3. untuk menyelesaikan latihan soal di atas, masukan code seperti ini
                                            
                                            import math
                                            # Ridho Akbar Pratama 312210294-TI22B1


                                            def a(n): return lambda x: x**n


                                            lambdaA = a(4)
                                            print(lambdaA(4))


                                            def b(i, j):
                                                return lambda x, y: math.sqrt(x**i + y**j)


                                            lambdaB = b(4, 0)
                                            print(lambdaB(3, 0))


                                            def c(*args):
                                                return lambda *params: sum(args) / len(params)


                                            lambdaC = c(1, 2, 3, 4, 5)
                                            print(lambdaC(2, 2, 5))


                                            def d(firstname):
                                                return lambda *lastname: "".join(set(firstname)) + "".join(set(lastname))


                                            lambdaD = d("Ridho")
                                            print(lambdaD("Akbar", "Pratama"))

                                                      
                                                     
4. maka tampilan dari code di atas akan menjadi seperti ini
![Screenshot (212)](https://user-images.githubusercontent.com/115474016/205481758-6c8de7bf-b64b-4730-b762-11dade7c6fa4.png)

5. Buat program sederhana dengan mengaplikasikan penggunaan fungsi
yang akan menampilkan daftar nilai mahasiswa, dengan ketentuan:


• Fungsi tambah() untuk menambah data


• Fungsi tapilkan() untuk menampilkan data


• Fungsi hapus(nama) untuk menghapus data berdasarkan nama


• Fungsi ubah(nama) untuk mengubah data berdasarkan nama

6. sebelum membuat program nya, kita buat terlebih dahulu flowchart nya seperti ini

![image](https://user-images.githubusercontent.com/115474016/205482980-69b0cc50-8973-40fb-9b7d-1fba342c8e0b.png)




7. setelah flowchart sudah di bikin, lanjut membuka file Tugas.py dan masukan code seperti ini untuk membuat program sederhana yang telah ditugaskan
                                    
                                    
                                    # import tabulate
                                    from tabulate import tabulate  

                                    # Ridho akbar pratama
                                    # TI22B1

                                    dataMahasiswa = {
                                        'No': [],
                                        'Nim': [],
                                        'Nama': [],
                                        'Tugas': [],
                                        'Uts': [],
                                        'Uas': [],
                                        'Nilai Akhir': [],
                                    }
                                    no = 0
                                    # fungsi untuk menampilkan data

                                    def tampilkan():
                                        print("Berikut data yang ada")
                                        print(tabulate(dataMahasiswa, headers=[
                                            'No', 'Nim', 'Nama', 'Tugas', 'UTS', 'UAS', 'Nilai Akhir'], tablefmt="fancy_grid"))

                                    # fungsi untuk menambahkan data


                                    def tambah(no):
                                        # menginput data
                                        nim = int(input("Masukan NIM : "))
                                        nama = input("Masukan Nama : ")
                                        tugas= int(input("Masukan Nilai Tugas : "))
                                        uts = int(input("Masukan Nilai Uts : "))
                                        uas = int(input("Masukan Nilai Uas : "))
                                        nilai_akhir = (tugas * 40 / 100) + (uts * 45 / 100) + (uas * 55 / 100)
                                        # menambahkan data
                                        dataMahasiswa['No'].append(no)
                                        dataMahasiswa['Nim'].append(nim)
                                        dataMahasiswa['Nama'].append(nama)
                                        dataMahasiswa['Uts'].append(uts)
                                        dataMahasiswa['Tugas'].append(tugas)
                                        dataMahasiswa['Uas'].append(uas)
                                        dataMahasiswa['Nilai Akhir'].append(nilai_akhir)
                                        print('Data berhasil ditambahkan.')
                                        # print(tabulate(dataMahasiswa, headers=[
                                        #       'NIM', 'Nama', 'Tugas', 'UTS', 'UAS', 'Nilai Akhir'], tablefmt="fancy_grid"))

                                    # fungsi untuk Mengedit data


                                    def ubah(nama):
                                        # cek jika ada nama tersebut di dataMahasiswa
                                        if nama in dataMahasiswa['Nama']:
                                            # cari posisi indexnya lalu disimpan di nimIndex
                                            namaIndex = dataMahasiswa['Nama']. index(nama)  
                                            print("Print Data yang mau diedit")
                                            # perulangan mengedit data dalam bentuk pilihan
                                            while True:
                                                editApa = int(input(
                                                    "(1) Nim, \n (2) Nama, \n (3) Nilai Tugas, \n (4) Nilai Uts, \n (5) Nilai Uas, \n (0) Save Perubahan & exit \n :"))
                                                print("")

                                                if editApa == 1:
                                                    # merubah nim
                                                    newNim = int(input("Masukan Nim :"))
                                                    dataMahasiswa['Nim'][namaIndex] = newNim
                                                elif editApa == 2:
                                                    # merubah nama
                                                    newNama = int(input("Masukan Nama :"))
                                                    dataMahasiswa['Nama'][namaIndex] = newNama
                                                elif editApa == 3:
                                                    # merubah nilai tugas dan nilai akhir
                                                    newTugas = int(input("Masukan Nilai Tugas :"))
                                                    nilai_akhir = (newTugas * 40 / 100) + (dataMahasiswa['Uts'][namaIndex] * 45 / 100) + (
                                                        dataMahasiswa['Uas'][namaIndex] * 55 / 100)
                                                    dataMahasiswa['Tugas'][namaIndex] = newTugas
                                                    dataMahasiswa['Nilai Akhir'][namaIndex] = nilai_akhir            
                                                elif editApa == 4:
                                                    # merubah nilai uts dan nilai akhir
                                                    newUts = int(input("Masukan Nilai Uts :"))
                                                    nilai_akhir = (newTugas * 40 / 100) + (dataMahasiswa['Uts'][namaIndex] * 45 / 100) + (dataMahasiswa['Uas'][namaIndex] * 55 / 100)
                                                    dataMahasiswa['Uts'][namaIndex] = newUts
                                                    dataMahasiswa['Nilai Akhir'][namaIndex] = nilai_akhir
                                                elif editApa == 5:
                                                    # merubah nilai uas dan nilai akhir
                                                    newUas = int(input("Masukan Nilai Uas :"))
                                                    nilai_akhir = (newTugas * 40 / 100) + (dataMahasiswa['Uts'][namaIndex] * 45 / 100) + (dataMahasiswa['Uas'][namaIndex] * 55 / 100)
                                                    dataMahasiswa['Uas'][namaIndex] = newUas
                                                    dataMahasiswa['Nilai Akhir'][namaIndex] = nilai_akhir                        
                                                elif editApa == 0:
                                                    print('Perubahan Data berhasil disimpan,')
                                                    break
                                            else:
                                                print("data tidak ditemukan")

                                    # fungsi untuk Menghapus data


                                    def hapus(nama):
                                        if nama in dataMahasiswa['Nama']:
                                            namaIndex = dataMahasiswa['Nama'].index(nama)
                                            # menghapus data berdasarkan position index pada nama
                                            del dataMahasiswa['No'][namaIndex]
                                            del dataMahasiswa['Nim'][namaIndex]
                                            del dataMahasiswa['Nama'][namaIndex]
                                            del dataMahasiswa['Tugas'][namaIndex]
                                            del dataMahasiswa['Uts'][namaIndex]
                                            del dataMahasiswa['Uas'][namaIndex]
                                            del dataMahasiswa['Nilai Akhir'][namaIndex]
                                            print("data berhasil dihapus. ")
                                        else:
                                            print("data tidak ditemukan")


                                    # fungsi untuk Mencari data

                                    # melakukan perulangan menggunakan while sampai user menekan huruf Q perulangan akan berhenti
                                    while True:
                                        # opsi input pilihan C,R,U,D,F,Q
                                        tanya = input(
                                            "(C) Menambah data,\n (R) Melihat semua data,\n (U) Update data,\n (D) Menghapus data,\n (Q) Keluar program : ")
                                        if tanya == "C":
                                            while True:
                                                no += 1
                                                # memanggil fungsi tambahData dan memparsing data no
                                                tambah(no)
                                                tambahDataLagi = input("Tambah data lagi ? (y/n) :")
                                                if tambahDataLagi == 'n':
                                                    break
                                        elif tanya == "R":
                                            # menampilkan data dalam bentuk table menggunakan package tabulate
                                            tampilkan()
                                            print("")
                                        elif tanya == "U":
                                            print(tabulate(dataMahasiswa, headers=[
                                            'No', 'Nim', 'Nama', 'Tugas', 'UTS', 'UAS', 'Nilai Akhir'], tablefmt="fancy_grid"))
                                            nama = input('Masukan nama yang mau di edit :')
                                            print("")
                                            ubah(nama)
                                        elif tanya == "D":
                                            print(tabulate(dataMahasiswa, headers=[
                                            'No', 'Nim', 'Nama', 'Tugas', 'UTS', 'UAS', 'Nilai Akhir'], tablefmt="fancy_grid"))
                                            nama = input('Masukan nama yang mau di hapus :')
                                            print("")
                                            hapus(nama)
                                        elif tanya == "Q":
                                            print("")
                                            print("Anda telah keluar dari program.")
                                            break
                                            
                                       
8. Hasil output dari program di atas memiliki beberapa opsi seperti "C", "R", "U", "D", dan "Q"
  - jika memilih opsi "C" untuk menambah data maka hasil nya seperti ini
  ![Screenshot (213)](https://user-images.githubusercontent.com/115474016/205482581-7a7b352d-33f9-4a2c-a493-65a79e36a01d.png)
  
  - jika memilih opsi "R" unutuk melihat data maka hasil nya seperti ini
  ![Screenshot (214)](https://user-images.githubusercontent.com/115474016/205482632-6d8a69ad-2c60-4c08-9ebd-b3ae15abcc7c.png)
  
  - jika memilih opsi "U" untuk mengupdet atau mengubah data maka hasil nya seperti ini
  ![Screenshot (215)](https://user-images.githubusercontent.com/115474016/205482670-23902dfd-d5dc-4f2e-8c86-63b39df6ff4f.png)
  
  - jika memilih opsi "D" untuk menghapus data maka hasil nya seperti ini
  ![Screenshot (216)](https://user-images.githubusercontent.com/115474016/205482701-b0b7326d-9021-4363-9909-9a05ea4e8e61.png)
  
  - jika memilih opsi "Q" untuk keluar dari program maka hasil nya seperi ini
  ![Screenshot (217)](https://user-images.githubusercontent.com/115474016/205482720-22ae536a-ca83-4d2e-ad03-b58371c851ee.png)
  
  
                                                      SEKIAN HASIL PROJECT SAYA
                                                             TERIMA KASIH





    
        



