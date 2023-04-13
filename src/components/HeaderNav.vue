<template>
  <header>
    <nav class="container">

      <a href="/"><img src="./images/VINICIUS MIGUEL.svg" id="logo" alt="logo da pagina"></a>

      <img v-on:click="openMenu" alt="Abrir menu" id="menu-button" src="https://raw.githubusercontent.com/william-costa/wdev-mock-site-resources/master/assets/images/menu.svg" >

      <div id="menu-overlay" v-if="menuActive"></div>

      <div id="menu-items" :class="{active:menuActive}">

        <img src="./images/VINICIUS MIGUEL.svg" id="menu-logo" alt="logo do menu lateral">

        <ul>
          <li><a href="/inicio">Inicio</a></li>
          <li><a href="/conhecimentos">Conhecimentos</a></li>
          <li><a href="/projetos">Projetos</a></li>
          <li><a href="/sobre-mim">Sobre mim</a></li>
          <li><a href="/contato">Contato</a></li>
        </ul>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  name:'HeaderNav',
  data(){
    return {
      menuActive: false
    }
  },
  methods:{
    openMenu: function(){
      this.menuActive = true;
    },
    closeMenu: function(){
      this.menuActive = false;
    }
  }
}
</script>

<style scoped>

header{
  background-color: var(--hover-color);
  width: 100%;
  height: 60px;
  display: flex;
  justify-content: center;
  align-items: center;
}

nav{
  display: flex;
  justify-content: space-between;
}

#logo {
  width: 130px;
}

#menu-button{
  width: 30px;
}

#menu-overlay{
  position: fixed;
  top: 0;
  left: 0;
  width: 40%;
  height: 100vh;
  background-color:  #010101;
  opacity: 0.5;
}

#menu-logo {
  width: 150px;
  margin-top: 15px;
  margin-bottom: 35px;
  
}

#menu-items {
  position: fixed;
  top: 0;
  right: 0;
  background-color: var(--hover-color);
  opacity: 0.8;
  width: 60%;
  height: 100vh;
  display: none;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;

}

#menu-items .active{
  display: flex;

}

ul{
  list-style: none;
  text-align: center;
}

ul li{
  margin: 30px 0px;
}

ul li a {
  color: var(--text-color);
  font-weight: 900;
  font-size: 2rem;
}


</style>