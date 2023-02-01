<template>
    <div class="card">
        <div class="card-body">
            <h5>
                CONFIRM RUNNING SYSTEM
            </h5>
            <div class="d-flex justify-content-around bg-dark p-3 mt-2">
                <div class="start-big-button bg-success">
                    <div class="h2">
                        start
                    </div>
                </div>
                <div class="stop-big-button bg-danger">
                    <div class="h2">
                        stop
                    </div>
                </div>
            </div>
            <div class="d-flex justify-content-around p-3">
                <div class="mx-3">
                    <button class="btn btn-inverse-light text-warning">
                        STATUS: <small>Running</small>
                    </button>
                </div>
                <div class="mt-2">
                    <ButtonToggle />
                </div>
                <div class="h6 text-warning mt-2 mx-3">
                    CONFIRM
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import ButtonToggle from '@/components/button/buttonToggle.vue'
export default {
    components:{
        ButtonToggle,
    }
}
</script>

<style lang="scss" scoped>

</style>