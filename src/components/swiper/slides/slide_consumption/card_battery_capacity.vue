<template>
    <div class="card mb-4">
        <div class="card-body">
            <h5>
                BATTERY CAPACITY {{ name }} {{ age }} {{ jsonData }}
            </h5>
            <div class="d-flex justify-content-between">
                <div class="progress" style="height:2rem !important;">
                    <div class="progress-bar bg-success" role="progressbar" style="width: 82.1%;" aria-valuenow="90"
                        aria-valuemin="0" aria-valuemax="100">
                    </div>
                </div>
                <div class="h3 align-self-center m-0">
                    82.1 %
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

}
</script>

<style lang="scss" scoped>

</style>