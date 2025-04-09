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
        +----------------+
        |    MainApp     |
        +----------------+
        | +main()        |
        | +runUserMenu() |
        | +runAdminMenu()|
        +----------------+
               |
               | uses
               ↓
        +---------------------+
        |  WasteInputService  |<------------------+
        +---------------------+                   |
        | +getWasteInput()    |                   |
        | +getCustomInput()   |                   |
        +---------------------+                   |
                ▲                                 |
                | implements                      |
        +---------------------+                  |
        |   InputComponent    |------------------+
        +---------------------+
        
        +---------------------+
        |   SortingService    |<--------------------+
        +---------------------+                     |
        | +sort(waste: String)|                     |
        +---------------------+                     |
                ▲                                   |
                | implements                        |
        +---------------------+                    |
        |   SorterComponent   |--------------------+
        | -history: HistoryComponent               |
        +---------------------+
        
        +------------------------+
        |  HistoryComponent      |
        +------------------------+
        | +showHistory()         |
        | +searchHistory()       |
        | +clearHistory()        |
        | +showStats()           |
        | +getHistory()          |
        +------------------------+
        
        +------------------------+
        |  EducationComponent    |
        +------------------------+
        | +showEducation()       |
        | +showTipsByCategory()  |
        +------------------------+

## 📎Use Case Diagram
                       +--------+                      +--------+
                       |  User  |                      | Admin  |
                       +--------+                      +--------+
                            |                               |
              +-------------+-------------+     +-----------+-----------------+
              |             |             |     |     |     |       |         |
        +------------+ +-------------+ +--------------+ +-------------+ +--------------+
        | Pilih      | | Smart Sort | | Edukasi       | | Lihat       | | Ekspor       |
        | Jenis      | | (Manual)   | | Sampah        | | Statistik   | | Riwayat      |
        | Sampah     | +-------------+ +--------------+ +-------------+ +--------------+
        +------------+                      |                            |
               |                            |                            |
               +-------------> Lihat Riwayat / Cari Riwayat <------------+


## 📑 Design by Contract (DbC)
  **Komponen**		
  SorterComponent		
  InputComponent			
  HistoryComponent
  EducationComponent
  
  **Precondition**
  Input tidak kosong
  User memilih input dari daftar/manual
  Riwayat tersedia (jika ingin ditampilkan)
  Kategori valid dimasukkan oleh user
  
  **Postcondition**	
  Output berupa kategori valid (Organik/Anorganik/B3)
  Mengembalikan string input valid
  Statistik ditampilkan atau diekspor	
  Tips edukatif muncul sesuai kategori
  
  **Invariant**
  History selalu dicatat dan konsisten
  Tidak boleh return null atau kosong
  Data tidak boleh berubah tanpa perintah
  Database edukasi tetap dan tidak duplikat


## 📂 Struktur Projek
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

## 💡 Prinsip yang Digunakan
      1. Modular Design
         Setiap komponen memiliki tanggung jawab terpisah dan dapat dikembangkan secara independen.
      2. Object-Oriented Programming (OOP)
         Penggunaan class, interface, dan pewarisan untuk fleksibilitas dan maintainability.
      3. Design by Contract
         Setiap method dijalankan dengan precondition dan menghasilkan postcondition yang terjamin.
      4. UML Diagrams
         Mendokumentasikan arsitektur dengan Class Diagram, Use Case Diagram, dan Component Diagram.

   



