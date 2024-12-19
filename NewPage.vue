<template>
  <div style="justify-items: center">
    <p v-if="a">Welcome To My Project</p>

    <button @click="openshow">
      <span v-if="a">Hidden</span>
      <span v-else>Show</span>
    </button>

    <h2 style="margin-top: 20px">Manakah Box Yang Berwarna Pink?</h2>
    <div class="induk">
      <div v-if="view == 'pink'" class="box1"></div>
      <div v-if="view == 'blue'" class="box2"></div>
      <div v-if="view == 'purple'" class="box3"></div>
      <div v-if="view == 'red'" class="box4"></div>
    </div>
    <div class="induk" style="margin-top: 10px">
      <button @click="show(1)" class="bt1" type="button">1</button>
      <button @click="show(2)" class="bt2" type="button">2</button>
      <button @click="show(3)" class="bt3" type="button">3</button>
      <button @click="show(4)" class="bt4" type="button">4</button>
    </div>
    <div>
      <h2 style="text-align: center;">Kesempatan Anda Tinggal = {{ k }} kali</h2>
      <h2 style="text-align: center;"><a href="https://hung18.site/">{{ ket }}</a></h2>
    </div>
    {{ view }}
  </div>
</template>

<script setup>
import { ref } from "vue";

const a = ref(false);
const view = ref("white");
const k = ref(3);
const ket = ref("");

function openshow() {
  a.value = !a.value;
}

function show(pil) {
  if (pil == 1) {
    view.value = "pink";
    ket.value = "Selamat Anda Memenangkan 10 Unit Mobil Pajero Dan 100 Iphone 15 Promax! Silahkan Hubungi Admin Untuk Mengklaim Hadiahnya WA: +6281252456382";
  } else if (pil == 2) {
    view.value = "blue";
    k.value = k.value - 1;
    if (k.value <= 0) {
      ket.value="Anda Kalah! Silahkan Coba Lagi"
    } else {
      ket.value="Pilihan Anda Salah!"
    }
  } else if (pil == 3) {
    view.value = "purple";
    k.value = k.value - 1;
     if (k.value <= 0) {
      ket.value="Anda Kalah! Silahkan Coba Lagi"
    } else {
      ket.value="Pilihan Anda Salah!"
    }
  } else if (pil == 4) {
    view.value = "red";
    k.value = k.value - 1;
     if (k.value <= 0) {
      ket.value="Anda Kalah! Silahkan Coba Lagi"
    } else {
      ket.value="Pilihan Anda Salah!"
    }
  }
}
</script>

<style>
.induk {
  display: flex;
  gap: 14px;
  border-radius: solid black;
}
.box1 {
  width: 150px;
  height: 150px;
  border: solid 1px black;

  background-color: pink;
}
.box2 {
  width: 150px;
  height: 150px;
  border: solid 1px black;

  background-color: blue;
}
.box3 {
  width: 150px;
  height: 150px;
  border: solid 1px black;

  background-color: purple;
}
.box4 {
  width: 150px;
  height: 150px;
  border: solid 1px black;

  background-color: red;
}

.bt1 {
  font-size: 20px;
  bottom: -30px;
}
.bt2 {
  font-size: 20px;
  bottom: -30px;
}
.bt3 {
  font-size: 20px;
  bottom: -30px;
}
.bt4 {
  font-size: 20px;
  bottom: -30px;
}
</style>
