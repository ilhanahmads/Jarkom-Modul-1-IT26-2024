# Jarkom-Modul-1-IT26-2024
Laporan Resmi pengerjaan soal shift modul 1 Praktikum Jaringan Komputer 2024 Kelompok IT26

## Anggota Kelompok
1. Ilhan Ahmad Syafa (5027221040)
2. george David Neborre (5027221043)

# 1. ATM or ATP or FTP
<a href="https://ibb.co/5WktcNC"><img src="https://i.ibb.co/WW0qKb7/Screenshot-2024-03-30-234253.png" alt="Screenshot-2024-03-30-234253" border="0"></a> \
Pada file `ftp.pcap` berisi serangkaian paket yang menunjukkan aktivitas seseorang tak dikenal yang hendak melakukan login dengan cara _brute force_. Problem yang diberikan adalah apa password yang didapatkan oleh hacker sehingga berhasil login ke server tersebut?

<a href="https://ibb.co/0tmBHdd"><img src="https://i.ibb.co/FVmsRjj/Screenshot-2024-03-31-000349.png" alt="Screenshot-2024-03-31-000349" border="0"></a> \
Dari cuplikan screenshot beberapa paket di atas ditemukan bahwa setelah beberapa kali hacker melakukan _brute force_, akhirnya hacker berhasil melakukan login. Kami menganalisis bahwa sebagian besar proses tercapture pada paket berprotokol FTP. Oleh karena itu, kami memfilter capture dengan menggunakan command `ftp`. Setelah menganalisis paket dari awal sampai akhir, ditemukan bahwa hacker berhasil login dengan menggunakan password `m4y_th3_Kn!fe_ch1p_&_sh4tter`. Jawab pertanyaan dengan password tersebut. Setelah itu kami mendapatkan flag berikut untuk disubmit di platform ctfd:

Flag: `JARKOM2024{Brut3f0rce_FtP_uhwlPzpfyAFskr9}`

# 2. How Many Packets?
<a href="https://ibb.co/19KwWqt"><img src="https://i.ibb.co/rZM1r6R/Screenshot-2024-03-30-234408.png" alt="Screenshot-2024-03-30-234408" border="0"></a> \
Masih pada file `ftp.pcap` yang berisi serangkaian paket yang menunjukkan aktivitas seseorang tak dikenal yang hendak melakukan login dengan cara _brute force_. Namun, kali ini problem yang diberikan adalah berapa kali hacker telah mencoba melakukan _brute force_ sebelum akhirnya menemukan password yang benar pada soal sebelumnya. 

<a href="https://ibb.co/hCkvDFJ"><img src="https://i.ibb.co/b7xnz5M/Screenshot-2024-03-30-234456.png" alt="Screenshot-2024-03-30-234456" border="0"></a> \
Pada soal ini kami memanfaatkan _packet analyzer_ bawaan dari Wireshark itu sendiri yaitu `tshark` dengan menjalankan command `tshark -q -r ftp.pcap -z io,stat,0, "COUNT(frame)frame matches \"Login incorrect"\"` pada directory yang sesuai dengan tempat file `ftp.pcap` berada. Output dari command tersebut adalah mencari frame atau potongan kalimat dalam file bernama `ftp.pcap` yang mengandung **Login incorrect** di dalamnya kemudian akan dihitung hasilnya. Ternyata didapatkan hasil sebanyak **934** kali _brute force_ gagal yang dilakukan oleh hacker. Setelah itu kami mendapatkan flag berikut untuk disubmit di platform ctfd:

Flag: `JARKOM2024{c0unT_uR_P4cket5_9h8kv7xjl6VtCrY}`

# 3. Trace Him
<a href="https://ibb.co/x69mSjY"><img src="https://i.ibb.co/GRYsv29/Screenshot-2024-03-30-234634.png" alt="Screenshot-2024-03-30-234634" border="0"></a> \
Masih pada file `ftp.pcap` yang berisi serangkaian paket yang menunjukkan aktivitas seseorang tak dikenal yang hendak melakukan login dengan cara _brute force_. Pada kali ini, problemnya adalah kami diminta untuk mengetahui IP dari hacker yang sedang melancarkan serangan. 

<a href="https://ibb.co/7rTSwjC"><img src="https://i.ibb.co/vLrc7Vq/Screenshot-2024-03-31-000349.png" alt="Screenshot-2024-03-31-000349" border="0"></a> \
Dari cuplikan screenshot beberapa paket di atas ditemukan bahwa setelah beberapa kali hacker melakukan _brute force_, akhirnya hacker berhasil melakukan login. Kami menganalisis bahwa sebagian besar proses tercapture pada paket berprotokol FTP. Oleh karena itu, kami memfilter capture dengan menggunakan command `ftp`. Setelah menganalisis paket dari awal sampai akhir, ditemukan bahwa hacker berhasil login dengan menggunakan password `m4y_th3_Kn!fe_ch1p_&_sh4tter`. Dari capture tersebut dapat diketahui _source_ dan _destination_ pada sebuah paket yang mana _source_ merupakan alamat IP seseorang yang melakukan aktivitas (dalam konteks soal ini adalah _brute force_) dan _destination_ merupakan target serangannya sehingga dapat disimpulkan bahwa alamat IP dari attacker adalah _source_ yang tertera pada tampilan interface Wireshark. Jawab pertanyaan dengan alamat IP tersebut. Setelah itu kami mendapatkan flag berikut untuk disubmit di platform ctfd:

