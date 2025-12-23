# Panduan Menampilkan Gambar di Website Pengguna

## 🔧 Masalah: Gambar Tidak Muncul di Website Pengguna

Gambar yang diupload admin tidak muncul di halaman ujian siswa karena kode belum menangani display gambar.

## ✅ Solusi: Update Kode Ujian

### 1. **Update `ujian.js` - Fungsi showQuestion**

```javascript
// Render question with image support
const imageHtml = question.image_url
    ? `<div class="question-image"><img src="${question.image_url}" alt="Soal ${index + 1}" onerror="this.style.display='none'"></div>`
    : '';

questionCard.innerHTML = `
    <div class="question-number">Soal ${index + 1}</div>
    <div class="question-text">${question.question_text}</div>
    ${imageHtml}  // ← GAMBAR DITAMBAHKAN DI SINI
    <div class="options">
        // ... options HTML
    </div>
`;
```

### 2. **Update `ujian.html` - CSS Styling**

```css
.question-image {
    margin: 1.5rem 0;
    text-align: center;
}

.question-image img {
    max-width: 100%;
    height: auto;
    max-height: 300px;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    border: 1px solid #e5e7eb;
}
```

### 3. **Setup Supabase Storage**

Pastikan bucket `images` sudah dibuat dan public:

```sql
-- Buat bucket images
INSERT INTO storage.buckets (id, name, public)
VALUES ('images', 'images', true);

-- Set RLS policies
CREATE POLICY "Images are publicly accessible" ON storage.objects
    FOR SELECT USING (bucket_id = 'images');
```

## 🎯 Cara Kerja:

1. **Admin Upload Gambar** → Disimpan di Supabase Storage bucket `images`
2. **URL Gambar** → Disimpan di kolom `image_url` tabel questions
3. **Siswa Mengerjakan Ujian** → Kode di `ujian.js` menampilkan gambar jika ada
4. **Gambar Ditampilkan** → Dengan styling yang responsive

## 📋 Checklist Implementasi:

- ✅ **Bucket `images` dibuat** di Supabase Storage
- ✅ **Public access enabled** untuk bucket
- ✅ **Kode `ujian.js` diperbarui** untuk menampilkan gambar
- ✅ **CSS styling ditambahkan** di `ujian.html`
- ✅ **Error handling** dengan `onerror="this.style.display='none'"`

## 🔍 Troubleshooting:

### **Gambar Tidak Muncul:**

1. **Cek Console Browser:**
   ```javascript
   // Jalankan di browser console saat ujian
   console.log(question.image_url); // Cek apakah URL ada
   ```

2. **Cek Supabase Storage:**
   - Buka Supabase Dashboard → Storage
   - Pastikan bucket `images` ada dan public
   - Cek apakah file gambar ada di bucket

3. **Cek Database:**
   ```sql
   -- Cek apakah soal punya image_url
   SELECT id, question_text, image_url
   FROM questions
   WHERE image_url IS NOT NULL;
   ```

### **Error Loading Gambar:**

- **Network Error**: Bucket tidak public
- **404 Error**: File tidak ada di storage
- **CORS Error**: Policy RLS salah

## 🚀 Testing:

1. **Upload gambar** di admin panel
2. **Simpan soal** dengan gambar
3. **Buka ujian** sebagai siswa
4. **Cek apakah gambar muncul** di soal

## 📱 Responsive Design:

Gambar akan otomatis responsive:
- **Desktop**: Max width 100%, height auto
- **Mobile**: Scale down sesuai layar
- **Max height**: 300px untuk mencegah gambar terlalu besar

---

**Gambar sekarang akan muncul di website pengguna saat mengerjakan ujian!** 📸🖼️