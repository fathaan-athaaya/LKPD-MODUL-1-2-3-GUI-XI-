<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'

const props = defineProps({
 nama: { type: String, required: true },
 harga: { type: Number, required: true },
 gambar: { type: String, required: true },
})

const zoomTerbuka = ref(false)

function tambahKeKeranjang(nama) {
 const suara = new Audio('/audio/faaah.mp3')
 suara.play()
 alert(`${nama} ditambahkan ke keranjang!`)
}

function bukaZoom() {
 zoomTerbuka.value = true
 document.body.style.overflow = 'hidden'
}

function tutupZoom() {
 zoomTerbuka.value = false
 document.body.style.overflow = ''
}

function tanganiEscape(event) {
 if (event.key === 'Escape' && zoomTerbuka.value) tutupZoom()
}

onMounted(() => window.addEventListener('keydown', tanganiEscape))
onBeforeUnmount(() => {
 window.removeEventListener('keydown', tanganiEscape)
 document.body.style.overflow = ''
})
</script>

<template>
 <article class="product-card">
  <button class="product-image-button" type="button" @click="bukaZoom">
   <img :src="props.gambar" :alt="props.nama" class="product-image" loading="lazy" />
  </button>
  <h3>{{ props.nama }}</h3>
  <p class="product-price">Rp {{ props.harga.toLocaleString('id-ID') }}</p>
  <button class="btn-pill-solid" type="button" @click="tambahKeKeranjang(props.nama)">
   Tambah ke Keranjang
  </button>
 </article>

 <Teleport to="body">
  <div
   v-if="zoomTerbuka"
   class="fixed inset-0 z-50 flex items-center justify-center bg-black/60 p-4"
   @click="tutupZoom"
  >
    <div class="zoom-content" @click.stop>
     <img :src="props.gambar" :alt="props.nama" class="zoom-image" />
     <p>{{ props.nama }}</p>
   </div>
  </div>
 </Teleport>
</template>