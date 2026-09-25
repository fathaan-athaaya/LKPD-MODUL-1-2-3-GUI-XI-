<script setup>
const fitur = [
 { id: 1, emoji: '☑️', judul: 'Kualitas Terjamin', deskripsi: 'Bahan dipilih langsung oleh tim kami.' },
 { id: 2, emoji: '🤑', judul: 'Harga Bersahabat', deskripsi: 'Harga ramah di kantong siswa.' },
 { id: 3, emoji: '🏫', judul: 'Ambil di Rumah', deskripsi: 'Tidak perlu ongkir, ambil di koperasi.' },
]
</script>

<template>
 <main class="page landing">
  <section class="hero">
   <div class="container">


    <h1>Butuh Perlengkapan Sekolah? Berkualitas &amp; Affordable</h1>
    <p class="subtitle">Dari Seragam, kacu, sampai Dasi sekolah, Semua ada di sini..</p>
    <RouterLink to="/product" class="btn-pill">Lihat Produk</RouterLink>
   </div>
  </section>

  <section class="fitur">
   <div class="container">
    <div class="cards">
     <article
      v-for="item in fitur"
      :key="item.id"
      class="card"
     >
      <span class="emoji">{{ item.emoji }}</span>
      <h3>{{ item.judul }}</h3>
      <p>{{ item.deskripsi }}</p>
     </article>
    </div>
   </div>
  </section>

  <section class="video-section">
   <div class="container">
    <h2>Video Pilihan Kami</h2>
    <video class="intro-video" controls preload="metadata">
     <source src="/video/mov_bbb.mp4" type="video/mp4" />
     Browser kamu tidak mendukung pemutar video.
    </video>
   </div>
  </section>
 </main>
</template>
<style scoped>
video {
 margin-top: 16px;
 border-radius: 10px;
 display: block;
}
.landing {
 padding: 0;
}
.video-section {
 padding: 1px 0 90px;
}
.video-section h2 {
 text-align: center;
 margin-bottom: 20px;
}
.intro-video {
 width: min(100%, 760px);
 aspect-ratio: 16 / 9;
 margin: 0 auto;
 object-fit: cover;
 background: #2f5148;
 box-shadow: var(--shadow);
}
.hero {
 background: var(--gradient-hero);
 color: #ffffff;
 text-align: center;
 padding: 100px 20px;
}
.hero h1 {
 color: #fff;
 font-size: clamp(1.9rem, 5vw, 3rem);
 max-width: 760px;
 margin: 0 auto 16px;
}
.subtitle {
 color: rgba(255, 255, 255, 0.92);
 font-size: clamp(1rem, 2.5vw, 1.2rem);
 max-width: 520px;
 margin: 0 auto 36px;
}
.fitur {
 padding: 64px 0 80px;
}
.cards {
 display: flex;
 gap: 24px;
 flex-wrap: wrap;
 justify-content: center;
}
.card {
 flex: 1 1 240px;
 max-width: 320px;
 padding: 32px 24px;
 background: #fff;
 border-radius: var(--radius);
 box-shadow: var(--shadow);
 text-align: center;
 transition: transform 0.2s ease, box-shadow 0.2s ease;
}
.card:hover {
 transform: translateY(-4px);
 box-shadow: var(--shadow-hover);
}
.emoji {
 display: block;
 font-size: 2.4rem;
 margin-bottom: 12px;
}
.card h3 {
 margin-bottom: 6px;
 font-size: 1.15rem;
}
.card p {
 font-size: 0.95rem;
}
@media (max-width: 640px) {
 .hero { padding: 72px 20px; }
 .fitur { padding: 48px 0 64px; }
}
</style>