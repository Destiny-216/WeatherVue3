<template>
    <div class="weather-card" v-if="weatherData">
      <h2>{{ weatherData.name }}</h2>
      <div class="temperature">
        {{ Math.round(weatherData.main.temp) }}°C
      </div>
      <div class="description">
        {{ weatherData.weather[0].description }}
      </div>
      <div class="details">
        <div class="detail-item">
          <strong>湿度:</strong> {{ weatherData.main.humidity }}%
        </div>
        <div class="detail-item">
          <strong>風速:</strong> {{ weatherData.wind.speed }} m/s
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { defineProps } from 'vue';
  
  const props = defineProps({
    weatherData: {
      type: Object,
      required: true
    }
  });
  </script>
  
  <style scoped>
  .weather-card {
    text-align: center;
    background: linear-gradient(135deg, #a1c4fd, #c2e9fb);
    border-radius: 15px;
    padding: 30px;
    color: #fff;
    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
    transition: transform 0.3s ease-in-out;
  }
  
  .weather-card:hover {
    transform: translateY(-5px);
  }
  
  h2 {
    font-size: 2.5rem;
    margin-top: 0;
    font-weight: 300;
  }
  
  .temperature {
    font-size: 5rem;
    font-weight: 200;
    margin: 10px 0;
  }
  
  .description {
    font-size: 1.5rem;
    text-transform: capitalize;
    margin-bottom: 20px;
  }
  
  .details {
    display: flex;
    justify-content: space-around;
    font-size: 1.1rem;
    background-color: rgba(255, 255, 255, 0.2);
    padding: 15px;
    border-radius: 10px;
  }
  </style>