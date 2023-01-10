<template>
    <div class="container-fluid content d-flex flex-column justify-content-start bg-dark py-4">
        <div class="container">
            <div class="row">
                <div class="col-lg-4 grid-margin stretch-card">
                    <card-top-left/>
                </div>
                <div class="col-lg-8 grid-margin stretch-card">
                   <card-top-right/>    
                </div>
            </div>
        </div>
        <div class="container">
            <div class="row">
                <div class="col-lg-9 grid-margin stretch-card">
                    <CardSetParam></CardSetParam>
                </div>
                <div class="col-lg-3 grid-margin stretch-card">
                    <card-option/>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

import CardTopLeft from './slide_setting/CardTopLeft.vue'
import CardTopRight from './slide_setting/CardTopRight.vue'
import CardSetParam from './slide_setting/CardSetParam.vue'
import CardOption from './slide_setting/CardOption.vue'
export default{
    name:'SlidSetting',
    components:{
        CardTopLeft,
        CardTopRight,
        CardSetParam,
        CardOption,
        // buttonToggle
    }
}
</script>

<style>
/* .card-top-left{
    height: 225px;
} */
</style>