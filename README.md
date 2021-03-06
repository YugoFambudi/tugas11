# <p align="center"> **Tugas Praktikum 11**

# Latihan 1
***Perintah :***
Ubahlah kode dibawah ini menjadi fungsi lambada
```py
import math


def a(x):
    return x**2

def b(x, y):
    return math.sqrt(x**2 + y**2)

def c(*args):
    return sum(args)/len(args)

def d(s):
    return "".join(set(s))
```

Penyelesaian

> before
```
def a(x):
    return x**2
```
> after 
```py
a=lambda x: (x**2)
```
nomor 2 :
> before
```py
def b(x,y):
    return math.sqrt(x**2 + y**2)
```
> after
```py
b=lambda x,y: math.sqrt(x**2 + y**2)
```
nomor 3
> before
```py
def c(*args):
    return sum(args)/len(args)
```
> after
```py
c=lambda *args:sum(args)/len(args)
```
nomor 4:
> before
```py
def d(s):
    return "".join(set(s))
```
> after
```py
d=lambda s: "".join(set(s))
```

# ***Praktikum***

Perintah
Buat program sederhana dengan mengaplikasian penggunaan fungsi yang akan ditampilkan daftar nilai mahasiswa, dengan ketentuan:
1. Fungsi **tambah()** untuk menambahkan data
2. Fungsi **tampilkan()** untuk menampilkan
3. Fungsi **hapus(nama)** untuk menghapus data berdasarkan nama
4. Fungsi **ubah(nama)** untuk mengubah data berdasarkan nama

Buat flowchart dan penjelasan programnya pada README.md.
Commit dan push ke repository ke git hub

Penyelesaian

Membuat program looping supaya program bisa berulang.
```py
while True:
    print('\ntambah\t(1)\nubah\t(2)\nhapus\t(3)\nlihat\t(4)\nkeluar\t(5) ')                                                                                     
    c = input("\nsilahkan masukan pilihan : ")

Kemudian membuat format if untuk memasukan pilihan ,
sebagai contoh apabila memilih (1) akan menambah data
```py
if (c.lower() == '1'):                                               
        print('\nTambah Data Mahasiswa Baru')
        nama= input("Masukkan Nama\t\t: ")                                        
        nim= input("Masukkan NIM\t\t: ")                                         
        nilaiTugas= int(input("Masukkan Nilai Tugas\t: "))                              
        nilaiUts= int(input("Masukkan Nilai UTS\t: "))                                   
        nilaiUas= int(input("Masukkan Nilai UAS\t: "))                                    
        nilaiAkhir= (0.30 * nilaiTugas) + (0.35 * nilaiUts) + (0.35 * nilaiUas)              
        dataMhs[nama]= nim, nilaiTugas, nilaiUts, nilaiUas, nilaiAkhir                         
        print("\nData Berhasil Ditambahkan!")
```

Lakukan percabangan if (elif) untuk melaksanakan pilihan yang lain
```py
elif (c.lower() == '2'):                                                                    
        print('\nMengedit Data Mahasiswa')
        nama = input("Masukkan Nama: ")                                                         
        if nama in dataMhs.keys():                              
            nim= input("Masukkan NIM Baru\t: ")                              
            nilaiTugas= int(input("Masukkan Nilai Tugas\t: "))                           
            nilaiUts= int(input("Masukkan Nilai UTS\t: "))                           
            nilaiUas= int(input("Masukkan Nilai UAS\t: "))                           
            nilaiAkhir= (0.30 * nilaiTugas) + (0.35 * nilaiUts) + (0.35 * nilaiUas)          
            dataMhs[nama] = nim, nilaiTugas, nilaiUts, nilaiUas, nilaiAkhir                      
            print("\nData Berhasil Di Update!")
```

Lalu menggunakan else untuk apabila salah memasukan pilihan inputan 
```py
else:
    print("\nMohon maaf input salah\n\nSilahkan pilih menu yang tersedia: ")                                                                                                            
```

# Flowchart
![.](Gambar/flowchart`.png)

