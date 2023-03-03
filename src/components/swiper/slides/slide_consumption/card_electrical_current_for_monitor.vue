<template>
    <div class="card mb-4">
        <div class="tranbackground">
        <span></span>
        <span></span>
        <span></span>
        <span></span>
    </div>
        <div class="card-body">
            <h6>
                ELECTRICAL CURRENT FOR MONITOR
            </h6>
            <div class="row">
                <div class="col-6 text-center">
                    <div class="mr-2">
                        <currentNow :get-current-now="current_now"/>
                        <!-- <circle-progress :percent="80" :unit="kg / hr" :show-percent="true" :size="100"
                            :class="circle - progress" class="dummy-meter" /> -->
                    </div>
                    <div class="pt-1 text-muted">
                        <small>
                            SPEED CURRENT
                        </small>
                    </div>
                </div>
                <div class="col-1"></div>
                <div class="col-5">
                    <div class="display-4">
                        {{ current_now }} A
                    </div>
                    <small>
                        CURRENT MAX 120.0
                    </small><br>
                    <small>
                        CURRENT AVE 35.0
                    </small><br>
                    <small class="d-flex">
                        STATUS
                        <div class="text-warning mx-3">
                            Forward
                        </div>
                    </small>
                    <small class="d-flex">
                        WORKING
                        <div class="text-primary mx-3">
                            Ready
                        </div>
                    </small>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import "vue3-circle-progress/dist/circle-progress.css";
// import CircleProgress from "vue3-circle-progress";
import currentNow from "@/components/speedOmeter/currentNowMeter.vue";

export default {
    components: {
        // CircleProgress,
        currentNow
    },
    data() {
        return {
            current_now: 'Default',
        }
    },
    props: {
        get_ELECTRICAL_MONITOR: {
            type: Object
        }
    },
    created() {
        setInterval(() => {
            this.current_now = this.get_ELECTRICAL_MONITOR.ELECTRICAL_CURRENT_FOR_MOTOR.current_now.value
        }, 1000)
    }
}
</script>

<style lang="scss" scoped>

</style>