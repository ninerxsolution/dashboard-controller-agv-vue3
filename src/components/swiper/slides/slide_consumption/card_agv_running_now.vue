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
                AGV RUNNING NOW
            </h5>
            <div class="row">
                <div class="col-6 text-center">
                    <div class="mr-2">
                        <currentMeter :getSpeedCurrent="speed_current"/>
                        <!-- <circle-progress :percent="(speed_current / 2.0) * 100" :unit="''" :show-percent="true"
                            :size="100" class="dummy-meter" /> -->
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
                        {{ speed_current }} m/s
                    </div>
                    <small>
                        SPEED MAX 2.0 m/s
                    </small><br>
                    <small>
                        SET SPEED 0.5 m/s
                    </small><br>
                    <small class="d-flex">
                        STATUS
                        <div class="text-primary mx-3">
                            Running
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
import currentMeter from "@/components/speedOmeter/currentMeter.vue";
export default {
    components: {
        // CircleProgress,
        currentMeter,
    },
    data() {
        return {
            speed_current: 'Default',
        }
    },
    props: {
        get_AGV_RUNNING: {
            type: Object
        }
    },
    created() {
        setInterval(() => {
            this.speed_current = this.get_AGV_RUNNING.AGV_RUNNING_NOW.speed_current.value
        }, 1000)
    }
}
</script>

<style lang="scss" scoped>

</style>