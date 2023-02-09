<template>
    <div class="container-scroller">
        <dashboardSidebar />
        <!-- partial -->
        <div class="container-fluid page-body-wrapper">
            
            <dashboardNav />
            <!-- partial -->
            <div class="main-panel pt-0">
               
                <div class="content-wrapper">
                    
                 
                    <div class="bubbles">
                        <span style="--i:11;"></span>
                        <span style="--i:12;"></span>
                        <span style="--i:24;"></span>
                        <span style="--i:10;"></span>
                        <span style="--i:14;"></span>
                        <span style="--i:23;"></span>
                        <span style="--i:18;"></span>
                        <span style="--i:16;"></span>
                        <span style="--i:19;"></span>
                        <span style="--i:20;"></span>
                        <span style="--i:22;"></span>
                        <span style="--i:25;"></span>
                        <span style="--i:18;"></span>
                        <span style="--i:21;"></span>
                        <span style="--i:15;"></span>
                        <span style="--i:13;"></span>
                        <span style="--i:26;"></span>
                        <span style="--i:17;"></span>
                        <span style="--i:13;"></span>
                        <span style="--i:28;"></span>
                        <span style="--i:11;"></span>
                        <span style="--i:12;"></span>
                        <span style="--i:24;"></span>
                        <span style="--i:10;"></span>
                        <span style="--i:14;"></span>
                        <span style="--i:23;"></span>
                        <span style="--i:18;"></span>
                        <span style="--i:16;"></span>
                        <span style="--i:19;"></span>
                        <span style="--i:20;"></span>
                        <span style="--i:22;"></span>
                        <span style="--i:25;"></span>
                        <span style="--i:18;"></span>
                        <span style="--i:21;"></span>
                        <span style="--i:15;"></span>
                        <span style="--i:13;"></span>
                        <span style="--i:26;"></span>
                        <span style="--i:17;"></span>
                        <span style="--i:13;"></span>
                        <span style="--i:28;"></span>
                        
                    </div>
                    <swiperContainer />
                </div>
                <!-- content-wrapper ends -->
                <dashboradFooter />
            </div>
            <!-- main-panel ends -->
        </div>
        <!-- page-body-wrapper ends -->
    </div>
</template>

<script>
import dashboradFooter from './dashboard_footer.vue';
import dashboardSidebar from './dashboard_sidebar.vue';
import dashboardNav from './dashboard_navbar.vue';
import swiperContainer from '../swiper/swiper_container.vue';

export default {
    components: {
        dashboradFooter,
        dashboardSidebar,
        dashboardNav,
        swiperContainer,
    }
}
</script>

<style>

</style>