<template>
    <div class="card mb-4">
        <div class="card-body">
            <h5>
                ELECTRICAL CURRENT FOR MONITOR
            </h5>
            <div class="row">
                <div class="col-6 text-center">
                    <div>
                        <circle-progress :percent="80" :unit="kg / hr" :show-percent="true" :size="100"
                            :class="circle - progress" class="dummy-meter" />
                    </div>
                    <div class="pt-1 text-muted">
                        <small>
                            SPEED CURRENT
                        </small>
                    </div>
                </div>
                <div class="col-6">
                    <div class="display-4">
                        49.9 A
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
import CircleProgress from "vue3-circle-progress";
export default {
    components: {
        CircleProgress,

    }
}
</script>

<style lang="scss" scoped>

</style>