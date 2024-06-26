<template>
    <q-card class="q-pa-md weather-widget">
      <q-card-section>
        <div class="text-h6">Widget Cuaca</div>
      </q-card-section>
      <q-card-section>
        <q-input filled v-model="city" @keyup.enter="fetchWeather" label="Masukkan nama kota" />
        <q-btn class="q-mt-md" color="primary" @click="fetchWeather">Cari</q-btn>
      </q-card-section>
      <q-card-section v-if="weather">
        <div>
          <p>{{ weather.name }}</p>
          <p>{{ weather.weather[0].description }}</p>
          <p>{{ (weather.main.temp - 273.15).toFixed(2) }}°C</p>
        </div>
      </q-card-section>
      <q-card-section v-else>
        <p>Memuat...</p>
      </q-card-section>
    </q-card>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    name: 'WeatherWidget',
    data() {
      return {
        city: '',
        weather: null,
        apiKey: '582e0922efcea48ff86a04b957b4e429'
      };
    },
    methods: {
      fetchWeather() {
        const url = `https://api.openweathermap.org/data/2.5/weather?q=${this.city}&appid=${this.apiKey}`;
        axios.get(url)
          .then(response => {
            this.weather = response.data;
          })
          .catch(error => {
            console.error("Error fetching weather data:", error);
          });
      }
    },
    mounted() {
      this.fetchWeather();
    }
  };
  </script>
  
  <style scoped>
  .weather-widget {
    max-width: 300px;
    margin: 50px auto;
    text-align: center;
  }
  </style>
  