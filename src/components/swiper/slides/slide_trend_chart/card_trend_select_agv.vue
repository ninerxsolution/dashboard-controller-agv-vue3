<template>
    <div class="card mb-4">
        <div class="tranbackground">
            <span></span>
            <span></span>
            <span></span>
            <span></span>
        </div>
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
                <div class="d-flex text-dark">
                    <datepicker :value="date" name="uniquename" v-model="date" />
                </div>
                <div class="d-flex">
                    <!-- {{ date }} -->
                    <button class="btn btn-light" @click="splitDate()">
                        Get date split
                    </button>
                    {{ dateUse }} / {{ arr }} / {{ id }}
                </div>
                <div class="d-flex">
                    <button class="btn btn-dark mx-3 align-self-center">Date-time</button>
                    <span class="text-warning mx-0 align-self-center">STATUS: </span>
                    <span class="text-success mx-4 align-self-center">Online</span>
                </div>
            </div>
            <div class="row">
                <div class="col-12 mt-2">
                    <div class="row" style="height:120px;">
                        <LineChart :chartval="speedData" />
                    </div>
                    <div class="row" style="height:120px;">
                        <LineChart :chartval="powerData" />
                    </div>
                    <div class="row" style="height:120px;">
                        <LineChart :chartval="currentData" />
                    </div>
                </div>
                <!-- <div class="col-3">
                    <div class="scrollbar scrollbar-success my-2 bg-dark" style="height:90%;">
                        <div class="col">
                            <div class="scrollbar scrollbar-success my-3 bg-dark" style="height:90%;">
                                <table class="table table-sm table-borderless mt-2">
                                    <tbody>
                                        <tr v-for="tsa in trend_select_agv" :key="tsa">
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
                    <div class="col-12 d-flex justify-content-around p-0 m-0">
                        <button class="btn btn-sm btn-warning text-dark">SELECT ALL</button>
                        <button class="btn btn-sm btn-primary text-dark">EXPORT EXCEL</button>
                    </div>
                </div> -->
            </div>
        </div>
    </div>
</template>

<script>
// import SpeedChart from '@/components/Chart/SpeedChart.vue';
// import PowerChart from '@/components/Chart/PowerChart.vue';
// import CurrentChart from '@/components/Chart/CurrentChart.vue';
import LineChart from '@/components/Chart/LineChart.vue'
import Datepicker from 'vuejs3-datepicker';

