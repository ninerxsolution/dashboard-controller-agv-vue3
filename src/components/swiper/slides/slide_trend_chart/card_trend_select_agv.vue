<template>
    <div class="card mb-4">
        <div class="card-body">
            <div class="col-12 d-flex justify-content-between px-0">
                <div class="d-flex h5 mx-0 mt-1">
                    TREND SELECT AGV
                </div>
                <div class="d-flex">
                    <div class="input-group-prepend">
                        <button class="btn btn-dark dropdown-toggle text-warning" type="button" data-toggle="dropdown"
                            aria-haspopup="true" aria-expanded="false">
                            AGV1
                        </button>
                        <div class="dropdown-menu">
                            <a class="dropdown-item" href="#">Action</a>
                            <a class="dropdown-item" href="#">Another action</a>
                            <a class="dropdown-item" href="#">Something else here</a>
                            <div role="separator" class="dropdown-divider"></div>
                            <a class="dropdown-item" href="#">Separated link</a>
                        </div>
                    </div>
                </div>
                <div class="d-flex">
                    <button class="btn btn-dark mx-3 align-self-center">Date-time</button>
                    <span class="text-warning mx-0 align-self-center">STATUS: </span>
                    <span class="text-success mx-4 align-self-center">Online</span>
                </div>
            </div>
            <div class="row">
                <div class="col-9 mt-2">
                    <div class="row" style="height:120px;">
                        <SpeedChart />
                    </div>
                    <div class="row" style="height:120px;">
                        <PowerChart />
                    </div>
                    <div class="row" style="height:120px;">
                        <CurrentChart />
                    </div>
                </div>
                <div class="col-3">
                    <div class="scrollbar scrollbar-success mb-3 bg-dark" style="height:90%;">
                        <div class="col">
                            <div class="scrollbar scrollbar-success my-3 bg-dark" style="height:90%;">
                                <table class="table table-sm table-borderless mt-2">
                                    <tbody>
                                        <tr v-for="tsa in trend_select_agv" :key="tsa">
                                            <!-- <td class="text-warning p-0">·</td> -->
                                            <td scope="row"
                                                class="text-left text-warning d-flex justify-content-between">
                                                <ul class="mb-2">
                                                    <li>
                                                        {{ tsa.name }}
                                                    </li>
                                                </ul>
                                                <div class="form-check p-0 m-0">
                                                    <input type="checkbox" class="form-check-input my-0"
                                                        :checked="tsa.check">
                                                </div>
                                            </td>
                                        </tr>
                                    </tbody>
                                </table>
                            </div>

                        </div>
                    </div>
                    <div class="col-12 d-flex justify-content-between p-0 m-0">
                        <button class="btn btn-sm btn-warning text-dark">SELECT ALL</button>
                        <button class="btn btn-sm btn-primary text-dark">EXPORT EXCEL</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import SpeedChart from '@/components/Chart/SpeedChart.vue';
import PowerChart from '@/components/Chart/PowerChart.vue';
import CurrentChart from '@/components/Chart/CurrentChart.vue';
// import LineChart from '@/components/Chart/LineChart.vue'

export default {
    components: {
        SpeedChart,
        PowerChart,
        CurrentChart,
        // LineChart,       
    },
    data() {
        return {
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

            ]
        }
    }
}
</script>

<style lang="scss" scoped>

</style>