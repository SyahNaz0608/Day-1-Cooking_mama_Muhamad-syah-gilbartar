# From AI to GitHub: Rangkuman Materi

> **Building with AI, Managing Change with GitHub**
> Pemateri: Nugi Farhan, Senior Product Designer

Rangkuman dan poin-poin penting dari materi workshop "From AI to GitHub". Materi ini terdiri dari dua bagian: membuat dan mengembangkan sesuatu dengan AI (*prompt engineering*), lalu mengelola perubahan dan kolaborasi dengan Git dan GitHub. Praktik akhirnya adalah membuat aplikasi sederhana bernama **Student Task Planner**.

## Identitas

- Nama: Muhamad Syah Gilbartar
- Kelompok: 21 - Cooking Mama
- Deskripsi repo: memuat tentang rangkuman workshop git vs github
- Tujuan repo: mempelajari git dan github merupakan satu kesatuan yang saling melengkapi satu sama lain

## Tujuan Belajar

Setelah mengikuti materi ini, peserta diharapkan mampu:

- Menjelaskan bagaimana prompt AI yang lebih spesifik menghasilkan hasil yang lebih baik.
- Mengidentifikasi repository, commit, branch, dan pull request.
- Membedakan Git dan GitHub.
- Melakukan version control.

## 1. Prompt Engineering

### Apa itu prompt?

**Prompt** adalah instruksi atau masukan yang diberikan kepada model AI untuk mendapatkan hasil tertentu. Bentuknya bisa berupa pertanyaan sederhana, kata kunci, instruksi yang rumit, atau potongan kode.

**Prompt engineering** adalah cara merancang instruksi agar AI memberikan jawaban yang tepat, relevan, dan layak digunakan.

### Konteks adalah kunci

| Tanpa konteks | Dengan konteks |
|---|---|
| `Create student task planner` | Prompt yang menjelaskan peran, tujuan, kebutuhan, batasan, dan format keluaran |

Prompt yang pendek membuat AI menebak sendiri kebutuhan Anda. Prompt yang berkonteks mengarahkan hasilnya.

### Struktur prompt yang baik

Struktur yang dipakai di materi terdiri dari empat komponen: **Role, Task, Context, dan Format**.

| Komponen | Fungsi | Contoh dari materi |
|---|---|---|
| **Role** | Menentukan peran AI dan situasinya | `You are helping me build a beginner-friendly student task planner as a simple web application.` |
| **Task** | Tujuan yang ingin dicapai | Bagian `## Goal`: membuat task planner untuk mahasiswa tahun pertama |
| **Context** | Kebutuhan dan batasan | Bagian `## Requirements` dan `## Constraints` |
| **Format** | Teknologi dan bentuk keluaran | HTML, CSS, vanilla JavaScript, dan bagian `## Output` |

Contoh prompt lengkap dari materi:

```text
You are helping me build a beginner-friendly student task planner as a simple
web application.

## Goal
Create a task planner that helps first-year university students keep track of
assignments and deadlines.

## Requirements
- Display a list of sample assignments.
- Each assignment must show its title, due date, and completion status.
- Allow users to mark assignments as completed.
- Include a filter for all, pending, and completed assignments.
- Make the interface clean, readable, and responsive.

## Constraints
- Use HTML, CSS, and vanilla JavaScript.
- Keep the implementation simple enough for a beginner to understand.
- Avoid unnecessary libraries and external dependencies.
- Keep the code organized and explain the purpose of each file.

## Output
Provide the complete code for each file, explain how to run the application, and
describe how to test the main interactions.

Do not claim that the application works until you have verified its behavior.
```

Baris terakhir penting: AI diminta memverifikasi perilaku aplikasinya sebelum mengklaim bahwa aplikasi itu berfungsi.

### Taktik menulis prompt

