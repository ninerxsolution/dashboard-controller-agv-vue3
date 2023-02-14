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
                                <button type="button" class="btn btn-outline-secondary" @click="updateChart('year')">
                                    Year
                                </button>
                                "{{ ChartType }}"
                                <button type="button" class="btn btn-outline-secondary" @click="updateChart('month')">
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
                    <!-- {{ tmpExpt_1 }} {{ tmpExpt_2 }} {{ tmpExpt_3 }} {{ ChartType }} {{ getExport }} -->
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
import exportFromJSON from "export-from-json";

export default {
    data() {
        return {
            ChartType: 'month',
            getExport: '',
            ToSwitch: 'Default',
            watchIndex: '',
            afterCheck: 'Before',
            tmpExpt_1: 'Default_1',
            tmpExpt_2: 'Default_2',
            tmpExpt_3: 'Default_3',
            detail_export: [
                { name: 'ENERGY AGV TOTAL', check: false },
                { name: 'PRODUCTION TOTAL', check: false },
                { name: 'CYCLE TRANSPORT', check: false },
            ]
        }
    },
    created() {
        this.tmpExpt_1 = this.detail_export[0].check
        this.tmpExpt_2 = this.detail_export[1].check
        this.tmpExpt_3 = this.detail_export[2].check
    },
    methods: {
        async exportExcel() {
            try {
                const response = await axios.get('https://se-sskru.com/ev-rail/json/AGV_1/export?energy=' + this.tmpExpt_1 + '&product=' + this.tmpExpt_2 + '&cycle=' + this.tmpExpt_3 + '&type=' + this.ChartType)
                this.getExport = response.data.return.export
                this.ToSwitch = "Incorrected!"
            } catch (error) {
                console.error(error)
            }
            const data = this.getExport
            const fileName = "agv-default-export-data";
            const exportType = exportFromJSON.types.csv;
            if (data) exportFromJSON({ data, fileName, exportType });
        },
        checked(index, checked) {
            this.watchIndex = index
            this.afterCheck = checked
            this.detail_export[index].check = !checked
            this.tmpExpt_1 = this.detail_export[0].check
            this.tmpExpt_2 = this.detail_export[1].check
            this.tmpExpt_3 = this.detail_export[2].check
        },
        updateChart(choose) {
            this.ChartType = choose
        }
    },

}
</script>

<style lang="scss" scoped>

</style>