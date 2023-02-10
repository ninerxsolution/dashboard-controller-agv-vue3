<template>
    <div class="card">
        <div class="tranbackground">
            <span></span>
            <span></span>
            <span></span>
            <span></span>
        </div>
        <div class="card-body">
            <h6>
                DEFAULT EXPORT TOTAL
            </h6>
            <div class="row">
                <div class="col-12">
                    <div class="scrollbar scrollbar-success mb-3 bg-dark" style="height:10rem;">
                        <table class="table table-sm table-borderless mt-2">
                            <tbody>
                                <tr v-for="(tsa, index) in detail_export" :key="tsa">
                                    <td scope="row" class="text-left text-warning d-flex justify-content-between">
                                        <ul class="mb-2">
                                            <li style="font-size: 10px">
                                                {{ tsa.name }}
                                            </li>
                                        </ul>
                                        <div class="form-check p-0 m-0">
                                            <!-- <input type="checkbox" class="form-check-input my-0" :checked="tsa.check"> -->
                                            <input type="checkbox" class="form-check-input my-0"
                                                @click="checked(index, tsa.check)">
                                        </div>
                                    </td>
                                </tr>

                            </tbody>
                            <div class="btn-groug col-12 d-flex justify-content-between">
                                <button type="button" class="btn btn-outline-secondary" @click="updateChart('Year')">
                                    Year
                                </button>
                                "{{ ChartType }}"
                                <button type="button" class="btn btn-outline-secondary" @click="updateChart('Month')">
                                    Month
                                </button>
                            </div>
                        </table>
                    </div>
                    <!-- {{ watchIndex }} {{ detail_export[0].check }} {{ detail_export[1].check }} {{ detail_export[2].check }} -->
                    <div class="col-12 d-flex justify-content-between p-0 m-0">
                        <button class="btn btn-sm btn-warning text-dark">SELECT ALL</button>
                        <button class="btn btn-sm btn-primary text-dark" @click="exportExcel()">EXPORT EXCEL</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    data() {
        return {
            ChartType: 'Month',
            getExport: '',
            ToSwitch: 'Default',
            watchIndex: '',
            afterCheck: 'Before',
            detail_export: [
                { name: 'ENERGY AGV TOTAL', check: false },
                { name: 'PRODUCTION TOTAL', check: false },
                { name: 'CYCLE TRANSPORT', check: false },
            ]
        }
    },
    methods: {
        async exportExcel() {
            try {
                const response = await axios.get('https://se-sskru.com/ev-rail/json/AGV_1/-1?energy=' + this.detail_export[0].check + '&product=' + this.detail_export[1].check + '&cycle=' + this.this.detail_export[2].check + '&type=' + this.ChartType)
                this.getExport = response.data
                this.ToSwitch = "GGEZ"
            } catch (error) {
                console.error(error)
            }
        },
        checked(index, checked) {
            this.watchIndex = index
            this.afterCheck = checked
            this.detail_export[index].check = !checked
        },
        updateChart(choose) {
            this.ChartType = choose
        }
    },

}
</script>

<style lang="scss" scoped>

</style>