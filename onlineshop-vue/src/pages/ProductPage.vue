<script setup>
import ProductCard from '../components/ProductCard.vue'
const daftarProduk = [
 { id: 1, nama: 'Seragam Sekolah', harga: 175000, gambar:
'https://placehold.co/150' },
 { id: 2, nama: 'Kacu Sekolah', harga: 10000, gambar:
'https://placehold.co/150' },
 { id: 3, nama: 'Dasi Sekolah', harga: 20000, gambar:
'https://placehold.co/150' },
]
</script>

<template>
  <main class="page">
  <section class="page-header">
   <div class="container">
    <h1>Produk Kami</h1>
   </div>
  </section>
  <div class="container product-list grid">
  <ProductCard
   v-for="produk in daftarProduk"
   :key="produk.id"
   :nama="produk.nama"
   :harga="produk.harga"
   :gambar="produk.gambar"
  />
  </div>
  </main>
</template>

<style scoped>

.grid {
 display: flex;
 gap: 16px;
 flex-wrap: wrap;
}

</style>