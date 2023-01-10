<template>
    <div class="card card-set-param pb-2">
        <div class="container h6 pt-2">
            <div class="row">
                <div class="col-lg-4 pt-2">
                    <span> SET PARAMETER AGV</span>
                </div>
                <div class="col-lg-4">
                    <button class="btn btn-sm btn-dark text-warning h6">CONFIRM STANDBY AGV1</button>
                </div>
            </div>
        </div>
        <div class="container contant-param">
            <div class="d-flex flex-column justify-content-around contant-param">
                <div class="agv-set-param" v-for="cl in car_list" :key="cl">
                    <com-set-param :name="cl.name" :speed="cl.speed" :battery="cl.battery"/>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import ComSetParam from './ComSetParam.vue'
export default{
    name:'CardSetParam',
    components:{
        ComSetParam,
    },
    data(){
        return{
            car_list:[
                {name:'AGV 1',speed:'2 m/s',battery:'25 %'},
                {name:'AGV 2',speed:'0 m/s',battery:'0 %'},
                {name:'AGV 3',speed:'0 m/s',battery:'0 %'},
            ]
        }
    }
}
</script>

<style>
.card-set-param{
    height: 130%;
}
.agv-set-param{
    height:30%;
    background-color:#13151D ;
}
.contant-param{
    height:100%;

}

</style>