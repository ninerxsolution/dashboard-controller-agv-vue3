<template>
    <div class="card mb-4">
        <div class="tranbackground">
        <span></span>
        <span></span>
        <span></span>
        <span></span>
    </div>
        <div class="card-body">
            <h5>
                BATTERY CAPACITY
            </h5>
            <div class="d-flex justify-content-between">
                <div class="progress" style="height:2rem !important;">
                    <div class="progress-bar bg-success" role="progressbar" style="width: 82.1%;" aria-valuenow="90"
                        aria-valuemin="0" aria-valuemax="100">
                    </div>
                </div>
                <div class="h3 align-self-center m-0">
                    {{ battery_capacity }} %
                </div>
            </div>
            <div class="text text-sm text-center text-warning">
                Discharge
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            battery_capacity: 'Default',
        }
    },
    props: {
        get_BATTERY: {
            type: Object
        }
    },
    created() {
        setInterval(() => {
            this.battery_capacity = this.get_BATTERY.BATTERY_CAPACITY.value
        }, 1000)
    }
}
</script>

<style lang="scss" scoped>

</style>