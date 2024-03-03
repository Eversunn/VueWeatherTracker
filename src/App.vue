<script>
import axios from 'axios'
export default {
  data(){
    return{
      city:'',
      error:'',
      info:null
    }
  },
  computed:{
    cityName(){
      return '<<' + this.city + '>>'
    }
  },
  methods:{

    WeatherTracker(){
      if(this.city.trim().length < 2){
        this.error = "Too short name"
        return false
      }
      this.error =''
      axios.get(`https://api.openweathermap.org/data/2.5/weather?q=${this.city}&units=metric&appid=3d9de74844d28377e81415151cbe6a66`)
      .then(res =>(this.info = res.data))
    }
  }
}
</script>

<template>
  <div class="wrapper">
    <h1>Weather Tracker</h1>
    <p>Track Weather in: {{ city == "" ? '':  cityName}}</p>
    <input type="text" v-model="city" placeholder="Input City">
    <p v-if="city==''">Enter City Name</p>
    <button v-else @click="WeatherTracker()">Recieve Weather</button>
    <p class="error">{{ error }}</p>

    <p v-if="info">{{ info.main.temp }}</p>
  </div>
</template>

<style>

.wrapper{
  width: 900px;
  height: 500px;
  border-radius: 50px;
  background-color: rgb(244, 250, 255);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
  justify-content: center;
}
.wrapper input{
  background: transparent;
  border: 2px solid black;
  border-radius: 10px;
  color: rgb(0, 0, 0);
  font-size: 14px;
  padding: 5px;
  outline: none;
}

.wrapper h1{
  font-weight:bolder
}
.wrapper button{
  padding: 5px;
  background: rgb(2,0,36);
background: linear-gradient(22deg, rgba(2,0,36,1) 0%, rgba(200,255,123,1) 0%, rgba(111,231,255,1) 100%);
border: 2px solid black;
border-radius: 10px;
font-size: 16px;
color: rgb(39, 44, 44);
transition: transform 500ms ease;
}
.wrapper button:hover{
  background: rgba(200,255,123,1);
  transform: scale(1.1);
}
.wrapper button:active{
  background: rgb(89, 145, 12);
}
</style>