export default {
    components: {
        // SpeedChart,
        // PowerChart,
        // CurrentChart,
        LineChart,
        Datepicker
    },
    props: ['powerChart', 'speedchart', 'currentChart',],
    data() {
        return {
            date: new Date(),
            id: 'Default',
            arr: 'Default',
            dateUse: 'Default',
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
            // dataset speed          
            baseSpeedData: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
            speedData: {
                labels: ['12 hr', '11 hr', '10 hr', '9 hr', '8 hr', '7 hr', '6 hr', '5 hr', '4 hr', '3 hr', '2 hr', '1 hr', '12 hr', '11 hr', '10 hr', '9 hr', '8 hr', '7 hr', '6 hr', '5 hr', '4 hr', '3 hr', '2 hr', '1 hr',],
                datasets: [
                    {
                        label: 'Speed',
                        borderColor: '#0090e7',
                        backgroundColor: '#0090e7',
                        data: [],
                        lineTension: 0.4,
                        borderWidth: 2.0,
                        pointRadius: 0,
                    }
                ],
            },
            speedDataFirst: {
                labels: ['12 hr', '11 hr', '10 hr', '9 hr', '8 hr', '7 hr', '6 hr', '5 hr', '4 hr', '3 hr', '2 hr', '1 hr', '12 hr', '11 hr', '10 hr', '9 hr', '8 hr', '7 hr', '6 hr', '5 hr', '4 hr', '3 hr', '2 hr', '1 hr',],
                datasets: [
                    {
                        label: 'Speed',
                        borderColor: '#0090e7',
                        backgroundColor: '#0090e7',
                        data: [],
                        lineTension: 0.4,
                        borderWidth: 2.0,
                        pointRadius: 0,
                    }
                ],
            },
            speedDataSecond: {
                labels: ['12 hr', '11 hr', '10 hr', '9 hr', '8 hr', '7 hr', '6 hr', '5 hr', '4 hr', '3 hr', '2 hr', '1 hr', '12 hr', '11 hr', '10 hr', '9 hr', '8 hr', '7 hr', '6 hr', '5 hr', '4 hr', '3 hr', '2 hr', '1 hr',],
                datasets: [
                    {
                        label: 'Speed',
                        borderColor: '#0090e7',
                        backgroundColor: '#0090e7',
                        data: [],
                        lineTension: 0.4,
                        borderWidth: 2.0,
                        pointRadius: 0,
                    }
                ],
            },
            // end dataset speed 
            // dataset power          
            basePowerData: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
            powerData: {
                labels: ['12 hr', '11 hr', '10 hr', '9 hr', '8 hr', '7 hr', '6 hr', '5 hr', '4 hr', '3 hr', '2 hr', '1 hr', '12 hr', '11 hr', '10 hr', '9 hr', '8 hr', '7 hr', '6 hr', '5 hr', '4 hr', '3 hr', '2 hr', '1 hr',],
                datasets: [
                    {
                        label: 'Power',
                        borderColor: '#ffab00',
                        backgroundColor: '#ffab00',
                        data: [],
                        lineTension: 0.4,
                        borderWidth: 2.0,
                        pointRadius: 0,
                    }
                ],
            },
            powerDataFirst: {
                labels: ['12 hr', '11 hr', '10 hr', '9 hr', '8 hr', '7 hr', '6 hr', '5 hr', '4 hr', '3 hr', '2 hr', '1 hr', '12 hr', '11 hr', '10 hr', '9 hr', '8 hr', '7 hr', '6 hr', '5 hr', '4 hr', '3 hr', '2 hr', '1 hr',],
                datasets: [
                    {
                        label: 'Power',
                        borderColor: '#ffab00',
                        backgroundColor: '#ffab00',
                        data: [],
                        lineTension: 0.4,
                        borderWidth: 2.0,
                        pointRadius: 0,
                    }
                ],
            },
            powerDataSecond: {
                labels: ['12 hr', '11 hr', '10 hr', '9 hr', '8 hr', '7 hr', '6 hr', '5 hr', '4 hr', '3 hr', '2 hr', '1 hr', '12 hr', '11 hr', '10 hr', '9 hr', '8 hr', '7 hr', '6 hr', '5 hr', '4 hr', '3 hr', '2 hr', '1 hr',],
                datasets: [
                    {
                        label: 'Power',
                        borderColor: '#ffab00',
                        backgroundColor: '#ffab00',
                        data: [],
                        lineTension: 0.4,
                        borderWidth: 2.0,
                        pointRadius: 0,
                    }
                ],
            },
            // end dataset power 
            // dataset current          
            baseCurrentData: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
            currentData: {
                labels: ['12 hr', '11 hr', '10 hr', '9 hr', '8 hr', '7 hr', '6 hr', '5 hr', '4 hr', '3 hr', '2 hr', '1 hr', '12 hr', '11 hr', '10 hr', '9 hr', '8 hr', '7 hr', '6 hr', '5 hr', '4 hr', '3 hr', '2 hr', '1 hr',],
                datasets: [
                    {
                        label: 'Current',
                        borderColor: '#00d25b',
                        backgroundColor: '#00d25b',
                        data: [],
                        lineTension: 0.4,
                        borderWidth: 2.0,
                        pointRadius: 0,
                    }
                ],
            },
            currentDataFirst: {
                labels: ['12 hr', '11 hr', '10 hr', '9 hr', '8 hr', '7 hr', '6 hr', '5 hr', '4 hr', '3 hr', '2 hr', '1 hr', '12 hr', '11 hr', '10 hr', '9 hr', '8 hr', '7 hr', '6 hr', '5 hr', '4 hr', '3 hr', '2 hr', '1 hr',],
                datasets: [
                    {
                        label: 'Current',
                        borderColor: '#00d25b',
                        backgroundColor: '#00d25b',
                        data: [],
                        lineTension: 0.4,
                        borderWidth: 2.0,
                        pointRadius: 0,
                    }
                ],
            },
            currentDataSecond: {
                labels: ['12 hr', '11 hr', '10 hr', '9 hr', '8 hr', '7 hr', '6 hr', '5 hr', '4 hr', '3 hr', '2 hr', '1 hr', '12 hr', '11 hr', '10 hr', '9 hr', '8 hr', '7 hr', '6 hr', '5 hr', '4 hr', '3 hr', '2 hr', '1 hr',],
                datasets: [
                    {
                        label: 'Current',
                        borderColor: '#00d25b',
                        backgroundColor: '#00d25b',
                        data: [],
                        lineTension: 0.4,
                        borderWidth: 2.0,
                        pointRadius: 0,
                    }
                ],
            },
            // end dataset current 
        }
    }, created() {

        setInterval(() => {
            setTimeout(() => {
                this.updateCurrentOne()
                this.updatepowerOne()
                this.updatespeedOne()
            }, 3000)
            this.updateCurrentTwo()
            this.updatepowerTwo()
            this.updatespeedTwo()
        }, 3000)
    },
    methods: {
        splitDate() {
            this.dateUse = this.date
            // this.id = "GUN-ANNA-MATTRA"
            this.id = this.date.toString()
            this.arr = this.id.split(" ");
            this.dateUse = 'Clicked Two'
            this.dateUse = (this.arr[1]+" "+this.arr[2]+" "+this.arr[3])
        },
        //speed 
        //for speed dataset one
        updatespeedOne() {
            try {
                this.setupspeedDataOne()
                this.speedDataFirst.datasets[0].data = this.baseSpeedData
                this.speedData = this.speedDataFirst
            } catch (error) {
                console.error(error)
            }
        },
        setupspeedDataOne() {
            this.baseSpeedData.shift()
            this.baseSpeedData.push(this.speedchart)
        },
        //end speed dataset one
        //------------------------------------------
        //start speed dataset two
        updatespeedTwo() {
            try {
                this.setupspeedDataTwo()
                this.speedDataSecond.datasets[0].data = this.baseSpeedData
                this.speedData = this.speedDataSecond
            } catch (error) {
                console.error(error)
            }
        },
        setupspeedDataTwo() {
            this.baseSpeedData.shift()
            this.baseSpeedData.push(this.speedchart)
        },
        //end speed dataset two 
        //end speed

        //-------------------------------------------------------------------------------------------
        //power 
        //for power dataset one
        updatepowerOne() {
            try {
                this.setuppowerDataOne()
                this.powerDataFirst.datasets[0].data = this.basePowerData
                this.powerData = this.powerDataFirst
            } catch (error) {
                console.error(error)
            }
        },
        setuppowerDataOne() {
            this.basePowerData.shift()
            this.basePowerData.push(this.powerChart)
        },
        //end power dataset one
        //------------------------------------------
        //start power dataset two
        updatepowerTwo() {
            try {
                this.setuppowerDataTwo()
                this.powerDataSecond.datasets[0].data = this.basePowerData
                this.powerData = this.powerDataSecond
            } catch (error) {
                console.error(error)
            }
        },
        setuppowerDataTwo() {
            this.basePowerData.shift()
            this.basePowerData.push(this.powerChart)
        },
        //end power dataset two 
        //end power

        //-------------------------------------------------------------------------------------------

        //current 
        //for current dataset one
        updateCurrentOne() {
            try {
                this.setupCurrentDataOne()
                this.currentDataFirst.datasets[0].data = this.baseCurrentData
                this.currentData = this.currentDataFirst
            } catch (error) {
                console.error(error)
            }
        },
        setupCurrentDataOne() {
            this.baseCurrentData.shift()
            this.baseCurrentData.push(this.currentChart)
        },
        //end current dataset one
        //------------------------------------------
        //start current dataset two
        updateCurrentTwo() {
            try {
                this.setupCurrentDataTwo()
                this.currentDataSecond.datasets[0].data = this.baseCurrentData
                this.currentData = this.currentDataSecond
            } catch (error) {
                console.error(error)
            }
        },
        setupCurrentDataTwo() {
            this.baseCurrentData.shift()
            this.baseCurrentData.push(this.currentChart)
        },
        //end current dataset two 
        //end current

    }
}
</script>

<style lang="scss" scoped>

</style>