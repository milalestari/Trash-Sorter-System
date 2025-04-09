# Trash-Sorter-System

TrashSorter adalah aplikasi konsol berbasis Java yang dirancang untuk membantu pengguna dalam menyortir sampah ke dalam kategori yang benar (Organik, Anorganik, atau B3), serta memberikan edukasi dan pencatatan riwayat penyortiran. Aplikasi ini bertujuan meningkatkan kesadaran lingkungan dengan pendekatan teknologi sederhana dan informatif.

---

## 📌 Fitur Utama

### 👤 Mode Pengguna (User)
- ✅ Pilih jenis sampah dari daftar
- ✅ Smart Sort (input manual)
- ✅ Edukasi tentang jenis dan pengolahan sampah
- ✅ Lihat dan cari riwayat penyortiran
- ✅ Rekomendasi pengolahan berdasarkan kategori

### 🛠️ Mode Admin
- ✅ Lihat seluruh riwayat penyortiran
- ✅ Lihat statistik berdasarkan kategori
- ✅ Cari data riwayat spesifik
- ✅ Reset semua riwayat
- ✅ Ekspor riwayat dan statistik ke file `.txt`

---

## 🧱 Arsitektur Komponen
                +----------------+
                |     Admin      |
                +----------------+
                   /   |   \   \
                  /    |    \   \
     +----------------+  |  +-------------------+
     | InputComponent |  |  | SorterComponent   |
     +----------------+  |  +-------------------+
                         |         |
     +--------------------------+  |
     |    EducationComponent    |  |
     +--------------------------+  |
                                   |
                   +--------------------------+
                   |     HistoryComponent     |
                   +--------------------------+

## 📘 Class Diagram (UML)


## 📎Use Case Diagram


## 📑 Design by Contract (DbC)

## Struktur Projek
TrashSorter/
├── MainApp.java                  # Program utama (entry point)
├── InputComponent.java           # Komponen input sampah
├── SorterComponent.java          # Komponen pemilah sampah
├── HistoryComponent.java         # Komponen pencatatan dan manajemen riwayat
├── EducationComponent.java       # Komponen edukasi dan tips pengelolaan
├── interfaces/
│   ├── WasteInputService.java    # Interface layanan input
│   ├── SortingService.java       # Interface layanan sorting
├── utils/
│   └── ANSI.java                 # Utility untuk pewarnaan output di terminal
├── riwayat_sampah.txt            # File hasil ekspor riwayat
└── README.md                     # Dokumentasi proyek



