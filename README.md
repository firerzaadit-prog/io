# 🎓 EduLearn TKA - Student Portal

Platform pembelajaran interaktif untuk siswa SMP dalam menghadapi Tes Kemampuan Akademik (TKA).

## 🎯 **Fitur untuk Siswa**

### **Authentication**
- ✅ Login dengan email/password
- ✅ Register akun baru
- ✅ Reset password via email
- ✅ Google OAuth integration
- ✅ Session management

### **Dashboard Pribadi**
- ✅ Welcome message dengan nama siswa
- ✅ Statistik pembelajaran (materi selesai, nilai rata-rata, jam belajar)
- ✅ Progress per mata pelajaran
- ✅ Quick access ke fitur utama

### **Materi Pembelajaran**
- ✅ Browse materi berdasarkan bab matematika
- ✅ Filter berdasarkan tipe materi (Artikel, Video, Infografis, Latihan)
- ✅ Filter berdasarkan tingkat kesulitan
- ✅ Detail view dengan rich content
- ✅ Download lampiran materi
- ✅ Progress tracking otomatis

### **Simulasi Ujian**
- ✅ Ujian TKA lengkap
- ✅ Timer otomatis
- ✅ Scoring real-time
- ✅ Pembahasan soal
- ✅ History nilai

### **Progress Tracking**
- ✅ Dashboard progress per bab
- ✅ Riwayat pembelajaran
- ✅ Achievement system
- ✅ Rekomendasi materi berikutnya

## 📁 **Struktur Folder**

```
WEBSITE_UNTUK_PENGGUNA/
├── index.html               # Halaman login siswa
├── daftarsekarang.html      # Halaman register
├── halamanpertama.html      # Dashboard siswa
├── halamanpertama.js        # Dashboard functionality
├── materi.html              # Halaman browse materi
├── lupakatasandi.html       # Reset password
├── updatepassword.html      # Update password setelah reset
├── ujian.html               # Halaman ujian
├── ujian.js                 # Ujian functionality
├── script.js                # Main JavaScript untuk semua halaman
├── style.css                # Global styles
├── halamanpertama.css       # Dashboard specific styles
├── auth.js                  # Authentication functions
├── supabaseClient.js        # Supabase client configuration
├── apisgoogle.js            # Google OAuth integration
├── schema.sql               # Database schema reference
├── package.json             # Dependencies
└── IMAGE_DISPLAY_GUIDE.md   # Guide for image handling
```

## 🚀 **Cara Menjalankan**

### **1. Setup Database**
```bash
# Pastikan database Supabase sudah setup dengan schema.sql
# Jalankan migration scripts jika diperlukan
```

### **2. Install Dependencies**
```bash
npm install
```

### **3. Jalankan Server**
```bash
# Gunakan server lokal
python -m http.server 8000
# Atau
npx http-server -p 8000
```

### **4. Akses Website**
- **Login/Register**: `http://localhost:8000/index.html`
- **Dashboard**: `http://localhost:8000/halamanpertama.html`
- **Materi**: `http://localhost:8000/materi.html`
- **Ujian**: `http://localhost:8000/ujian.html`

## 🔐 **Keamanan & Authentication**

### **User Authentication**
- ✅ Supabase Auth integration
- ✅ JWT token management
- ✅ Password hashing
- ✅ Email verification
- ✅ Session persistence

### **Data Protection**
- ✅ Row Level Security (RLS)
- ✅ User-specific data access
- ✅ Input validation
- ✅ XSS protection

## 📚 **Fitur Pembelajaran**

### **Materi Interaktif**
- **Rich Content**: HTML, images, videos, LaTeX formulas
- **Progressive Disclosure**: Step-by-step learning
- **Interactive Elements**: Quizzes, exercises
- **Multimedia Support**: Videos, infographics, animations

### **Assessment System**
- **Adaptive Testing**: Difficulty adjustment
- **Real-time Feedback**: Instant scoring
- **Detailed Analytics**: Performance breakdown
- **Progress Visualization**: Charts and graphs

### **Personalization**
- **Learning Paths**: Customized curriculum
- **Smart Recommendations**: AI-powered suggestions
- **Achievement System**: Badges and certificates
- **Progress Milestones**: Goal tracking

## 📱 **Responsive Design**

### **Desktop (>1024px)**
- Full dashboard layout
- Multi-column grids
- Advanced navigation
- Rich media display

### **Tablet (768px - 1024px)**
- Adapted grid layouts
- Touch-friendly controls
- Optimized navigation

### **Mobile (<768px)**
- Single column layout
- Bottom navigation
- Swipe gestures
- Optimized forms

## 🎨 **UI/UX Features**

- **Modern Design**: Clean, intuitive interface
- **Smooth Animations**: CSS transitions
- **Loading States**: User feedback
- **Error Handling**: Friendly error messages
- **Accessibility**: WCAG compliant
- **Performance**: Optimized assets

## 📊 **Analytics & Tracking**

### **Learning Analytics**
- **Time Spent**: Per materi/session
- **Completion Rates**: Progress tracking
- **Performance Metrics**: Scores, accuracy
- **Learning Patterns**: Study habits analysis

### **User Engagement**
- **Session Duration**: Active learning time
- **Feature Usage**: Most used features
- **Drop-off Points**: Improvement areas
- **Satisfaction Scores**: User feedback

## 🔧 **Technical Stack**

- **Frontend**: HTML5, CSS3, JavaScript (ES6+)
- **Backend**: Supabase (PostgreSQL, Auth, Storage)
- **Libraries**:
  - TinyMCE (Rich text editor)
  - Chart.js (Analytics visualization)
  - KaTeX (Math rendering)
  - Font Awesome (Icons)

## 📞 **Support & Documentation**

- **User Guide**: Integrated help system
- **Video Tutorials**: Step-by-step guides
- **FAQ Section**: Common questions
- **Contact Support**: Help desk integration

## 🎯 **Learning Objectives**

Platform ini dirancang untuk membantu siswa SMP:

1. **Master TKA Content**: Komprehensif coverage semua bab
2. **Develop Problem-solving**: Critical thinking skills
3. **Build Confidence**: Practice dengan feedback real-time
4. **Track Progress**: Visual progress indicators
5. **Enjoy Learning**: Gamified learning experience

---

**EduLearn TKA - Belajar Pintar, Sukses di TKA!** 🚀📚