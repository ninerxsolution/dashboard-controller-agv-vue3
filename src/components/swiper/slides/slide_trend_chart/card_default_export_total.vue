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
                                <tr v-for="tsa in detail_export" :key="tsa">
                                    <td scope="row" class="text-left text-warning d-flex justify-content-between">
                                        <ul class="mb-2">
                                            <li style="font-size: 10px">
                                                {{ tsa.name }}
                                            </li>
                                        </ul>
                                        <div class="form-check p-0 m-0">
                                            <input type="checkbox" class="form-check-input my-0" :checked="tsa.check">
                                        </div>
                                    </td>
                                </tr>
                            </tbody>
                        </table>
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
export default {
    data() {
        return {
            detail_export: [
                { name: 'ENERGY AGV TOTAL', check: true },
                { name: 'PRODUCTION TOTAL', check: true },
                { name: 'CYCLE TRANSPORT', check: false },
                { name: 'POWER AGV TOTAL', check: true },
                { name: 'TEST', check: false },
                { name: 'TEST', check: false },
                { name: 'TEST', check: true },
                { name: 'TEST', check: false },
                { name: 'TEST', check: false },
            ]
        }
    }
}
</script>

<style lang="scss" scoped>

</style>