| Taktik | Contoh prompt |
|---|---|
| Gunakan kata kerja aksi untuk menentukan tindakan | "Write a bulleted list that summarizes the key findings of the attached research paper" |
| Tentukan panjang dan format keluaran | "Compose a 500-word essay discussing the impact of climate change on coastal communities" |
| Sebutkan target audiens | "Write a product description for a new line of organic skincare products, targeting young adults concerned with sustainability" |
| Sertakan fakta dan data yang relevan | "Given that global temperatures have risen by 1 degree Celsius since the pre-industrial era, discuss the potential consequences for sea level rise" |
| Rujuk sumber atau dokumen tertentu | "Based on the attached financial report, analyze the company's profitability over the past five years" |
| Definisikan istilah dan konsep kunci | "Explain the concept of quantum computing in simple terms, suitable for a non-technical audience" |

### Manfaat prompt engineering

- Meningkatkan performa model AI.
- Mengurangi bias dan respons yang menyinggung.
- Meningkatkan kontrol dan keterprediksian hasil.
- Memberikan pengalaman pengguna yang lebih baik.

## 2. Git dan GitHub

### Git vs GitHub

| | **Git** | **GitHub** |
|---|---|---|
| Jenis | Sistem version control terdistribusi (DVCS) | Platform berbasis web |
| Fungsi | Melacak dan mengelola perubahan kode secara lokal | Menyimpan repository Git secara online dan mendukung kolaborasi |
| Cara kerja | Mencatat siapa, kapan, dan apa yang berubah pada file | Tempat berbagi, meninjau, dan menggabungkan perubahan |

Git dibuat oleh Linus Torvalds pada tahun 2005. Alternatif GitHub yang ditampilkan di materi adalah Bitbucket dan GitLab.

### Tiga area Git

```text
 Working Directory ──── git add ────▶ Staging Area ──── git commit ────▶ Repository (.git)
        ◀─────────────────────── checkout the project ──────────────────────
```

| Area | Penjelasan |
|---|---|
| **Working directory** | Salinan satu versi proyek yang sedang dikerjakan. File-filenya diambil dari database Git lalu ditempatkan di komputer agar bisa dipakai atau dimodifikasi. |
| **Staging area (index)** | Menyimpan informasi tentang perubahan apa saja yang akan masuk ke commit berikutnya. Dalam istilah teknis Git, staging area disebut *index*. |
| **Git directory (`.git`)** | Tempat Git menyimpan metadata dan object database proyek. Ini komponen terpenting Git. Bagian inilah yang disalin saat `clone`. |

## 3. Perintah Git Penting

### Perintah lokal

| Perintah | Fungsi |
|---|---|
| `git init` | Memulai repository baru |
| `git add .` | Memindahkan file ke staging area |
| `git commit -m "pesan"` | Menyimpan perubahan ke repository |

### Perintah ke GitHub

| Perintah | Fungsi |
|---|---|
| `git remote add <nama> <url>` | Menghubungkan repository lokal ke remote |
| `git push origin main` | Mengirim branch saat ini ke remote |
| `git pull origin main` | Mengambil perubahan dari remote lalu menggabungkannya ke branch saat ini |
| `git clone "<url>"` | Menyalin repository dari GitHub |

### Variasi `git add`

| Perintah | Hasil |
|---|---|
| `git add --all` / `git add -A` | Berperilaku sama, memasukkan semua perubahan di repository ke staging area |
| `git add .` | Memasukkan semua file di direktori saat ini dan subdirektorinya ke staging area |
| `git add *` | Memasukkan file yang diubah atau baru, tapi tidak yang dihapus |

### Dua cara menambahkan repository

**Cara 1: mulai dari lokal**

```bash
git init
```

**Cara 2: mulai dari GitHub**

1. Buka GitHub.
2. Buat repository baru.
3. Buka tombol dropdown **Code**.
4. Salin link repository.
5. Jalankan di terminal:

```bash
git clone "url"
```

## 4. Persiapan Lingkungan

### Instal Git dan atur identitas

```bash
git --version
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
git config --global --list
```

Output `git --version` berbentuk `git version 2.xx.xx`.

### Pasang VS Code

