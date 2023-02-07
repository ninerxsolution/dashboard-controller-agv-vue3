<template>
    <div class="container-fluid content      pt-3">
        <div class="row">
            <div class="col-md-4 grid-margin stretch-card">
                <CardConnect/>
                
            </div>

            <div class="col-md-8 grid-margin stretch-card">
                <CardDetailParams/>
            </div>
        </div>
        <div class="row">
            <div class="col-12 grid-margin">
                <CardMapRoute/>
            </div>
        </div>
    </div>
</template>

<script>
import CardConnect from './slide_monitor/card_connect_agv.vue';
import CardDetailParams from './slide_monitor/card_datail_parameter_agv.vue';
import CardMapRoute from './slide_monitor/card_map_for_route.vue';
export default {
    name: 'App',
    components: {
        CardConnect,
        CardDetailParams,
        CardMapRoute
    }
}
</script>

<style>
@media (min-width: 1000px) {}

@media (min-width: 1100px) {}

@media (min-width: 1300px) {}

@media (min-width: 1406px) {}

.dummy-meter {
    margin: auto;
    /* color: #00a2ff; */
}
</style>