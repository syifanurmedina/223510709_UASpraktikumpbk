<template>
  <q-page class="flex flex-center cloud-background">
    <div class="weather-container">
      <q-card class="weather-card">
        <q-card-section>
          <h5 class="text-center title">Check Your Weather Here!</h5>
        </q-card-section>
        <q-card-section>
          <q-input v-model="city" label="Input your city" outlined />
          <q-btn class="bg-black btn-search" label="Search" @click="fetchWeather" />
        </q-card-section>
        <q-card-section v-if="weather">
          <h3 class="weather-info">Location: {{ weather.name }}</h3>
          <p class="text-red-10 weather-info">Temperature: {{ weather.main.temp }}°C</p>
          <p class="weather-info">Description: {{ weather.weather[0].description }}</p>
        </q-card-section>
        <q-card-section v-if="error">
          <p class="text-red-5 error-message">{{ error }}</p>
        </q-card-section>
      </q-card>
    </div>
  </q-page>
</template>
<script>
import axios from 'axios';

export default {
  name: 'WeatherPage',
  data() {
    return {
      city: '',
      weather: null,
      error: ''
    };
  },
  methods: {
    async fetchWeather() {
      const apiKey = '94bf6d59f86ae95e8071e78240546056';
      const url = `https://api.openweathermap.org/data/2.5/weather?q=${this.city}&units=metric&appid=${apiKey}`;
      try {
        const response = await axios.get(url);
        this.weather = response.data;
        this.error = ''; 
      } catch (error) {
        this.error = 'CITY NOT FOUND'; 
      }
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

.weather-container {
  width: 90%;
  max-width: 400px;
  margin: auto;
}

.weather-card {
  background: rgba(255, 255, 255, 0.8);
  border-radius: 15px;
  overflow: hidden;
  box-shadow: 0 6px 8px rgba(0, 0, 0, 0.2);
}

.title {
  color: #333;
  font-weight: bold;
}

.btn-search {
  margin-top: 10px;
  width: 100%;
}

.weather-info {
  font-size: 18px;
  color: #333;
}

.error-message {
  color: #4b1714;
  font-weight: bold;
}

.bg-black {
  background-color: #c76ba8;
  color: #ffffff; 
}

.bg-black:hover {
  background-color: #333333; 
}
</style>
