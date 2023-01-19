<template>
    <div class="card">
        <div class="card-body">
            <h5>
                CONSUMPTION PRODUCTION TOTAL
            </h5>
            <div class="row">
                <div class="col-12">
                    <ul class="list-ticked text-muted mb-0">
                        <li>
                            <small class="text-muted">
                                PRODUCTION TOTAL (ton)
                            </small>
                        </li>
                    </ul>
                    <div class="d-flex justify-content-between">
                        <div class="progress mt-1">
                            <div class="progress-bar bg-warning" role="progressbar" style="width: 10%"
                                aria-valuenow="90" aria-valuemin="0" aria-valuemax="100">
                            </div>
                        </div>
                        <div class="text-right h6">
                            50 ton
                        </div>
                    </div>
                </div>
                <div class="col-12">
                    <ul class="list-ticked text-muted mb-0">
                        <li>
                            <small class="text-muted">
                                ENERGY (kWh)
                            </small>
                        </li>
                    </ul>
                    <div class="d-flex justify-content-between">
                        <div class="progress mt-1">
                            <div class="progress-bar bg-primary" role="progressbar" style="width: 80%"
                                aria-valuenow="90" aria-valuemin="0" aria-valuemax="100">
                            </div>
                        </div>
                        <div class="text-right h6">
                            6069 kWh
                        </div>
                    </div>
                </div>
                <div class="col-12">
                    <ul class="list-ticked text-muted mb-0">
                        <li>
                            <small class="text-muted">
                                BATTERY (kWh)
                            </small>
                        </li>
                    </ul>
                    <div class="d-flex justify-content-between">
                        <div class="progress mt-1">
                            <div class="progress-bar bg-success" role="progressbar" style="width: 65%"
                                aria-valuenow="90" aria-valuemin="0" aria-valuemax="100">
                            </div>
                        </div>
                        <div class="text-right h6">
                            562 kWh
                        </div>
                    </div>
                </div>
                <div class="col-12">
                    <ul class="list-ticked text-muted mb-0">
                        <li>
                            <small class="text-muted">
                                CO2 (kg)
                            </small>
                        </li>
                    </ul>
                    <div class="d-flex justify-content-between">
                        <div class="progress mt-1">
                            <div class="progress-bar bg-danger" role="progressbar" style="width: 75%" aria-valuenow="90"
                                aria-valuemin="0" aria-valuemax="100">
                            </div>
                        </div>
                        <div class="text-right h6">
                            4061 kg
                        </div>
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