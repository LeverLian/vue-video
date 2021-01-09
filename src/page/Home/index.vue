<template>
    <div class="home">
        <div class="home-header">
            <Swiper 
                ref="mySwiper"
                :options="swiperOption" 
                class="header-swiper"
                @swiper="onSwiper"
            >
                <SwiperSlide class="swiper-item" v-for="item of swiperList" :key="item.id">
                    <img :src="item.imgUrl" class="header-swiper-img"/>
                </SwiperSlide>
                <div class="swiper-pagination" slot="pagination"></div>
                <div class="swiper-button-prev" slot="button-prev"></div>
                <div class="swiper-button-next" slot="button-next"></div>
            </Swiper>
        </div>
        <div class="home-body">
            <SampleReels />
        </div>
        <div class="home-foot"></div>
    </div>
</template>

<script>

    import { Swiper as SwiperClass, Pagination, Mousewheel, Autoplay, Navigation ,EffectFade,EffectCoverflow} from 'swiper/core'
    import SampleReels from './SampleReels.vue'
    import getAwesomeSwiper from 'vue-awesome-swiper/dist/exporter'
    import 'swiper/swiper-bundle.min.css'
    
    const { Swiper, SwiperSlide } = getAwesomeSwiper(SwiperClass)
    SwiperClass.use([Pagination, Mousewheel, Autoplay,Navigation,EffectFade,EffectCoverflow])

export default {
    components: {
        Swiper,
        SwiperSlide,
        SampleReels
    },
    data() {
        return {
            swiperOption: {
                //slidesPerView: 3,//展示三个
                //slidesPerColumn: 2,//行数
                //spaceBetween: 30,//间距
                effect:'slide',//渐变效果
                // effect: 'coverflow',
                grabCursor: true,
                centeredSlides: true,
                slidesPerView: 'auto',
                coverflowEffect: {
                    rotate: 50,
                    stretch: 0,
                    depth: 100,
                    modifier: 1,
                    slideShadows: true,
                },
                pagination: {
                    el: '.swiper-pagination'
                },
                navigation: {
                    nextEl: ".swiper-button-next",
                    prevEl: ".swiper-button-prev",
                },
                loop: true,
                autoplay: {
                    delay: 2000,
                    disableOnInteraction: false,    
                },
                //滑动速度
                speed: 1000,
                on: {
                    // autoplay:function(a){
                    //     //your code
                    //     console.log(a,'a');
                    // },
                    observerUpdate: function(){
                        console.log(1111);
                    },
                },
            },
            swiperList: [
                {
                    id: "001",
                    imgUrl: require('assets/banner1.jpg'),
                },
                {
                    id: "002",
                    imgUrl: require('assets/banner2.jpg'),
                },
                {
                    id: "003",
                    imgUrl: require('assets/banner3.jpg'),
                },
            ]
        }
    },
    methods: {
        onSwiper(swiper) {
            console.log(swiper)
        },
        onSlideChange() {
            console.log('slide change')
        },
    },
}
</script>

<style lang="scss" scoped>
.home{
    width: 100%;
    height: 100%;
    position: relative;
    .home-header{
        width: 70%;
        height: 30%;
        background: rgba($color: #000, $alpha: 0.9);
        margin: auto;
        .header-swiper{
            width: 80%;
            height: 100%;
        }
        .header-swiper-img{
            height: 100%;
            width: 100%;
        }
        .swiper-button-prev{
            color: rgba($color: #777, $alpha: 0.6);
        }
        .swiper-button-next{
            color: rgba($color: #777, $alpha: 0.6);
        }
    }
    .home-body{
        height: 70%;
        width: 80%;
        position: absolute;
        top: 28%;   
        left: 50%;
        transform: translate(-50%, 0%);
        z-index: -1;
        background: rgba(#dcd , 0.2);
    }
    .home-foot{
        width: 100%;
        background: #fff;
    }
}
</style>