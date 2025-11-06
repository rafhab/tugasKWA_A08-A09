# Laporan Proyek: Sistem Deteksi Integritas File dan Aktivitas Mencurigakan

## 1. Informasi Umum Proyek
- **Nama Proyek**: Sistem Monitoring Integritas File
- **Bahasa Pemrograman**: Python
- **Tim Pengembang**: 1 Developer
- **Durasi Pengembangan**: 3-5 hari
- **Tanggal Mulai**: [Tanggal mulai aktual]
- **Tanggal Selesai**: [Tanggal selesai aktual]

## 2. Latar Belakang dan Tujuan
### 2.1 Latar Belakang
Kebutuhan untuk memantau integritas file dan mendeteksi aktivitas mencurigakan pada folder penting dalam sistem.

### 2.2 Tujuan
- Membangun sistem monitoring file otomatis
- Mendeteksi perubahan, penambahan, dan penghapusan file
- Memverifikasi integritas file menggunakan hash
- Melakukan logging komprehensif
- Menyediakan simulasi monitoring

## 3. Ruang Lingkup dan Fitur
### 3.1 Ruang Lingkup
- ✅ Monitoring folder `./secure_files/`
- ✅ Deteksi perubahan file (ubah, hapus, tambah)
- ✅ Verifikasi integritas dengan hash SHA-256
- ✅ Penyimpanan baseline hash di `hash_db.json`
- ✅ Logging ke `security.log`
- ✅ Simulasi alert system
- ✅ Analisis log file


## 4. Spesifikasi Teknis
### 4.1 Teknologi
- **Bahasa**: Python 3.8+
- **Library**: hashlib, json, os, logging, datetime
- **Format Data**: JSON untuk penyimpanan hash
- **Log Format**: Text file dengan timestamp

### 4.2 Struktur File
```
project/
├── file_monitor.py      # Main program
├── hash_db.json         # Database hash
├── security.log         # Log file
└── secure_files/        # Folder yang dimonitor
```

## 5. Rencana Implementasi

### Fase 1: Persiapan dan Desain (Hari 1)
**Task 1.1**: Analisis Kebutuhan
- [x] Identifikasi requirement
- [x] Tentukan struktur data
- [x] Rancang format logging

**Task 1.2**: Setup Environment
- [x] Buat project structure
- [x] Siapkan testing folder
- [x] Buat sample files

### Fase 2: Implementasi Core Functions (Hari 2-3)
**Task 2.1**: Hash Management System
```python
# Pseudocode
def calculate_file_hash(filepath):
    """Calculate SHA-256 hash of file"""
    
def save_baseline_hashes(folder_path, hash_db_file):
    """Save initial hashes to JSON"""
    
def load_baseline_hashes(hash_db_file):
    """Load hashes from JSON"""
```

**Task 2.2**: File Monitoring System
```python
def monitor_folder(folder_path, hash_db_file):
    """Monitor folder for changes"""
    - Compare current vs baseline
    - Detect new files
    - Detect deleted files
    - Detect modified files
```

**Task 2.3**: Logging System
```python
def setup_logging():
    """Configure logging format and file"""
    
def log_event(level, message, filename=None):
    """Log event with timestamp"""
```

### Fase 3: Alert dan Reporting (Hari 3-4)
**Task 3.1**: Alert System
```python
def send_alert(alert_type, filename):
    """Simulate alert sending"""
```

**Task 3.2**: Log Analysis
```python
def analyze_security_log(log_file):
    """Analyze log file and generate report"""
```

### Fase 4: Testing dan Debugging (Hari 4-5)
**Task 4.1**: Unit Testing
- [ ] Test hash calculation
- [ ] Test file detection
- [ ] Test logging functionality

**Task 4.2**: Integration Testing
- [ ] End-to-end monitoring test
- [ ] Log analysis test
- [ ] Error handling test

## 6. Timeline dan Milestone
```
Hari 1: │─── Persiapan & Desain ───│
Hari 2: │─── Core Hash System ───│
Hari 3: │─── Monitoring & Logging ───│
Hari 4: │─── Alert & Reporting ───│
Hari 5: │─── Testing & Finalisasi ───│
```

**Milestone**:
- M1: Hash system working
- M2: File monitoring operational
- M3: Logging system complete
- M4: Alert system functional
- M5: Project complete



## 7. Dokumentasi Penggunaan

### 7.1 Instalasi dan Setup
```bash
# 1. Clone/simpan file file_monitor.py
# 2. Buat folder secure_files (akan dibuat otomatis)
# 3. Jalankan program
python file_monitor.py
```

### 7.2 Workflow Penggunaan
1. **Inisialisasi Baseline**: Pilih opsi 1 untuk membuat baseline hash pertama kali
2. **Monitoring Rutin**: Pilih opsi 2 untuk menjalankan pemeriksaan
3. **Analisis Log**: Pilih opsi 3 untuk melihat laporan keamanan
4. **Testing**: Jalankan `python test_monitor.py` untuk testing komprehensif

### 7.3 Contoh Output
```
[2025-10-30 13:25:11] INFO: File "config.json" verified OK.
[2025-10-30 13:26:02] WARNING: File "data.txt" integrity failed!
[2025-10-30 13:27:15] ALERT: Unknown file "hacked.js" detected.

SECURITY LOG ANALYSIS REPORT
==================================================
Files verified safe: 15
Files corrupted/suspicious: 3  
Last anomaly detected: [2025-10-30 13:27:15]
==================================================
```


