<template>
    <div class="container-scroller">
        <dashboardSidebar />
        <!-- partial -->
        <div class="container-fluid page-body-wrapper">
            <dashboardNav />
            <!-- partial -->
            <div class="main-panel pt-0">
                <div class="content-wrapper">
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