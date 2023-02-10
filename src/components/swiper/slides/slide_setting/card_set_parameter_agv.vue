<template>
    <div class="card mb-4">
        <div class="tranbackground">
        <span></span>
        <span></span>
        <span></span>
        <span></span>
    </div>
        <div class="card-body">
            <div class="row px-2">
                <div class="col-9 d-flex justify-content-start px-0">
                    <div class="d-flex h5 mx-0 mt-1">
                        SET PARAMETER AGV
                    </div>
                    <div class="d-flex">
                        <div class="btn  text text-warning mx-3">
                            CONFIRM STANDBY AGV 1
                        </div>
                    </div>
                </div>
                <div class="col-3 d-flex px-3 align-self-center">
                    OPTION
                </div>
            </div>

            <div class="row mt-0">
                <div class="col-9">
                    <div class="agv-set-param">
                        <com-set-param :getParamAgv="getSetParamAgv" :getAgvSpeed="getAgvSpeed" :getAgvBatt="getAgvBatt" />
                    </div>
                    <div class="agv-set-param">
                        <com-set-param :getParamAgv="getSetParamAgv" :getAgvSpeed="getAgvSpeed" :getAgvBatt="getAgvBatt" />
                    </div>
                    <div class="agv-set-param">
                        <com-set-param :getParamAgv="getSetParamAgv" :getAgvSpeed="getAgvSpeed" :getAgvBatt="getAgvBatt" />
                    </div>
                </div>
                <div class="col-3  bg-dark  card  d-flex">
                    <div class="d-flex flex-column  card-option-content ">
                        <div class="text-primary text-center ">
                            <small>WORNNING REPORT</small>
                        </div>
                       <div class="row ">
                        <div class="app-option mt-5">
                            <div class="container card-option-content ">
                                <div class="row option-item-row">
                                    <div class="col-sm-6 d-flex flex-column justify-content-center">
                                        <div >
                                            <img class="img-social"
                                                src="https://static.newmobilelife.com/wp-content/uploads/2014/10/LineforiPad00-210x210.png"
                                                alt="">
                                        </div>
                                    </div>
                                    <div class="col-sm-6 d-flex flex-column justify-content-center text-center">
                                        <div class="text-warning mb-2"><small>LINE APP</small> </div>
                                        <div class="mb-2 mx-auto"><button-toggle :buttValue="lineOption" @click="lineOption = !lineOption"/></div>
                                        <div class="text-warning"><small>CONFIRM</small> </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div class="app-option mt-5">
                            <div class="container card-option-content">
                                <div class="row option-item-row">
                                    <div class="col-sm-6 d-flex flex-column justify-content-center">
                                        <div >
                                            <img class="img-social"
                                                src="https://logos-download.com/wp-content/uploads/2016/05/Gmail_logo_icon.png"
                                                alt="">
                                        </div>
                                    </div>
                                    <div class="col-sm-6 d-flex flex-column justify-content-center text-center">
                                        <div class="text-warning mb-2"><small>GMAIL</small> </div>
                                        <div class="mb-2 mx-auto"><button-toggle :buttValue="gmailOption" @click="gmailOption = !gmailOption"/></div>
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
    </div>
    <!-- <span>{{getOption}}</span> -->
</template>

<script>
import ButtonToggle from '@/components/button/buttonToggle.vue';
// import { click } from 'dom7';
import ComSetParam from './ComSetParam.vue';

export default {
    components: {
        ButtonToggle,
        ComSetParam,
    },
    props:[
        'getSetParamAgv',
        'getAgvSpeed',
        'getAgvBatt',
        'getOption'
    ]
    ,
    data() {
        return {
            lineOption:'',
            gmailOption:'',
            tmpOption:''
        }
    },
    created(){
        setInterval(()=>{
            if(JSON.stringify(this.tmpOption) !== JSON.stringify(this.getOption)){
                this.tmpOption = this.getOption
                this.setOptionData()
            }
        },3000)
    },
    methods:{
        setOptionData(){
            this.lineOption = this.tmpOption.line_app_setting
            this.gamilPotion = this.tmpOption.gmail_setting
        },
    }
}
</script>

<style lang="scss" scoped>
.img-social {
    width: 100%;
    height: 96%;
    
    border-radius: 20px;
}
</style>