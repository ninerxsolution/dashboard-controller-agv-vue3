<template>
    <div class="card mb-4">
        <div class="card-body">
            <h5>
                AGV RUNNING NOW
            </h5>
            <div class="row">
                <div class="col-6 text-center">
                    <div>
                        <circle-progress :percent="10" :unit="''" :show-percent="true" :size="100"
                            class="dummy-meter" />
                    </div>
                    <div class="pt-1 text-muted">
                        <small>
                            SPEED CURRENT
                        </small>
                    </div>
                </div>
                <div class="col-6">
                    <div class="display-4">
                        0.5 m/s
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
import CircleProgress from "vue3-circle-progress";
export default {
    components: {
        CircleProgress,
    }
}
</script>

<style lang="scss" scoped>

</style>