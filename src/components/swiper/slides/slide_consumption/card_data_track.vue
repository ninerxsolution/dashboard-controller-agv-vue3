<template>
    <div class="card mb-4">
        <div class="card-body">
            <h5 class="mb-0">
                DATA AGV TRACK
            </h5>
            <div class="d-flex justify-content-between">
                <ul class="list-ticked text-muted mb-0 justify-centent-between">
                    <li>
                        <div class="text-muted d-flex justify-centent-between">
                            Transpot today
                        </div>
                    </li>
                </ul>
                <div class="text-right">
                    {{ transpot_today }}/400 ton
                </div>
            </div>
            <div class="d-flex justify-content-between">
                <ul class="list-ticked text-muted mb-0 justify-centent-between">
                    <li>
                        <div class="text-muted d-flex justify-centent-between">
                            Working mode
                        </div>
                    </li>
                </ul>
                <div class="text-right">
                    {{ working_mode }}
                </div>
            </div>
            <div class="d-flex justify-content-between">
                <ul class="list-ticked text-muted mb-0 justify-centent-between">
                    <li>
                        <div class="text-muted d-flex justify-centent-between">
                            Status cycle
                        </div>
                    </li>
                </ul>
                <div class="text-right">
                    {{ status_cycle }}/100 Cycle
                </div>
            </div>
            <div class="d-flex justify-content-between">
                <ul class="list-ticked text-muted mb-0 justify-centent-between">
                    <li>
                        <div class="text-muted d-flex justify-centent-between">
                            Maximum load
                        </div>
                    </li>
                </ul>
                <div class="text-right">
                    {{ maximum_load }} ton
                </div>
            </div>
            <div class="d-flex justify-content-between">
                <ul class="list-ticked text-muted mb-0 justify-centent-between">
                    <li>
                        <div class="text-muted d-flex justify-centent-between">
                            Tracking guide
                        </div>
                    </li>
                </ul>
                <div class="text-right">
                    {{ tracking_guide }}
                </div>
                <!-- {{ get_DATA_TRACK }} -->
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            transpot_today: 'Default',
            working_mode: 'Default',
            status_cycle: 'Default',
            maximum_load: 'Default',
            tracking_guide: 'Default',
        }
    },
    props: {
        get_DATA_TRACK: {
            type: Object
        }
    },
    created() {
        setInterval(() => {
            this.transpot_today = this.get_DATA_TRACK.DATA_AGV_TRACK.transpot_today.value
            this.working_mode = this.get_DATA_TRACK.DATA_AGV_TRACK.working_mode.value
            this.status_cycle = this.get_DATA_TRACK.DATA_AGV_TRACK.status_cycle.value
            this.maximum_load = this.get_DATA_TRACK.DATA_AGV_TRACK.maximum_load.value
            this.tracking_guide = this.get_DATA_TRACK.DATA_AGV_TRACK.tracking_guide.value

        }, 1000)
    }
}
</script>

<style lang="scss" scoped>



</style>