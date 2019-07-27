<template>
  <div id="app">
        <header>
            <h1>
                酷狗音乐
                <img src="./images/logo.png" alt="酷狗音乐">
            </h1>
            <div class="search">
                <img src="./images/search.png" alt="">
            </div>         
        </header>
        <nav>
            <ul class="nav">
                <li class="active">
                   <router-link to="/">新歌</router-link>
                </li>
                <li>
                    <router-link to="/rank">排行</router-link>
                </li>
                <li>
                   
                    <router-link to="/plist">歌单</router-link>
                </li>
                <li>
                  <router-link to="/singer">歌手</router-link>
                </li>
            </ul>
        </nav>
        <Playboy />
        
    <router-view/>
  </div>
</template>
<script>
import './css/index.css';
import Playboy from './components/playboy.vue';
export default {
  name: 'app',
  components:{
      Playboy
  }
}
</script>
<style>

</style>
