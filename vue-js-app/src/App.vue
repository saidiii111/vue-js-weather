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



</style>
