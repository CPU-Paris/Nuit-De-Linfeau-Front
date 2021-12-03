<template>
  <div class="themeSwitcherComponent">      
    <a :class="{'disabled': darkTheme}" href="#!" @click="switchTheme()" >
        <img src="/img/lightTheme.svg" alt="lightTheme" />
    </a>
    <a :class="{'disabled': !darkTheme}" href="#!" @click="switchTheme()" >
        <!--todo : remplacer par une image appropriée-->
        <img src="/img/lightTheme.svg" alt="darkTheme" style="filter: brightness(0.2);" />
    </a>
  </div>
  
</template>

<script>
export default {

    data() {
        return {
            darkTheme: true
        }
    },
    methods: {
        switchTheme() {
            this.darkTheme = !this.darkTheme;
        }
    }
}
</script>

<style>
.themeSwitcherComponent img {
    width: 3.8em;
    margin-top: 0.5em;
    margin-right: 1.4em;
}

.themeSwitcherComponent {
    display: block;
    justify-content: center;
    align-items: center;
    position: relative;
}
.themeSwitcherComponent span {
    line-height: 5em;
}
.themeSwitcherComponent a {
    display: flex;
    position: relative;
    top:0;
    left:0;
    z-index: 2;
    opacity: 1;
    transition: all 0.3s ease-in-out;
}
.themeSwitcherComponent a.disabled {
    position: absolute;
    z-index: 1;
    transform: scale(0.8);
    opacity: 0;
}
</style>