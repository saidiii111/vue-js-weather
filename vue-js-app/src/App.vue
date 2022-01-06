<template>
 <div id="app">
   <main>
     <div class="search-box">
       <input type="text" class="search-bar" placeholder="Search..." v-model="query"
       @keypress="fetchWeather">
     </div>
     <div class="weather-wrap" v-if="typeof weather.main != 'undefined'">
       <div class="location-box">
         <div class="location">{{ weather.name }}, {{ weather.sys.country }}</div>
         <div class="date">Thursday 06 Jan 2022</div>
       </div>
       <div class="weather-box">
         <div class="temp">{{ Math.round(weather.main.temp) }}9°c</div>
         <div class="weather">{{weather.weather[0].main}}</div>
       </div>
     </div>
   </main>
 </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      api_key: '5d4147f3303193a9b1a6bf4cc0482630',
      url_base: 'https://api.openweathermap.ogg/data/2.5',
      
      weather: {}
    }
  },
  methods: {
    fetchWeather (e) {
      if (e.key == "Enter") {
        fetch(`${this.url_base}weather?q=${this.query}&units=metric&APPID=${this.api_key}`)
        .then(res => {
          return res.json();
        }).then(this.setResults);
      }
    },
    setResults (results) {
      this.weather = results;
    },
    dateBuilder ( {
      let d = new Date();
      let months = ["Jan", "Feb", "Mar", "Apr", "Mai", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Des"];
      let days = ["Sun", "Mon", "Tues", "Wed", "Thurs", "Fri", "Sat"];
    })
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'motserrat', sans-serif;
}

#app {
  background-image: url('./assets/cold.jpg');
  background-size: cover;
  background-position: bottom;
  transition: .4s;
}

main {
  min-height: 100vh;
  padding: 25px;
  
  background-image: linear-gradient(to bottom, rgba(0, 0, 0, .25));
}

.search-box {
  width: 100%;
  margin-bottom: 30px;
}

.search-box .search-bar {
  display: block;
  widows: 100%;
  padding:  15px;

  color: blue;
  font-size: 20px;

  appearance: none;
  border: none;
  outline: none;
  background: none;

  box-shadow: 0px, 0px, 8px rgba(0, 0, 0, .25);
  background-color: rgba(255, 255, 255, .5);
  border-radius: 0px, 16px, 0px, 16px;
  transition: .4s;
}

.search-box .search-bar:focus {
  box-shadow: 0px, 0px, 16px rgba(0, 0, 0, .45);
  background-color: rgba(255, 255, 255, .75);
  border-radius: 16px 0px 16px 0px;
}

.location-box .location {
  color: #fff;
  font-weight: 500;
  font-size: 32px;
  text-align: center;
  text-shadow: 1px 3px rgba(0, 0, 0, .25);
}

.location-box .date {
  color: #fff;
  font-size: 20px;
  font-weight: 300;
  font-style: italic;
  text-align: center;
}

.weather-box {
  text-align: center;
}

.weather-box .temp {
  display: inline-block;
  padding: 10px 25px;
  color: #fff;
  font-size: 102px;
  font-weight: 900;

  text-shadow: 3px 6px rgba(0, 0, 0, .25);
  background-color: rgba(255, 255, 255, .25);
  border-radius: 16px;
  margin: 30px 0px;

  box-shadow: 3px 6px rgba(255, 255, 255, .25);
}

.weather-box weather {
  color: #fff;
  font-size: 48px;
  font-weight: 700;
  font-style: italic;
  text-shadow: 3px 6px rgba(0, 0, 0, .25);
}

</style>
