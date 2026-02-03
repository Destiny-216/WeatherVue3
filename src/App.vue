<template>
    <div id="app-container">
        <h1>天気予報</h1>
        <div class="search-container">
            <input v-model="city" @keyup.enter="getWeather" placeholder="都市名を入力します， 例:Osaka" />
            <button class="search-btn" @click="getWeather">検索</button>
        </div>
        <div v-if="loading" class="loading">読み込み中...</div>
        <div v-if="error" class="error">{{ error }}</div>
        <WeatherCard v-if="weatherData" :weatherData="weatherData" />
        <div v-if = "!weatherData && !loading && !error" class="tip"> 都市名を入力して天気を確認します。</div>
    </div>

</template>

<script setup lang='ts'>
import WeatherCard from './components/WeatherCard.vue';
import {ref} from 'vue';
import axios from 'axios';

const city = ref('');
const loading = ref (false);
const error = ref('');
const weatherData = ref(null);

const API_KEY = '024ea8e2275fffc0775123a4402b887c';
const BASE_URL = 'https://api.openweathermap.org/data/2.5/weather';

const getWeather = async() => {
    if(!city.value){
        error.value = '都市名を入力してください';
        return;
    }
    loading.value = true;
    error.value = '';
    weatherData.value = null;
    
    try{
        const response = await axios.get(BASE_URL,{
            params:{
                q:city.value,
                appid:API_KEY,
                units:'metric',
                lang: 'jp'
            }
        });
        weatherData.value = response.data;
    }catch(err:any){
        if(err.response && err.response.status === 404){
            error.value = '該当する都市の天気情報が見つかりません。';
        }else{
            error.value = '天気情報の取得に失敗しました。しばらくしてから再試行してください。';
        }
    }finally{
        loading.value = false;
    }
    
}
</script>

<style lang="scss" scoped>
h1{
    text-align: center;
    color: #101010;
    font-size: 2.5rem;
    font-weight: 200;
}


</style>