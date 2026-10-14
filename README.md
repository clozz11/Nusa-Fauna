# Nusa Fauna

Nusa Fauna adalah proyek deteksi hewan langka menggunakan model YOLO. Aplikasi web mengirim gambar ke backend Python dan menampilkan nama hewan, status kelangkaan, tingkat keyakinan, serta kotak deteksi.

## Struktur proyek

- `Website Projek AI Kelompok 8 LA20/ProjectAIFInpro/Backend/` — API FastAPI dan bobot model yang digunakan aplikasi.
- `Website Projek AI Kelompok 8 LA20/ProjectAIFInpro/Front end/homepage.html` — halaman web.
- `Hasil Evaluasi Model AI.csv`, gambar evaluasi, poster, dan proposal — hasil serta dokumen proyek.
- `Model AI.pt` — salinan bobot model utama.

## Menjalankan aplikasi di Windows

Pastikan Python sudah terpasang. Dari folder utama proyek, buat dan aktifkan virtual environment, lalu pasang dependensi:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

Jalankan backend dari foldernya agar file bobot model ditemukan:

```powershell
Set-Location ".\Website Projek AI Kelompok 8 LA20\ProjectAIFInpro\Backend"
python -m uvicorn main:app --reload --port 8000
```

Kemudian buka `Website Projek AI Kelompok 8 LA20/ProjectAIFInpro/Front end/homepage.html` di browser. Halaman web menggunakan API pada `http://localhost:8000`; backend harus tetap berjalan saat melakukan deteksi.

## Endpoint API

- `POST /predict` — unggah gambar dengan field multipart bernama `file`.
- `GET /docs` — dokumentasi interaktif FastAPI saat backend berjalan.