1. Instal VS Code.
2. Buka VS Code lalu tekan `Cmd+Shift+P` (macOS) atau `Ctrl+Shift+P`.
3. Cari **Shell Command: Install 'code' command in PATH**.
4. Cek di terminal dengan `code --version`.

### Buat SSH key untuk GitHub

```bash
ssh-keygen -t ed25519 -C "email@domain.com"
```

- Saat ditanya lokasi file, tekan **Enter** untuk memakai default (`~/.ssh/id_ed25519`).
- Saat ditanya passphrase, isi passphrase yang aman (atau tekan Enter dua kali untuk tanpa passphrase).

**Tentang Ed25519:** Ed berarti EdDSA (Edwards-curve Digital Signature Algorithm), dan 25519 merujuk pada kurva eliptik Curve25519 buatan Daniel J. Bernstein (2011). Ed25519 dirancang untuk keamanan dan performa tinggi, serta tahan terhadap serangan implementasi kriptografi yang umum.

### Jalankan ssh-agent

```bash
eval "$(ssh-agent -s)"
touch ~/.ssh/config
```

Tambahkan konfigurasi berikut ke `~/.ssh/config` (materi memakai macOS):

```text
Host github.com
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_ed25519
```

Lalu tambahkan kunci ke agent:

```bash
# macOS
ssh-add --apple-use-keychain ~/.ssh/id_ed25519

# Linux
ssh-add ~/.ssh/id_ed25519
```

### Daftarkan kunci ke GitHub

1. Salin kunci publik:
   ```bash
   # macOS
   pbcopy < ~/.ssh/id_ed25519.pub

   # Linux
   cat ~/.ssh/id_ed25519.pub
   ```
2. Buka pengaturan **SSH and GPG keys** di GitHub.
3. Klik **New SSH key**.
4. Isi **Title** dengan label yang jelas (misalnya "MacBook").
5. Biarkan **Key type** sebagai *Authentication Key*.
6. Tempel kunci ke kolom **Key**.
7. Klik **Add SSH key**.
8. Verifikasi koneksi:
   ```bash
   ssh -T git@github.com
   ```
   Pesan yang diharapkan: `Hi username! You've successfully authenticated, but GitHub does not provide shell access.`

### Cek setup

```bash
git --version                      # 1. Git
git config --global user.name      # 2. Identitas Git
git config --global user.email
code --version                     # 3. VS Code
ssh -T git@github.com              # 4. Koneksi GitHub
```

## 5. Praktik: Student Task Planner

Alur praktik dalam materi:

1. Pasang platform AI (Claude, Antigravity, atau ChatGPT).
2. Tulis prompt untuk membuat web atau aplikasinya.
3. Tambahkan ke Git dengan `git init`.
4. Commit dan push ke GitHub.
5. Lakukan perubahan.
6. Commit dan push lagi.

Contoh alur perintahnya:

```bash
git init
git add .
git commit -m "Initial commit: student task planner"
git remote add origin git@github.com:<username>/<repository>.git
git push origin main

# setelah mengubah file
git add .
git commit -m "Describe the change"
git push origin main
```

## Poin-poin Penting

1. Prompt yang spesifik dan berkonteks menghasilkan keluaran yang lebih baik.
2. Struktur **Role, Task, Context, Format** membantu menyusun prompt.
3. Minta AI memverifikasi hasilnya, dan jangan langsung memercayainya.
4. **Git** adalah alat lokal untuk melacak perubahan. **GitHub** adalah layanan online untuk menyimpan dan berkolaborasi.
5. Alurnya working directory, staging area, lalu repository, dengan `add` dan `commit` sebagai langkah perpindahan.
6. `push` mengirim ke GitHub, `pull` mengambil perubahan dari GitHub.
7. Atur identitas Git (`user.name` dan `user.email`) sebelum commit pertama.
8. SSH key membuat autentikasi ke GitHub lebih aman. **Jangan pernah membagikan kunci privat** (file tanpa akhiran `.pub`).
9. Commit dan push secara berkala. Seperti pesan humor di slide: *"In case of fire: git commit, git push, leave building."*
