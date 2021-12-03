<template>
  <div id="page" class="">
    <div><img id="back" src="https://www.brest-ocean-boat.fr/wp-content/uploads/2020/12/Antares11-Fly-0760-1600x1065.jpg"></div>
    <div id="gradient">
      <div id ="infos">
        <h1 id="title"><typing text="Je suis un gentil bato" :speed="90"/></h1>
        <p> <typing text="Motheuur 12 cylindr" :speed="90" :startAfter="2340" /></p>
      </div>
      
    </div>
    
</div>
</template>

<script>
  export default {
    data() {
      return {
      }
    }
  }
</script>

<style>
  body {
    margin: 0;
  }
  

  #gradient {
    min-width: 100vw;
    min-height: 100vh;
    border: 1px solid red;   
    background: linear-gradient(80deg,rgba(26, 26, 26, 0.904) 30%,rgba(43,43,43,0));  
  }

  #back {
    position: fixed;
    min-width: 100vw;
    min-height: 100vh;
    z-index: -1;
  }

  #infos {
    border: 1px solid green;
    min-height: 60vh;
    max-width: 40vw;
    margin-top: 20vh;
    margin-left: 5vw;
    color: white;
    font-size: 300%;
    }

</style>
