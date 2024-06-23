<template>
  <q-page class="flex flex-center cloud-background">
    <div class="text-content">
      <h3 class="title">Welcome To Weather-S</h3>
      <h5 class="subtitle">Project by Syifa Nur Medina</h5>
      <q-btn label="Go to Weather" @click="goToWeather" class="btn-go-to-weather" />
    </div>
  </q-page>
</template>
<script>
export default {
  name: 'HomePage',
  methods: {
    goToWeather() {
      this.$router.push('/weather');
    }
  }
};
</script>
<style scoped>
.cloud-background {
  background-image: url('/src/assets/awan1.jpeg');
  background-size: cover;
  background-position: center;
  height: 100vh;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.text-content {
  font-family: "Times New Roman", Times, serif; 
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  text-align: center;
}

.title {
  color: #333;
  margin-bottom: 10px;
  font-size: 2em;
}

.subtitle {
  color: #000000;
  margin-bottom: 20px;
  font-size: 1.2em;
}

.btn-go-to-weather { 
  color: #000000; 
  border-radius: 5px;
  padding: 10px 20px;
  font-size: 1em;
  transition: all 0.3s ease;
}

.btn-go-to-weather:hover {
  background-color: #555; 
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3); 
}
</style>
