# Praktikum6

Nama : Danang Nurcahyo

NIM : 312210004

Kelas : TI.22.A1

## DAFTAR ISI <br>
| No | Description | Link |
|-----|------|-----|
|1|Latihan|[Click Here](#latihan)|
|2|Praktikum-5|[Click Here](#praktikum-5)|
|3|Flowchart Praktikum-5|[Click Here](#flowchart-praktikum-5)|

## Latihan
Buat Dictionary daftar kontak
- Nama sebagai key, dan nomor sebagai value
- Tampilkan kontaknya Ari
- Tambah kontak baru dengan nama Riko, nomor 087654544
- Ubah kontak Dina dengan nomor baru 088999776
- Tampilkan semua Nama
- Tampilkan semua Nomor
- Tampilkan daftar Nama dan nomornya
- Hapus kontak Dina

### Langkah-langkah :
1. Buat program terlebih dahulu seperti gambar di bawah ini

![Screenshot (214)](https://user-images.githubusercontent.com/115867244/204136213-aa23be2d-0652-458d-b59d-0cd1d04bde5a.png)

    daftarKontak = {"Nama":"Nomer Telpon"}
    kontak       = {'Ari':'081267888', 'Dina' : '087677776'}

    #print
    print(30*"═")
    print("    Nama    |  Nomor Telepon  ") #prinr daftarkontak
    print(30*"-")
    print("   # Ari    | ", kontak['Ari']) #print kontak Ari
    print("   # Dina   | ", kontak['Dina']) #print kontak Dina
    print(30*"═")

    #Tampilkan kontaknya Ari
    print("Tampilkan kontaknya Ari")
    print("    Ari     | ", kontak['Ari']) #print kontak Ari
    print(30*"═")
    #Tambah kontak baru dengan nama Riko, nomor 087654544
    print("Tambah kontak baru dengan nama Riko, nomor 087654544")
    kontak['Riko'] = '087654544'
    print("    Riko    | ", kontak['Riko'])
    print(30*"═")

    #Ubah kontak Dina dengan nomor baru 088999776
    print("Ubah kontak Dina dengan nomor baru 088999776")
    kontak['Dina'] = '088999776'
    print("    Dina    | ", kontak['Dina'])
    print(30*"═")

    #Tampilkan semua Nama
    print("Tampilkan semua Nama")
    print(kontak.keys())
    print(30*"═")

    #Tampilkan semua Nomor
    print("Tampilkan semua Nomor")
    print(kontak.values())
    print(30*"═")

    #Tampilkan daftar Nama dan nomornya
    print("Tampilkan daftar Nama dan nomornya")
    print(kontak.items())
    print(30*"═")

    #MengHapus kontak Dina
    print("Hapus kontak Dina")
    kontak.pop('Dina')
    print(kontak.items())
    print(30*"═")
    
2. Hasil Run

![Screenshot (215)](https://user-images.githubusercontent.com/115867244/204136376-31daf9f5-eae7-49e6-b943-c7780d1dc106.png)

![Screenshot (216)](https://user-images.githubusercontent.com/115867244/204136385-0482a094-e5ff-40f4-94fc-277e28714d64.png)

## Praktikum 5
Buat program sederhana yang akan menampilkan daftar nilai mahasiswa, dengan ketentuan :
- Program dibuat dengan menggunakan **Dictionary**
- Tampilkan menu pilihan : (Tambah Data, Ubah Data, Hapus Data, Tampilkan Data, Cari Data)
- Nilai Akhir diambil dari perhitungan 3 komponen nilai (tugas : 30%, UTS : 35%, UAS : 35%)
- Buat flowchart dan penjelasan programnya pada README.md.
- Commit dan push repository ke github.

### Langkah-langkah :
1. Buat programnya terlebih dahulu seperti gambar di bawah ini

![Screenshot (217)](https://user-images.githubusercontent.com/115867244/204138112-82896320-aa27-46c1-bc42-e88745caac95.png)

    print("====================================")
    print("======>  Program Input Nilai  <======")
    print("====================================")
    data = {}
    while True:
        print("")
        m = input("===>> (L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar : <=== ")
        print("================================================================")
        print("| NO |  Nama     |   Nim    |  Tugas  |  UTS  |  UAS  |   Akir |")
        print("================================================================")
        print(">>>>>>>>>>>>>>>>>>>>>>>> TIDAK ADA DATA <<<<<<<<<<<<<<<<<<<<<<<<")
        if m.lower() == 'k':
            break

        elif m.lower() == 'l':
            print("----- DAFTAR NILAI -----")
            print("==================================================================================")
            print("| NO |   NAMA     |   NIM        |  TUGAS   |   UTS     |   UAS      |  AKHIR    |")
            print("==================================================================================")
            i = 0
            for x in data.items():
                i += 1
                print("|  1 |{0:9}   |{1:9}     |{2:9} |{3:9}  |{4:9}   |{5:9}  |" .format(x[0], x[1][0],
                                                                                           x[1][1], x[1][2], x[1][3],
                                                                                           x[1][4], i))

            else:
                print("====================>>>>>>>>>>>>> Tidak Ada Data <<<<<<<<<<<<<====================")

        elif m.lower() == 't':
            print("--------------- Tambah Data ---------------")
            nama = input("Nama                  : ")
            nim = input("Nim                   : ")
            tugas = float(input("Masukan Nilai Tugas   : "))
            uts = float(input("Masukan Nilai UTS     : "))
            uas = float(input("Masukan Nilai UAS     : "))
            akhir = (int(tugas) * .30) + (int(uts) * .35) + (int(uas) * .35)
            data[nama] = nim, tugas, uts, uas, akhir

        elif m.lower() == 'u':
            print("----- Ubah Data Mahasiswa -----")
            nama = input("Nama  : ")
            if nama in data.keys():
                nim = input("Nim : ")
                tugas = float(input("masukan nilai tugas : "))
                uts = float(input("masukan nilai Uts : "))
                uas = float(input("masukan nilai uas : "))
                akhir = (int(tugas) * .30) + (int(uts) * .35) + (int(uas) * .35)
                data[nama] = nim, tugas, uts, uas, akhir

            else:
                print("Tidak Ada data")

        elif m.lower() == 'h':
            print("Hapus Data Mahasiswa")
            nama = input("nama : ")
            if nama in data.keys():
                print("Datanya", nama, "adalah {0}".format(data[nama]))
            else:
                print("Tidaak Ada Data")

        else:
            print("Pilih menu yang tersedia")
            
2. Hasil Run 

![Screenshot (218)](https://user-images.githubusercontent.com/115867244/204138409-15951ea9-4379-4552-9759-dcafc1888323.png)

![Screenshot (219)](https://user-images.githubusercontent.com/115867244/204138424-ef87deff-66fb-4929-817a-87981e152b43.png)


### Penjelasan Program :
1. Buatlah Dictionary berupa Nama, NIM, Nilai Tugas, Nilai UTS, Nilai UAS
2. Lalu inputlah menu pilihan berupa Lihat, Tambah, Ubah, Hapus, Cari, Keluar
3. Gunakanlah perulangan for, dengan perintah for i in range(len(Nama)):. Fungsi "len" ialah untuk mengembalikan panjang (jumlah anggota) dari suatu objek.
4. Lalu inputlah Nama, NIM, Nilai Tugas, Nilai UTS, Nilai UAS
5. Lalu mencari nilai akhir dengan perhitungan nilai tugas 30%, nilai uts 35% dan uas 35% , dengan perintah float
6. Jika ingin melihat dictionary data ketik "L", jika ingin menambah data ketik "T", jika ingin mengubah data ketik "U", jika ingin menghapus ketik "H", jika ingin mencari data ketik "C" dan jika ingin keluar dari data ketik "K"
7. Lalu cetak dengan perintah print ("Pilih menu yang tersedia")
8. Selesai

### Flowchart Praktikum-5

![flowchart7_page-0001](https://user-images.githubusercontent.com/115867244/204285409-a9908a84-fa15-4d5e-8225-be7bf7afa66e.jpg)


## Sekian, Terima kasih
