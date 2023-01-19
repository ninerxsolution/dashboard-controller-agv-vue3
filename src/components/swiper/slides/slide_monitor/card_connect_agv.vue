<template>
    <div class="card">
        <div class="card-body">
            <h5>
                CONNECT AGV
            </h5>
            <div class="row">
                <div class="d-flex justify-content-between">
                    <ul class="list-ticked text-muted mb-0">
                        <li>
                            <small class="text-muted">
                                TOTAL AGV
                            </small>
                        </li>
                    </ul>
                    <div class="progress mt-1" style="width: 40%">
                        <div class="progress-bar bg-warning" role="progressbar" style="width: 100%" aria-valuenow="100"
                            aria-valuemin="0" aria-valuemax="100">
                        </div>
                    </div>
                    <div class="text-right mx-1">
                        3
                    </div>
                </div>
                <div class="d-flex justify-content-between">
                    <ul class="list-ticked text-muted mb-0">
                        <li>
                            <small class="text-muted">
                                AGV Online
                            </small>
                        </li>
                    </ul>
                    <div class="progress mt-1" style="width: 40%">
                        <div class="progress-bar bg-success" role="progressbar" style="width: 33%" aria-valuenow="100"
                            aria-valuemin="0" aria-valuemax="100">
                        </div>
                    </div>
                    <div class="text-right mx-1">
                        1
                    </div>
                </div>
                <div class="d-flex justify-content-between">
                    <ul class="list-ticked text-muted mb-0">
                        <li>
                            <small class="text-muted">
                                AGV Offline
                            </small>
                        </li>
                    </ul>
                    <div class="progress mt-1" style="width: 40%">
                        <div class="progress-bar bg-danger" role="progressbar" style="width: 66%" aria-valuenow="100"
                            aria-valuemin="0" aria-valuemax="100">
                        </div>
                    </div>
                    <div class="text-right mx-1">
                        2
                    </div>
                </div>
                <div class="pt-1 text-danger text-center">
                    <small>
                        For Maximum AGV : 3 connects
                    </small>
                </div>
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