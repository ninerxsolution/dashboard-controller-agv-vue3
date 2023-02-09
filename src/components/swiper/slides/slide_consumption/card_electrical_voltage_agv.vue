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
                ELECTRICAL VOLTAGE AGV
            </h5>
            <div class="row">
                <div class="col-6 text-center">
                    <div>
                        <circle-progress :percent="80" :unit="kg / hr" :show-percent="true" :size="100"
                            :fill-color="'#ffd000'" class="dummy-meter" />
                    </div>
                    <div class="pt-1 text-muted">
                        <small>
                            VOLTAGE AVERAGE
                        </small>
                    </div>
                </div>
                <div class="col-6">
                    <div class="display-4">
                        {{ voltage_average }} v
                    </div>
                    <small>
                        VOL MAX 55.9 v
                    </small><br>
                    <small>
                        VOL MIN 48.9 v
                    </small><br>
                    <small class="d-flex">
                        STATUS
                        <div class="mx-3 text-warning">
                            Standby
                        </div>
                    </small>
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
    },
    data() {
        return {
            voltage_average: 'Default',
        }
    },
    props: {
        get_ELECTRICAL: {
            type: Object
        }
    },
    created() {
        setInterval(()=>{
            this.voltage_average = this.get_ELECTRICAL.ELEECTRICAL_VOLTAGE_AGV.voltage_average.value
        },1000)
    }
}
</script>

<style lang="scss" scoped>

</style>