# Program
```py
dataMhs = {}                                                                                     
print("==================================================================")
print("|                 PROGRAM INPUT NILAI MAHASISWA                  |")
print("==================================================================")

while True:
    print('\ntambah\t(1)\nubah\t(2)\nhapus\t(3)\nlihat\t(4)\nkeluar\t(5) ')                                                                                     
    c = input("\nsilahkan masukan pilihan : ")                                
    if (c.lower() == '1'):                                               
        print('\nTambah Data Mahasiswa')
        nama= input("Masukkan Nama\t\t: ")                                        
        nim= input("Masukkan NIM\t\t: ")                                         
        nilaiTugas= int(input("Masukkan Nilai Tugas\t: "))                              
        nilaiUts= int(input("Masukkan Nilai UTS\t: "))                                   
        nilaiUas= int(input("Masukkan Nilai UAS\t: "))                                    
        nilaiAkhir= (0.30 * nilaiTugas) + (0.35 * nilaiUts) + (0.35 * nilaiUas)              
        dataMhs[nama]= nim, nilaiTugas, nilaiUts, nilaiUas, nilaiAkhir                         
        print("\nData Berhasil Ditambahkan!")
    elif (c.lower() == "2"):                                                                    
        print('\nMengubah Data Mahasiswa')
        nama = input("Masukkan Nama\t\t: ")                                                         
        if nama in dataMhs.keys():                              
            nim= input("Masukkan NIM Baru\t: ")                              
            nilaiTugas= int(input("Masukkan Nilai Tugas\t: "))                           
            nilaiUts= int(input("Masukkan Nilai UTS\t: "))                           
            nilaiUas= int(input("Masukkan Nilai UAS\t: "))                           
            nilaiAkhir= (0.30 * nilaiTugas) + (0.35 * nilaiUts) + (0.35 * nilaiUas)          
            dataMhs[nama] = nim, nilaiTugas, nilaiUts, nilaiUas, nilaiAkhir                      
            print("\nData Berhasil Di Update!")
        else:                                                                                    
            print("Data tidak ditemukan!")                                                                                             
    elif (c.lower() == '3'):                                                                    
        nama = input("Masukkan Nama:  ")                                                        
        if nama in dataMhs.keys():                                                              
            del dataMhs[nama]                                                                   
            print("Data Telah dihapus!")
        else:
            print("Data Mahasiswa Tidak Ada".format(nama))                                     
    elif (c.lower() == '4'):                                                                    
        if dataMhs.items():                                                                     
            print("\n                      DAFTAR NILAI MAHASISWA                    ")
            print("==================================================================")
            print("| No |     Nama     |    NIM    | Tugas |  UTS  |  UAS  |  Akhir |")
            print("==================================================================")
            i = 0
            for x in dataMhs.items():
                i += 1
                print("| {6:2} | {0:12s} | {1:9s} | {2:5} | {3:5} | {4:5} | {5:6} |".format(x[0], x[1][0], x[1][1], x[1][2], x[1][3], x[1][4], i))  
            print("==================================================================")
        else:
            print("\n                      DAFTAR NILAI MAHASISWA                    ")
            print("==================================================================")
            print("| No |     Nama     |    NIM    | Tugas |  UTS  |  UAS  |  Akhir |")
            print("==================================================================")
            print("|                          TIDAK ADA DATA!                       |")
            print("==================================================================")         
    elif (c.lower() == '5'):                                                                   
        print('\n=====terimakasih=====\n')
        print(21*'=')
        print("Nama\t: Yugo Rilo Fambudi\nKelas\t: TI.21.C5\nNIM\t: 312110228")
        print(21*'=')
        break                                                                                 

    else:
        print("\nMohon maaf input salah\n\nSilahkan pilih menu yang tersedia: ")
```

# Output Program
 ***Output apabila akan menambahkan data***

![.](Gambar/1.png)

***Output ketika merubah data yang telah dimasukan***

![.](Gambar/2.png)

***Output apabila ingin menambahkan data lagi***

![.](Gambar/`1.png)

***Output saat menghapus data***

![.](Gambar/3.png)

***Output ketika melihat data terakhir***

![.](Gambar/4.png)

***Output untuk keluar/berhenti***

![.](Gambar/5.png)

# <p align="center"> TERIMA KASIH