Flag: `JARKOM2024{Wh3re'5_thE_S4uce_x6fkX7xfyRVsCAB}`

# 4. Creds
<a href="https://ibb.co/1s6yQDX"><img src="https://i.ibb.co/YDZnQzd/Screenshot-2024-03-31-000750.png" alt="Screenshot-2024-03-31-000750" border="0"></a> \
Beralih ke file `evidence.pcap`. File pcap tersebut berisi serangkaian percobaan masuk oleh attacker serta aktivitas transfer data yang dilakukan oleh attacker setelah berhasil login ke dalam server. Dengan melakukan capture filter `tcp.stream eq 2` di Wireshark, kami mendapatkan informasi terkait kredensial yang digunakan oleh attacker untuk login ke dalam server seperti pada screenshot di atas yaitu dengan `USER: h3ngk3rTzy` dan `PASS: S!l3ncE` yang dibuktikan dengan adanya response "Login successful." dari server.

<a href="https://imgbb.com/"><img src="https://i.ibb.co/wg0j3qF/Screenshot-2024-03-30-234946.png" alt="Screenshot-2024-03-30-234946" border="0"></a> \ 
Setelah berhasil mendapatkan kredensial attacker, kami menjawab pertanyaan soal dan mendapatkan flag berikut untuk disubmit di platform ctfd:

Flag: `JARKOM2024{s3curE_uR_FtP_xTrCv7nygRJsCrB}`

# 5. Malwleowleo
<a href="https://ibb.co/Y70FRS3"><img src="https://i.ibb.co/yn4cfCX/Screenshot-2024-04-02-224939.png" alt="Screenshot-2024-04-02-224939" border="0"></a>
<a href="https://ibb.co/Y2vB7bY"><img src="https://i.ibb.co/sjL9vtk/Screenshot-2024-03-31-000903.png" alt="Screenshot-2024-03-31-000903" border="0"></a> \
Masih pada file `evidence.pcap` yang berisi serangkaian percobaan masuk oleh attacker serta aktivitas transfer data yang dilakukan oleh attacker setelah berhasil login ke dalam server. Kami menganalisis aktivitas attacker melalui kolom **info**. Setelah mendapati terdapat aktivitas mencurigakan dari attacker yang mana tertera melakukan **STOR** suatu file, kami mencoba **follow stream** paket tersebut dan kami menemukan attacker mengirim sebuah malware berupa file bernama `m4L1c10us_W4re.c`

<a href="https://ibb.co/pZbTXp8"><img src="https://i.ibb.co/92c0YjL/Screenshot-2024-03-30-235030.png" alt="Screenshot-2024-03-30-235030" border="0"></a> \
Setelah berhasil menemukan file malware yang dikirim oleh attacker, kami menjawab pertanyaan soal dan mendapatkan flag berikut untuk disubmit di platform ctfd:

Flag: `JARKOM2024{beC4refUl_0f_m4lwAr3_cT8RYzpHizdHRrB}`

# 6. Whoami
<a href="https://ibb.co/dpDD1gR"><img src="https://i.ibb.co/gWJJHVx/Screenshot-2024-04-02-230221.png" alt="Screenshot-2024-04-02-230221" border="0"></a> \
Masih pada file `evidence.pcap` yang berisi serangkaian percobaan masuk oleh attacker serta aktivitas transfer data yang dilakukan oleh attacker setelah berhasil login ke dalam server. Namun, problem pada soal ini adalah kami disuruh mencari identitas nama dari attacker yang mengirimkan file malware. Kami mencoba mengekspor file malware yang telah disisipkan oleh attacker untuk dianalisis.

<a href="https://ibb.co/dcRWNmp"><img src="https://i.ibb.co/xsNCnFg/Screenshot-2024-04-02-230332.png" alt="Screenshot-2024-04-02-230332" border="0"></a> \
Setelah kami buka pada Visual Studio Code, kami menemukan serangkaian code mencurigakan yang sepertinya sudah mengalami proses encode. 

<a href="https://ibb.co/wCSWc3m"><img src="https://i.ibb.co/WFkyVqJ/Screenshot-2024-04-02-230344.png" alt="Screenshot-2024-04-02-230344" border="0"></a>
<a href="https://ibb.co/HV7D6PN"><img src="https://i.ibb.co/CzB5g9J/Screenshot-2024-03-30-235520.png" alt="Screenshot-2024-03-30-235520" border="0"></a> \
Dengan menggunakan bantuan dari decoder online, kami mencoba mendecode code mencurigakan tersebut dengan format base64. Benar saja, setelah berhasil kami decode, kami mengetahui bahwa attacker ini bernama **Paul Atreides**. Setelah berhasil menemukan nama attacker, kami menjawab pertanyaan soal dan mendapatkan flag berikut untuk disubmit di platform ctfd:

Flag: `JARKOM2024{Duk3_0f_4rak!s_LISAN AL GHAIB!_9JrCv79yl1kH88B}`
