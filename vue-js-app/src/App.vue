<template>
 <div id="app">
   <main>
     <div class="search-box">
       <input type="text" class="search-bar" placeholder="Search..." />
     </div>
   </main>
 </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      api_key: '5d4147f3303193a9b1a6bf4cc0482630'
    }
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


</style>
