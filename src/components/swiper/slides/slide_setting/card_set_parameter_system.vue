<template>
    <div class="card">
    <div class="tranbackground">
        <span></span>
        <span></span>
        <span></span>
        <span></span>
    </div>
        <div class="card-body">
            <h5 class="d-flex">
                SET PARAMETER SYSTEM
            </h5>
            <div class="col-12">
                <div class="scrollbar scrollbar-setting-setpara" style="height:10rem;">
                    <table class="table table-sm table-borderless force-overflow-setting mt-2">
                        <tbody>
                            <tr>
                                <td scope="row" class="text-left text-warning">
                                    <ul class="m-auto">
                                        <li >
                                            <span class="text-sm">AGV</span>
                                        </li>
                                    </ul>
                                </td>
                                <td>
                                    <input :class="classInput" type="text" name="" id="" v-model="agv_setting">
                                </td>
                                <td scope="row" class="text-left text-warning">
                                    <ul class="m-auto">
                                        <li >
                                            <span>PRODUCTION</span>
                                        </li>
                                    </ul>
                                </td>
                                <td >
                                    <input :class="classInput" type="text" name="" id="" v-model="product_setting">
                                </td>
                            </tr>
                            <tr>
                                <td scope="row" class="text-left text-warning">
                                    <ul class="m-auto">
                                        <li >
                                             <span>MAX SPEED</span>
                                        </li>
                                    </ul>
                                </td>
                                <td>
                                    <input :class="classInput" type="text" name="" id="" v-model="max_speed_setting">
                                </td>
                                <td scope="row" class="text-left text-warning">
                                    <ul class="m-auto">
                                        <li >
                                            MAX LOAD
                                        </li>
                                    </ul>
                                </td>
                                <td>
                                    <input :class="classInput" type="text" name="" id="" v-model="max_load_setting">
                                </td>
                            </tr>
                            <tr>
                                <td scope="row" class="text-left text-warning">
                                    <ul class="m-auto">
                                        <li >
                                            CYCKE TIME
                                        </li>
                                    </ul>
                                </td>
                                <td>
                                    <input :class="classInput" type="text" name="" id="" v-model="cycle_time_setting">
                                </td>
                                <td scope="row" class="text-left text-warning">
                                    <ul class="m-auto">
                                        <li >
                                            LOOP CYCLE
                                        </li>
                                    </ul>
                                </td>
                                <td>
                                    <input :class="classInput" type="text" name="" id="" v-model="loop_cycle_setting">
                                </td>
                            </tr>
                            <tr>
                                <td scope="row" class="text-left text-warning">
                                    <ul class="m-auto">
                                        <li >
                                            DISTANCE
                                        </li>
                                    </ul>
                                </td>
                                <td>
                                    <input :class="classInput" type="text" name="" id="" v-model="distance_setting">
                                </td>
                                <td scope="row" class="text-left text-warning">
                                    <ul class="m-auto">
                                        <li >
                                            CAMERA
                                        </li>
                                    </ul>
                                </td>
                                <td>
                                    <input :class="classInput" type="button" name="" id="" v-model="camera_setting" @click="(this.camera_setting == 'YES')? camera_setting = 'NO':camera_setting = 'YES'">
                                </td>
                            </tr>
                            <tr>
                                <td scope="row" class="text-left text-warning">
                                    <ul class="m-auto">
                                        <li >
                                            BATTERY TIME
                                        </li>
                                    </ul>
                                </td>
                                <td>
                                    <input :class="classInput" type="text" name="" id="" v-model="batter_time_setting">
                                </td>
                                <td scope="row" class="text-left text-warning">
                                    <ul class="m-auto">
                                        <li >
                                            LIDAR
                                        </li>
                                    </ul>
                                </td>
                                <td>
                                    <input :class="classInput" type="button" name="" id="" v-model="lidar_setting" @click="(this.lidar_setting == 'YES')? lidar_setting = 'NO':lidar_setting ='YES'">
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
            <!-- <span>{{ tmpJson }}</span> -->
        </div>
    </div>
</template>

<script>
export default {
    props:{
        getSetParamSys:{
            type:Object
        }
    },
    data() {
        return {
            intervalTime:3000,
            classInput:"form-control form-control-sm input-param text-center text-primary",
            agv_setting:'default',
            product_setting:'default',
            max_speed_setting:'default',
            max_load_setting:'default',
            cycle_time_setting:'default',
            loop_cycle_setting:'default',
            distance_setting:'default',
            camera_setting:'default',
            batter_time_setting:'default',
            lidar_setting:'default',
            tmpJson:''
        }
    },
    created(){
        setInterval(()=>{
            if(JSON.stringify(this.tmpJson) !== JSON.stringify(this.getSetParamSys))
            { 
                this.tmpJson = this.getSetParamSys
                this.setValue()
            }
        },3000);
    },
    methods:{
        setValue(){
            this.agv_setting = this.tmpJson.agv_setting.value || 0
            this.product_setting = this.tmpJson.product_setting.value || 0
            this.max_speed_setting = this.tmpJson.max_speed_setting.value || 0
            this.max_load_setting = this.tmpJson.max_load_setting.value || 0
            this.cycle_time_setting = this.tmpJson.cycle_time_setting.value || 0
            // this.loop_cycle_setting = this.tmpJson.loop_cycle_setting.value || 0
            this.distance_setting = this.tmpJson.distance_setting.value || 0
            this.camera_setting = this.tmpJson.camera_setting.label || 0
            this.batter_time_setting = this.tmpJson.batter_time_setting.value || 0
            this.lidar_setting = this.tmpJson.lidar_setting.label || 0
        },
        cameraButtonClick(){
            (this.camera_setting == "YES") ? "NO":"YES"
        },
        lidarButtonClick(){

        }
    }
}
</script>

<style  scoped>
.input-param{
    width: 100%;
}
</style>