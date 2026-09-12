# mini_project
Sistem Program Perhitungan poin Pembalap Formula 1 adalah sistem program sederhana yang berfungsi membantu user untuk menghitung poin pembalap formula 1 sesuai dengan poin yang didapatkan ketika pembalap tersebut finish.

    flowchart yang saya buat :
<img width="762" height="742" alt="Untitled Diagram" src="https://github.com/user-attachments/assets/70ba0af5-98ea-4406-a2eb-13ffa80cf286" />












    daftar_pembalap = [
    ("George Russell", "Mercedes"),
    ("Max Verstappen", "Red Bull Racing"),
    ("Lewis Hamilton", "Ferrari"),
    ("Lando Norris", "McLaren"),
    ("Oscar Piastri", "Mclaren"),
    ("Isack Hadjar", "Red Bull Racing"),
    ("Pierre Gasly", "Alphine"),
    ("Liam Lawson", "Racing Bulls"),
    ("Charles Leclerc", "Ferrari"),
    ("Kimi Antonelli", "Mercedes")] 
    data_balapan = []
    
     
Pertama kita bikin list daftar pembalap dan data pembalap



    while lanjut == True:
    print ("1. Tambah Hasil Balapan")
    print ("2. Tampilkan Klasemen Balapan")
    print ("3. Keluar")
    pilihan = input ("Masukan Pilihan")
    if pilihan =="1":
        print ("Tambah Hasil Balapan")
        print ("Pilih Pembalap")
        nomor = 1
        for pembalap in daftar_pembalap:
            nomor = nomor + 1
        nomor_valid = False
        while nomor_valid == False:
            input_nomor = input("Masukkan nomor pembalap")
            nomor_pilih = int(input_nomor)
            if nomor_pilih >= 1:
                    nomor_valid = True
            else:
                    print("Nomor Pembalap Tidak ada")
        nama_pembalap = daftar_pembalap[nomor_pilih - 1][0]
        tim_pembalap = daftar_pembalap[nomor_pilih - 1][1]
        posisi_valid = False
        while posisi_valid == False:
            input_posisi = input("Masukkan pole position: ")
            posisi = int(input_posisi)
            if posisi >= 1 and posisi <= 10:
                    posisi_valid = True
        if posisi == 1:
            poin = 25
        elif posisi == 2:
            poin = 18
        elif posisi == 3:
            poin = 15
        elif posisi == 4:
            poin = 12
        elif posisi == 5:
            poin = 10
        elif posisi == 6:
            poin = 8
        elif posisi == 7:
            poin = 6
        elif posisi == 8:
            poin = 4
        elif posisi == 9:
            poin = 2
        elif posisi == 10:
            poin = 1
        else:
            poin = 0
        data_baru = (nama_pembalap, tim_pembalap, posisi, poin)
        data_balapan.append(data_baru)
        print("Data berhasil ditambahkan!")
        print("Pembalap:", nama_pembalap)
        print("Tim:", tim_pembalap)
        print("Posisi:", posisi)
        print("Poin:", poin)

selanjutnya membuat loop agar menu utama terus muncul berulang-ulang sampai user memilih opsi untuk keluar, di menu user dapat memilih opsi 1 (tambah hasil balapan), 2 (tampilkam klasemen balapan), dan (keluar). Jika user memilih pilihan 1 (tambah hasil balapan), maka user akan disuruh memilih pembalap yang sudah ada di list dan memasukan nomor finish pembalap. Berdasarkan sistem poin F1, poin hanya diberikan ke 10 pembalap yang finish di 10 kebawah. Jika pengguna memasukkan angka antara 1 sampai 10, maka posisi_valid menjadi True dan perulangan berhenti. Setelah itu data disimpan di tuple

          output yang dihasilkan :
   <img width="399" height="180" alt="image" src="https://github.com/user-attachments/assets/05c55a48-ed34-4344-b9aa-8b9a9481b209" />


    elif pilihan =="2":
        print("Seluru Data Hasil Klasemen")
    else:
        nomor = 1
        for data in data_balapan:
            print(str(nomor) + ". " + data[0] + " - " + data[1] + " | Posisi: " + str(data[2]) + " | Poin: " + str(data[3]))
            nomor = nomor + 1
        print("Klasemen Total Poin")
        for pembalap in daftar_pembalap:
            total_poin = 0
            for data in data_balapan:
                if data[0] == pembalap[0]:
                    total_poin = total_poin + data[3]
            print(pembalap[0] + " (" + pembalap[1] + ") : " + str(total_poin) + " poin")

jika user memilih pilihan 2 (tampilkan klasemen pembalap) maka user akan memperoleh seluruh data pembalap yang sudah ditambahkan ketika memilih opsi yang 1 (tambah hasil balapan). Program akan memeriksa kembali data pembalap yang sudah terdaftar di awal dan menampilkan total poin pembalap yang sudah terdaftar.

              
              output yang dihasilkan :
  <img width="547" height="182" alt="image" src="https://github.com/user-attachments/assets/ff02558c-a366-4f8b-b926-26eb3f9a492b" />


    if pilihan == "3":
        print("Keluar")

   jika user ingin keluar dari sistem program, user hanya tinggal mengetik 3(keluar)



