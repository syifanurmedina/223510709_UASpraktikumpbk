<template>
  <q-layout view="hHh lpR fFf">
    <q-header class="header-gradient" elevated>
      <q-toolbar>
        <q-toolbar-title class="text-brown">Syifa Nur Medina | 4B</q-toolbar-title>
        <q-btn dense flat round icon="menu" @click="toggleRightDrawer" class="text-brown" />
      </q-toolbar>
    </q-header>
    <q-drawer show-if-above v-model="rightDrawerOpen" side="right" bordered class="drawer-gradient">
      <q-list bordered padding>
        <q-item clickable v-ripple @click="goToTask(1)">Tugas 1</q-item>
        <q-item clickable v-ripple @click="goToTask(2)">Tugas 2</q-item>
        <q-item clickable v-ripple @click="goToTask(3)">Tugas 3</q-item>
        <q-item clickable v-ripple @click="goToTask(4)">Tugas 4</q-item>
        <q-item clickable v-ripple @click="goToTask(5)">Tugas 5</q-item>
        <q-item clickable v-ripple @click="goToTask(6)">Tugas 6</q-item>
        <q-item clickable v-ripple @click="goToTask(7)">Tugas 7</q-item>
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>

    <footer class="footer-gradient">
      <p>Ujian Akhir Semester | Praktikum Pemrograman Berbasis Komponen</p>
      <p>Teknik Informatika | Universitas Islam Riau</p>
      <div class="social">
        <a href="https://www.instagram.com/ssyifanm_?igsh=N280dXhxcjg1Nzl2"><i class="bx bxl-instagram-alt"></i></a>
        <a href="https://x.com/fluffycwip"><i class="bx bxl-twitter"></i></a>
      </div>
      <p class="end">&copy;copyright by nncipp</p>
    </footer>
  </q-layout>
</template>

<script>
import { ref } from 'vue'

export default {
  setup() {
    const rightDrawerOpen = ref(false)

    const goToTask = (taskNumber) => {
      const taskLinks = {
        1: 'https://syifa-project-cv.netlify.app/',
        2: 'https://tugas2praktikumpbk.netlify.app/',
        3: 'https://tugas3praktikumpbk.netlify.app/',
        4: 'https://tugas4praktikumpbk.netlify.app/',
        5: 'https://tugas5prakpbk.netlify.app/',
        6: 'https://tugas6praktikumpbk.netlify.app/',
        7: 'https://tugas7praktikumpbk.netlify.app/'
      }
      window.location.href = taskLinks[taskNumber]
    }

    const toggleRightDrawer = () => {
      rightDrawerOpen.value = !rightDrawerOpen.value
    }

    return {
      rightDrawerOpen,
      toggleRightDrawer,
      goToTask
    }
  }
}
</script>

<style>
* {
  font-family: 'Times New Roman', Times, serif;
}

.header-gradient {
  background: linear-gradient(45deg, #ffc7bd, #c76ba8); 
}

.drawer-gradient {
  background: linear-gradient(45deg, #ffc7bd, #c76ba8); 
}

.footer-gradient {
  background: linear-gradient(45deg, #ffc7bd, #c76ba8); 
}

footer {
  position: relative;
  width: 100%;
  height: 230px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding-top: 30px;
}
footer p:nth-child(1) {
  font-size: 30px;
  color: #4e2020;
  margin-bottom: 7px;
  font-weight: bold;
}
footer p:nth-child(2) {
  color: #4e2020;
  font-size: 17px;
  width: 500px;
  text-align: center;
  line-height: 26px;
}

.social {
  display: flex;
}
.social a {
  width: 45px;
  height: 45px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  background: #4e2020;
  margin: 22px 10px;
  color: white;
  text-decoration: none;
  font-size: 20px;
}
.social a:hover {
  transition: 0.4s;
  transform: scale(1.3);
}
.end {
  position: absolute;
  color: #4e2020;
  margin-bottom: -6px;
  font-size: 20px;
}

p {
  font-size: 20px;
  color: rgb(141, 43, 43);
}
</style>
