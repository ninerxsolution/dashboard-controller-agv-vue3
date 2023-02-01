<template>
    <div class="card">
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
                        <circle-progress :percent="15" :unit="kg / hr" :show-percent="false" :size="100"
                            :fill-color="'#89b8e0'" class="dummy-meter" />
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
                        <circle-progress :percent="80" :unit="kg / hr" :show-percent="false" :size="100"
                            :fill-color="'#ffd000'" class="dummy-meter" />
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
                        <circle-progress :percent="80" :unit="kg / hr" :show-percent="false" :size="100"
                            :fill-color="'#00a2ff'" class="dummy-meter" />
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
                        <circle-progress :percent="45" :unit="kg / hr" :show-percent="false" :size="100"
                            :fill-color="'#4cff45'" class="dummy-meter" />
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
import CircleProgress from "vue3-circle-progress";
export default {
    components: {
        CircleProgress,

    }
}
</script>

<style lang="scss" scoped>

</style>