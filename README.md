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
Masih pada file yang `ftp.pcap` berisi serangkaian paket yang menunjukkan aktivitas seseorang tak dikenal yang hendak melakukan login dengan cara _brute force_.

<a href="https://ibb.co/hCkvDFJ"><img src="https://i.ibb.co/b7xnz5M/Screenshot-2024-03-30-234456.png" alt="Screenshot-2024-03-30-234456" border="0"></a>
