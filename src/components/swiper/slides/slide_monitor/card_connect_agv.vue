<template>
    <div class="card">
        <div class="card-body">
            <h5>
                CONNECT AGV
            </h5>
            <div class="row">
                <div class="d-flex justify-content-between mt-2">
                    <ul class="list-ticked text-muted m-0">
                        <li>
                            <div class="text-muted align-self-center">
                                TOTAL AGV
                            </div>
                        </li>
                    </ul>
                    <div class="progress align-self-center" style="width: 40%">
                        <div class="progress-bar bg-warning" role="progressbar" style="width: 100%" aria-valuenow="100"
                            aria-valuemin="0" aria-valuemax="100">
                        </div>
                    </div>
                    <div class="text-right mx-1 align-self-center">
                        3
                    </div>
                </div>
                <div class="d-flex justify-content-between mt-2">
                    <ul class="list-ticked text-muted m-0">
                        <li>
                            <div class="text-muted">
                                AGV Online
                            </div>
                        </li>
                    </ul>
                    <div class="progress align-self-center" style="width: 40%">
                        <div class="progress-bar bg-success" role="progressbar" style="width: 33%" aria-valuenow="100"
                            aria-valuemin="0" aria-valuemax="100">
                        </div>
                    </div>
                    <div class="text-right mx-1">
                        1
                    </div>
                </div>
                <div class="d-flex justify-content-between mt-2">
                    <ul class="list-ticked text-muted m-0">
                        <li>
                            <div class="text-muted">
                                AGV Offline
                            </div>
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
                <div class="pt-2 text-danger text-center">
                    <div>
                        For Maximum AGV : 3 connects
                    </div>
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