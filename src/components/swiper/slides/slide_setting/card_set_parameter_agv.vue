<template>
    <div class="card mb-4">
        <div class="card-body">
            <div class="row px-2">
                <div class="col-9 d-flex justify-content-started px-0">
                    <div class="d-flex h5 mx-0 mt-1">
                        SET PARAMETER AGV
                    </div>
                    <div class="d-flex">
                        <div class="btn btn-dark text text-warning mx-3">
                            CONFIRM STANDBY AGV 1
                        </div>
                    </div>
                </div>
                <div class="col-3 d-flex px-3">
                    OPTION
                </div>
            </div>

            <div class="row">
                <div class="col-9 mt-2" style="height:24rem;">
                    <div class="agv-set-param" v-for="cl in car_list" :key="cl">
                        <com-set-param :name="cl.name" :speed="cl.speed" :battery="cl.battery" />
                    </div>
                </div>
                <div class="col-3 bg-dark d-flex" style="height:24rem;">
                    <div class="d-flex flex-column justify-content-around card-option-content">
                        <div class="text-primary text-center"><small>WORNNING REPORT</small></div>
                        <div class="app-option">
                            <div class="container card-option-content">
                                <div class="row option-item-row">
                                    <div class="col-md-6 d-flex flex-column justify-content-center">
                                        <div>
                                            <img class="img-social"
                                                src="https://static.newmobilelife.com/wp-content/uploads/2014/10/LineforiPad00-210x210.png"
                                                alt="">
                                        </div>
                                    </div>
                                    <div class="col-md-6 d-flex flex-column justify-content-center text-center">
                                        <div class="text-warning mb-2"><small>LINE APP</small> </div>
                                        <div class="mb-2 mx-4"><button-toggle /></div>
                                        <div class="text-warning"><small>CONFIRM</small> </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div class="app-option">
                            <div class="container card-option-content">
                                <div class="row option-item-row">
                                    <div class="col-md-6 d-flex flex-column justify-content-center">
                                        <div>
                                            <img class="img-social"
                                                src="https://logos-download.com/wp-content/uploads/2016/05/Gmail_logo_icon.png"
                                                alt="">
                                        </div>
                                    </div>
                                    <div class="col-md-6 d-flex flex-column justify-content-center text-center">
                                        <div class="text-warning mb-2"><small>GMAIL</small> </div>
                                        <div class="mb-2 mx-4"><button-toggle /></div>
                                        <div class="text-warning"><small>CONFIRM</small> </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

</template>

<script>
import ButtonToggle from '@/components/button/buttonToggle.vue';
import ComSetParam from './ComSetParam.vue';

export default {
    components: {
        ButtonToggle,
        ComSetParam,
    },
    data() {
        return {
            car_list: [
                { name: 'AGV 1', speed: '2 m/s', battery: '25 %' },
                { name: 'AGV 2', speed: '0 m/s', battery: '0 %' },
                { name: 'AGV 3', speed: '0 m/s', battery: '0 %' },
            ]
        }
    }
}
</script>

<style lang="scss" scoped>

</style>