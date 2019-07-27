<template>
  <section id="warp">
        <main class="body_box">
            <section class="body">
                <div class="banner">
                    <!-- <Carousel autoplay v-model="value1" loop>
                        <CarouselItem v-for="(val,key) in banners" :key="key">
                            <img :src="val.imgurl"/>
                        </CarouselItem>
                    </Carousel> -->
                    <van-swipe :autoplay="2000" indicator-color="white">
                        <van-swipe-item v-for="(val,key) in banners" :key="key">
                            <img :src="val.imgurl"/>
                        </van-swipe-item>
                    </van-swipe>

                </div>
                <div class="list">
                    <ul>
                        <li 
                            v-for="(val,key) in ary"
                            @click="addmusic(val.hash)"
                             :key="key"
                        >
                           <p>
                               {{val.filename}}
                           </p>
                            <img src="../images/upload.png" />
                        </li>
                    </ul>
                </div>
            </section>
        </main>
  </section>
</template>

<script>
// import { Carousel, CarouselItem} from 'iview';
import { mapMutations,mapActions } from 'vuex'
export default {
    name: 'home',
    data () {
        return {
            value1: 0,
            banners:[],
            ary:[]
        }
    },
   async created(){
        const data = await fetch('/api?json=true').then(e=>e.json())
        this.banners = data.banner;
        this.ary = data.data;
        this.addMusicAry(data.data);
    },
    components:{
    },
    methods:{
        ...mapMutations(['addMusicAry']),
        ...mapActions(['addmusic'])
    }

}
</script>
