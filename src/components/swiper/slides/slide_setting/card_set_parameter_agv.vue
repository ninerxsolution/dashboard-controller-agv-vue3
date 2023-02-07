<template>
    <div class="card mb-4">
        <div class="card-body">
            <div class="row px-2">
                <div class="col-9 d-flex justify-content-start px-0">
                    <div class="d-flex h5 mx-0 mt-1">
                        SET PARAMETER AGV
                    </div>
                    <div class="d-flex">
                        <div class="btn btn-dark text text-warning mx-3">
                            CONFIRM STANDBY AGV 1
                        </div>
                    </div>
                </div>
                <div class="col-3 d-flex px-3 align-self-center">
                    OPTION
                </div>
            </div>

            <div class="row mt-2">
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
                <div class="col-3 bg-dark d-flex">
                    <div class="d-flex flex-column  card-option-content">
                        <div class="text-primary text-center ">
                            <small>WORNNING REPORT</small>
                        </div>
                        <div class="app-option mt-2">
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
                                        <div class="mb-2 mx-auto"><button-toggle :buttValue="lineOption" /></div>
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
                                        <div class="mb-2 mx-auto"><button-toggle :buttValue="gmailOption" /></div>
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
    <!-- <span>{{getOption}}</span> -->
</template>

<script>
import ButtonToggle from '@/components/button/buttonToggle.vue';
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
            setParamAgv:'',
            lineOption:'',
            gmailOption:''
        }
    },
    created(){
        setInterval(()=>{
            this.setParamAgv = this.getSetParamAgv
            this.lineOption = this.getOption.line_app_setting
            this.gamilPotion = this.getOption.gmail_setting
        },3000)
    }
}
</script>

<style lang="scss" scoped>
.img-social {
    width: 100%;
    
    border-radius: 20px;
}
</style>