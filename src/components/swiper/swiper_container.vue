<template>
    <SwiperNav />
    <div class="content mb-4">
        <swiper :pagination="pagination" :spaceBetween="0" :hashNavigation="{ watchState: true, }" :navigation="true"
            :modules="modules" class="mySwiper">
            <swiper-slide>
                <SlideComsumption />
            </swiper-slide>
            <swiper-slide>
                <SlideMonitor />
            </swiper-slide>
            <swiper-slide>
                <SlideTrendChart/>
            </swiper-slide>
            <swiper-slide>
                <SlideSetting/>
            </swiper-slide>
            <swiper-slide>
                Slide 5
            </swiper-slide>
        </swiper>
    </div>
</template>

<script>

// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from "swiper/vue";
// Import Swiper styles
import "swiper/css";
import "swiper/css/pagination";
import { Pagination, Navigation } from "swiper";

import SlideComsumption from './slides/slide_comsumption.vue';
import SlideMonitor from './slides/slide_monitor.vue';
import SlideTrendChart from './slides/slide_trendChart.vue';
import SlideSetting from './slides/slide_setting.vue';

// import SlideCustomChart from './slides/slide_customchart.vue';

import SwiperNav from './swiper_navbar.vue';
export default {
    components: {
        Swiper,
        SwiperSlide,
        SlideComsumption,
        SlideMonitor,
        SlideTrendChart,
        SlideSetting,
        // SlideCustomChart,
        SwiperNav,
    },
    setup() {
        return {
            pagination: {
                clickable: true,
                renderBullet: function (index, className) {
                    return '<span class="' + className + '">' + (index + 1) + "</span>";
                },
            },
            modules: [Pagination, Navigation],
        };
    },
};
</script>
<style scoped>
.swiper-nav {
    left: 0;
}

#app {
    height: 100%
}

html,
body {
    position: relative;
    height: 100%;
}

body {
    background: #eee;
    font-family: Helvetica Neue, Helvetica, Arial, sans-serif;
    font-size: 14px;
    color: #000;
    margin: 0;
    padding: 0;
}

.content {
    height: 800px;
    max-height: auto;

}

@media (min-width: 1000px) {
    .content {
        height: 575px;
        max-height: auto;
    }
}

@media (min-width: 1100px) {
    .content {
        height: 690px;
        max-height: auto;

    }
}

@media (min-width: 1300px) {
    .content {
        height: 770px;
        max-height: auto;

    }
}

@media (min-width: 1600px) {
    .content {
        height: 800px;
        max-height: auto;

    }
}

.sidebar-icon-only .navbar {
    left: 0;
}

.swiper-slide {
    text-align: center;
    font-size: 18px;
    background: #191c24;

    display: -webkit-box;
    display: -ms-flexbox;
    display: -webkit-flex;
    display: flex;
    -webkit-box-pack: center;
    -ms-flex-pack: center;
    -webkit-justify-content: center;
    justify-content: center;
    -webkit-box-align: center;
    -ms-flex-align: center;
    -webkit-align-items: center;
    align-items: center;
}

/* .swiper-slide img {
    display: block;
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.swiper-pagination-bullet {
    width: 20px;
    height: 20px;
    text-align: center;
    line-height: 20px;
    font-size: 12px;
    color: rgb(255, 255, 255);
    opacity: 1;
    background: rgba(0, 0, 0, 0.2);
}

.swiper-pagination-bullet-active {
    color: rgb(255, 255, 255);
    background: #007aff;
} */
</style>
