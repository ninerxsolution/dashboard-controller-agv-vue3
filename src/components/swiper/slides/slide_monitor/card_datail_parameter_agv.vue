<template>
    <div class="card">
        <div class="tranbackground">
        <span></span>
        <span></span>
        <span></span>
        <span></span>
    </div>
        <div class="card-body">
            <div class="col-12 d-flex justify-content-between">
                <h5 class="d-flex">
                    DETAIL PARAMETER AGV
                </h5>
                <div class="text-success align-self-center">
                    <div>
                        Enegy (kWh) : 54376
                    </div>
                </div>
                <div class="text-danger align-self-center">
                    <div>
                        CO2 (kg) : 3456
                    </div>
                </div>
                
                <div class="progress align-self-center" style="width: 10%">
                    <div class="progress-bar bg-success" role="progressbar" style="width: 66%" aria-valuenow="100"
                        aria-valuemin="0" aria-valuemax="100">
                        81.2%
                    </div>
                </div>
                <div class="dropdown">
                    <button class="btn btn-light dropdown-toggle" type="button" id="dropdownMenuButton1"
                        data-toggle="dropdown" aria-haspopup="true" aria-expanded="false"> AGV 1
                    </button>
                    <div class="dropdown-menu" aria-labelledby="dropdownMenuButton1">
                        <h6 class="dropdown-header">AGV</h6>
                        <a class="dropdown-item" href="#">AGV 1</a>
                        <a class="dropdown-item" href="#">AGV 2</a>
                        <a class="dropdown-item" href="#">AGV 3</a>
                        <a class="dropdown-item" href="#">AGV 4</a>
                    </div>
                </div>
            </div>
            <div class="row mt-3">
                <div class="col-3">
                    <div class="justify-content-between">
                        <CurrentMeter :getSpeedCurrent="speedCurrent"/>
                    </div>
                    <div class="pt-1 text-muted text-center">
                        <div>
                            Current speed
                        </div>
                    </div>
                    <div class="h3 mb-0 text-center">
                        0.5 m/s
                    </div>
                    <div class="text-primary text-center">
                        <div>
                            Running
                        </div>
                    </div>
                </div>
                <div class="col-3">
                    <div class="justify-content-between">
                        <ElectricalValtageMeter :getValtageEverage="valtageEverage"/>
                    </div>
                    <div class="pt-1 text-muted text-center">
                        <div>
                            Voltage average
                        </div>
                    </div>
                    <div class="h3 mb-0 text-center">
                        50.6 V
                    </div>
                    <div class="text-warning text-center">
                        <div>
                            Standby
                        </div>
                    </div>
                </div>
                <div class="col-3">
                    <div class="justify-content-between">
                        <CurrentNow :getCurrentNow="currentNow" />
                    </div>
                    <div class="pt-1 text-muted text-center">
                        <div>
                            Current now
                        </div>
                    </div>
                    <div class="h3 mb-0 text-center">
                        49.9 A
                    </div>
                    <div class="text-primary text-center">
                        <div>
                            Ready
                        </div>
                    </div>
                </div>
                <div class="col-3">
                    <div class="justify-content-between">
                        <PowerNow :getPowerNow="powerNow"/>
                    </div>
                    <div class="pt-1 text-muted text-center">
                        <div>
                            Power now
                        </div>
                    </div>
                    <div class="h3 mb-0 text-center">
                        2.5 kW
                    </div>
                    <div class="text-success text-center">
                        <div>
                            Using
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import "vue3-circle-progress/dist/circle-progress.css";
// import CircleProgress from "vue3-circle-progress";
import PowerNow from "@/components/speedOmeter/powerNow.vue";
import CurrentMeter from "@/components/speedOmeter/currentMeter.vue"
import ElectricalValtageMeter from "@/components/speedOmeter/electricalValtageMeter.vue";
import CurrentNow from "@/components/speedOmeter/currentNowMeter.vue";
CurrentMeter
export default {
    components: {
        // CircleProgress,
        PowerNow,
        CurrentMeter,
        ElectricalValtageMeter,
        CurrentNow
    },
    data(){
        return{
            powerNow:2.5,
            speedCurrent:0.5,
            valtageEverage:50.6,
            currentNow:49.9
        }
    }
}
</script>

<style lang="scss" scoped>

</style>