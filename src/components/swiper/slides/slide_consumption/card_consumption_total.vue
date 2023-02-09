<template>
    <div class="card">
        <div class="tranbackground">
        <span></span>
        <span></span>
        <span></span>
        <span></span>
    </div>
        <div class="card-body">
            <h5 class="">
                CONSUMPTION PRODUCTION TOTAL
            </h5>
            <div class="row">
                <div class="col-12">
                    <ul class="list-ticked text-muted mb-0">
                        <li>
                            <div class="text-muted">
                                <small>PRODUCTION TOTAL (ton)</small>
                            </div>
                        </li>
                    </ul>
                    <div class="d-flex justify-content-between">
                        <div class="progress mt-1">
                            <div class="progress-bar bg-warning" role="progressbar"
                                :style="{ width: (production_total / 1000) * 100 + '%' }"
                                aria-valuenow="{{ production_total }}" aria-valuemin="0" aria-valuemax="100">
                            </div>
                        </div>
                        <div class="text-right h6">
                            {{ production_total }} ton
                        </div>
                    </div>
                </div>
                <div class="col-12">
                    <ul class="list-ticked text-muted mb-0">
                        <li>
                            <div class="text-muted">
                                <small>ENERGY (kWh)</small>
                            </div>
                        </li>
                    </ul>
                    <div class="d-flex justify-content-between">
                        <div class="progress mt-1">
                            <div class="progress-bar bg-primary" role="progressbar"
                                :style="{ width: (energy_total / 10000) * 100 + '%' }" aria-valuenow="{{energy_total}}"
                                aria-valuemin="0" aria-valuemax="100">
                            </div>
                        </div>
                        <div class="text-right h6">
                            {{ energy_total }} kWh
                        </div>
                    </div>
                </div>
                <div class="col-12">
                    <ul class="list-ticked text-muted mb-0">
                        <li>
                            <div class="text-muted">
                                <small>BATTERY (kWh)</small>
                            </div>
                        </li>
                    </ul>
                    <div class="d-flex justify-content-between">
                        <div class="progress mt-1">
                            <div class="progress-bar bg-success" role="progressbar" :style="{ width: (battery_total / 1000) * 100 + '%' }"
                                aria-valuenow="{{ battery_total }}" aria-valuemin="0" aria-valuemax="100">
                            </div>
                        </div>
                        <div class="text-right h6">
                            {{ battery_total }} kWh
                        </div>
                    </div>
                </div>
                <div class="col-12">
                    <ul class="list-ticked text-muted mb-0">
                        <li>
                            <div class="text-muted">
                               <small> CO2 (kg)</small>
                            </div>
                        </li>
                    </ul>
                    <div class="d-flex justify-content-between">
                        <div class="progress mt-1">
                            <div class="progress-bar bg-danger" role="progressbar"
                                :style="{ width: (co2_emit / 10000) * 100 + '%' }" aria-valuenow="{{co2_emit}}"
                                aria-valuemin="0" aria-valuemax="10000">
                            </div>
                        </div>
                        <div class="text-right h6">
                            {{ co2_emit }} kg
                        </div>
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
            production_total: 'Default',
            energy_total: 'Default',
            battery_total: 'Default',
            co2_emit: 'Default',
        }
    },
    props: {
        get_CONSUMPTION: {
            type: Object
        }
    },
    created() {
        setInterval(() => {
            this.production_total = this.get_CONSUMPTION.CONSUMPTION_PRODUCTION_TOTAL.total_consumption.value
            this.energy_total = this.get_CONSUMPTION.CONSUMPTION_PRODUCTION_TOTAL.energy_consumption.value
            this.battery_total = this.get_CONSUMPTION.CONSUMPTION_PRODUCTION_TOTAL.battery_life.value
            this.co2_emit = this.get_CONSUMPTION.CONSUMPTION_PRODUCTION_TOTAL.co2_emissions.value
        }, 1000)
    }
}
</script>

<style lang="scss" scoped>

</style>