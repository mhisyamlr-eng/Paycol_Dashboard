# 💼 Paycol Dashboard

Dashboard aplikasi untuk manajemen Payment Collection (Paycol) dengan multi-level user access.

## 🌟 Features

### 1. **Admin Aplikasi**
- Performansi CR (Collection Rate)
- Automatic grab dari MyBrain
- View Nasional, Regional, Per Segmen, Per Witel
- GAP Detail Navigation

### 2. **Admin Paycol Regional**
- Tunggakan Management
- Detail Pelanggan dengan navigasi
- Update Status Pembayaran
- Update Account Manager

### 3. **Admin Paycol Witel**
- Report KKP (Kartu Kendali Pembayaran)
- Rekap UTIP
- Request Flagging
- Update Status UTIP

### 4. **Management SSS**
- Input Invoice Manual
- Update Invoice
- Status Tracking
- Rekap Invoice

### 5. **Management Non SSS**
- Input Invoice Manual
- Update Invoice
- Status Tracking
- Rekap Invoice

### 6. **Guest**
- Input Adjustment
- Update Adjustment
- Status Tracking
- Rekap Adjustment

## 🚀 Installation

### Prerequisites
- Python 3.8+
- pip

### Local Setup

1. Clone repository:
```bash
git clone https://github.com/username/paycol-dashboard.git
cd paycol-dashboard
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Create data directory dan file Excel:
```bash
mkdir data
```

4. Run aplikasi:
```bash
streamlit run app.py
```

## 📁 Project Structure

```
paycol-dashboard/
│
├── .streamlit/
│   └── config.toml
│
├── data/
│   ├── users.xlsx
│   ├── performansi_cr.xlsx
│   ├── tunggakan.xlsx
│   ├── utip.xlsx
│   ├── invoice_manual.xlsx
│   ├── adjustment.xlsx
│   └── flagging.xlsx
│
├── modules/
│   ├── __init__.py
│   ├── auth.py
│   ├── admin_aplikasi.py
│   ├── admin_paycol_reg.py
│   ├── admin_paycol_witel.py
│   ├── management_sss.py
│   ├── management_non_sss.py
│   └── guest.py
│
├── utils/
│   ├── __init__.py
│   ├── excel_handler.py
│   └── data_processor.py
│
├── app.py
├── requirements.txt
├── .gitignore
└── README.md
```

## 🔐 Default Users

| Username | Password | Role |
|----------|----------|------|
| admin | admin123 | Admin Aplikasi |
| paycol_reg | reg123 | Admin Paycol Reg |
| paycol_witel | witel123 | Admin Paycol Witel |
| mgmt_sss | sss123 | Management SSS |
| mgmt_nonsss | nonsss123 | Management Non SSS |
| guest | guest123 | Guest |

## 🌐 Deploy to Streamlit Cloud

1. Push code ke GitHub repository

2. Go to [share.streamlit.io](https://share.streamlit.io)

3. Sign in dengan GitHub account

4. Click "New app"

5. Fill in:
   - Repository: `username/paycol-dashboard`
   - Branch: `main`
   - Main file path: `app.py`

6. Click "Deploy"

## 📊 Database Structure

### users.xlsx
- username
- password
- role
- regional
- status

### performansi_cr.xlsx
- regional
- witel
- segmen
- total_tagihan
- total_bayar
- cr_rate
- periode

### tunggakan.xlsx
- id_pelanggan
- nama_pelanggan
- segmen
- witel
- jumlah_tunggakan
- status
- am
- last_update

### utip.xlsx
- id_invoice
- nama_pelanggan
- witel
- nilai_invoice
- status
- last_update

### invoice_manual.xlsx
- id_invoice
- id_pelanggan
- nama_pelanggan
- segmen
- periode
- nilai_invoice
- status
- jenis_management
- created_by
- created_date

### adjustment.xlsx
- id_adjustment
- id_pelanggan
- nama_pelanggan
- jenis_adjustment
- nilai_adjustment
- status
- approval_status
- created_by
- created_date

## 🔧 Configuration

Edit `.streamlit/config.toml` untuk kustomisasi:

```toml
[theme]
primaryColor = "#FF4B4B"
backgroundColor = "#FFFFFF"
secondaryBackgroundColor = "#F0F2F6"
textColor = "#262730"
font = "sans serif"

[server]
maxUploadSize = 200
```

## 📝 Usage Tips

1. **Data Import**: Siapkan file Excel dengan struktur yang sesuai
2. **User Management**: Update file `users.xlsx` untuk menambah user baru
3. **Backup**: Backup folder `data/` secara berkala
4. **Security**: Ganti password default setelah deployment

## 🛠️ Development

Untuk menambah fitur baru:

1. Create modul baru di folder `modules/`
2. Import di `app.py`
3. Tambahkan kondisi di `show_dashboard()`
4. Test locally sebelum deploy

## 📞 Support

Untuk pertanyaan atau issue, silakan buat issue di GitHub repository.

## 📄 License

MIT License

## 👥 Contributors

- Your Name - Initial work

---

Made with ❤️ using Streamlit
