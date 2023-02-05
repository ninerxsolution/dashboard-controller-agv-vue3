<template>
    <div class="container-fluid content bg-dark pt-3">
        <div class="row">
            <div class="col-md-5 grid-margin stretch-card">
                <CardConfirmSystem :getJson="confirmSys" />
            </div>
            <div class="col-md-7 grid-margin stretch-card">
                <CardSetParamsSys :getSetParamSys="setParamSys"/>
            </div>
        </div>
        <div class="row">
            <div class="col-12 grid-margin">
                <CardSetParamsAgv :getSetParamAgv="setParamAgv" :getAgvSpeed="agvSpeed" :getAgvBatt="agvBatt" :getOption="setOption"/>
            </div>
        </div>
        <!-- <span>{{ setOption }}</span> -->
    </div>
</template>

<script>
import "vue3-circle-progress/dist/circle-progress.css";
import CardConfirmSystem from './slide_setting/card_confirm_running_system.vue';
import CardSetParamsSys from './slide_setting/card_set_parameter_system.vue';
import CardSetParamsAgv from './slide_setting/card_set_parameter_agv.vue';
export default {
    name: 'App',
    components: {
        // buttonToggle,
        
        CardConfirmSystem,
        CardSetParamsSys,
        CardSetParamsAgv
    },
    props:{
        getJson:{
            type:Object
        }
    },
    data() {
        return {
            confirmSys:undefined,
            setParamSys:undefined,
            setParamAgv:undefined,
            setOption:undefined,
            agvSpeed:undefined,
            agvBatt:undefined,
            detail_export: [
                { name: 'ENERGY AGV TOTAL', check: true },
                { name: 'PRODUCTION TOTAL', check: true },
                { name: 'CYCLE TRANSPORT', check: false },
                { name: 'POWER AGV TOTAL', check: true },
                { name: 'TEST', check: false },
                { name: 'TEST', check: false },
                { name: 'TEST', check: true },
                { name: 'TEST', check: false },
                { name: 'TEST', check: false },
            ],
            trend_select_agv: [
                { name: 'SPEED AGV 1', check: true },
                { name: 'SPEED AGV 2', check: false },
                { name: 'SPEED AGV 3', check: false },
                { name: 'POWER AGV 1', check: true },
                { name: 'POWER AGV 2', check: false },
                { name: 'POWER AGV 3', check: false },
                { name: 'CURR AGV 1', check: true },
                { name: 'CURR AGV 2', check: false },
                { name: 'CURR AGV 3', check: false },

            ],
            set_param_sys: [
                { name_left: 'AGV', val_left: '1', name_right: 'PRODUCTION', val_right: '400 ton.' },
                { name_left: 'MAX SPEED', val_left: '2 m/s', name_right: 'MAX LOAD', val_right: '4 ton.' },
                { name_left: 'CYCLE TIME', val_left: '10 min.', name_right: 'LOOP CYCLE', val_right: '100 cyc.' },
                { name_left: 'DISTANCE', val_left: '500 m', name_right: 'CAMERA', val_right: 'YES' },
                { name_left: 'BATTERY TIME', val_left: '8 hour', name_right: 'LIDAR', val_right: 'YES' },
                { name_left: 'test', val_left: '0', name_right: 'test', val_right: '0' },
                { name_left: 'test', val_left: '0', name_right: 'test', val_right: '0' },
                { name_left: 'test', val_left: '0', name_right: 'test', val_right: '0' },
            ],
            car_list: [
                { name: 'AGV 1', speed: '2 m/s', battery: '25 %' },
                { name: 'AGV 2', speed: '0 m/s', battery: '0 %' },
                { name: 'AGV 3', speed: '0 m/s', battery: '0 %' },
            ]
        }
    },
    created(){
        setInterval(() =>{
            // let set_Param_Agv = this.getJson.return.data.pages.page3.SET_PARAMETER_AGV 
            this.confirmSys = this.getJson.return.data.pages.page3.CONFIRM_RUNNING_SYSTEM.status_agv
            this.setParamSys = this.getJson.return.data.pages.page3.SET_PARAMETERS_SYSTEM
            this.setParamAgv = this.getJson.return.data.pages.page3.SET_PARAMETER_AGV
            this.setOption = this.getJson.return.data.pages.page3.OPTION
            this.agvBatt = this.getJson.return.data.pages.page1.BATTERY_CAPACITY.value
            this.agvSpeed = this.getJson.return.data.pages.page1.AGV_RUNNING_NOW.speed_max.value
        },1000)
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

/* scrollbar */
.scrollbar-top-left {
    /* margin-left: 30px; */
    /* float: left; */
    height: 8rem;
    /* width: 65px; */
    /* background: #fff; */
    overflow-y: scroll;
    margin-bottom: 25px;
}


.scrollbar-success::-webkit-scrollbar {
    width: 10px;
    background-color: #000000;
}

.scrollbar-success::-webkit-scrollbar-thumb {
    border-radius: 20px;
    -webkit-box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.1);
    background-color: #ffffff;
}

.start-stop-button-area {
    height: 120px;
}

.start-big-button {
    width: 90px;
    height: 90px;
    margin-top: auto;
    margin-bottom: auto;
    border: solid 4px gray;
    border-radius: 50%;
    text-align: center;
    padding-top: 1.25rem;
}

.stop-big-button {
    width: 90px;
    height: 90px;
    margin-top: auto;
    margin-bottom: auto;
    border: solid 4px gray;
    border-radius: 50%;
    text-align: center;
    padding-top: 1.25rem;
}

/* .force-overflow-top-left {
    min-height: 450px;
}

.scrollbar-success {
    scrollbar-color: #4285F4 #F5F5F5;
}

.btn {
    width: 100%;
    height: 100%;
}

.td {
    padding: unset !important;
} */
</style>