<template>
    <div class="container">
        <div class="row bg-dark mb-2">
            <div class="col-md-2 ">
                <div class="d-flex felx-column justify-content-center">
                    <img class="img-agv" src="https://purepng.com/public/uploads/large/purepng.com-gray-bmw-m4-gts-carcarbmwvehicletransport-961524662033wmsm1.png" alt="">
                </div>
                <div class="text-center">
                    <span>agv-1</span>
                </div>
            </div>
            <div class="col-sm-10 ">
                <div class="row p-0 row-function mt-1s mt-4">
                    <div class="col-sm-4 px-0">
                        <table class="table table-sm table-borderless table-setparam text-warning px-0 table-resopns">
                            <tbody>
                                <tr>
                                    <td class="speed-max px-0 text-center">MAX SPEED</td>
                                    <td class="td-val text-primary text-center" :v-text="speed">
                                        <div class="param-val bg-dark">2 m/s</div>
                                    </td>
                                </tr>
                                <tr>
                                    <td  class="speed-max px-0 text-center">MAN BATTERY</td>
                                    <td class="td-val text-primary text-center" :v-text="battery">
                                        <div class="param-val bg-dark">20 %</div>
                                    </td>
                                </tr>
                            </tbody>
                        </table>
                        
                    </div>
                    <div class="col-sm-5 px-0">
                        <table class="table table-sm table-borderless table-setparam text-warning px-0">
                            <tbody>
                                <tr>
                                    <td class="px-0"><button-toggle/></td>
                                    <td class="px-0 text-center">FUNCTION CAMERA</td>
                                </tr>
                                <tr>
                                    <td class="p-0"><button-toggle/></td>
                                    <td class="p-0 text-center">FUNCTION LIDAR</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                    <div class="col-sm-3 px-0">
                        <table class="table table-sm table-borderless table-setparam text-warning px-0">
                            <tbody>
                                <tr>
                                    <td class="px-0"><button-toggle/></td>
                                    <td class="px-0 text-center">AUTO MODE</td>
                                </tr>
                                <tr>
                                    <td class="px-0"><button-toggle/></td>
                                    <td class="px-0 text-center">NETWORK</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>
                
            </div>
        </div>
    </div>
</template>

<script>
import ButtonToggle from '@/components/button/buttonToggle.vue'
export default{
    name:'ComSetParam',
    components:{
        ButtonToggle,
    },
    props:[
        'name',
        'speed',
        'battery'
    ],
}
</script>

<style>

</style>
    