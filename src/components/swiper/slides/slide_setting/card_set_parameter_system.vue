<template>
    <div class="card">
        <div class="card-body">
            <h5 class="d-flex">
                SET PARAMETER SYSTEM
            </h5>
            <div class="col-12">
                <div class="scrollbar scrollbar-setting-setpara" style="height:10rem;">
                    <table class="table table-sm table-borderless force-overflow-setting mt-2">
                        <tbody>
                            <tr v-for="sps in set_param_sys" :key="sps">
                                <td scope="row" class="text-left text-warning p-0">
                                    <ul class="mb-2">
                                        <li>
                                            {{ sps.name_left }}
                                        </li>
                                    </ul>
                                </td>
                                <td class="text-center text-primary sup-val">
                                    <div class="val bg-dark p-2">
                                        {{ sps.val_left }}
                                    </div>
                                </td>
                                <td class="space"></td>
                                <td scope="row" class="text-left text-warning p-0">
                                    <ul>
                                        <li>
                                            {{ sps.name_right }}
                                        </li>
                                    </ul>
                                </td>
                                <td class="text-center text-primary sup-val">
                                    <div class="val bg-dark p-2">
                                        {{ sps.val_right }}
                                    </div>
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    components:
    {

    },
    data() {
        return {
            set_param_sys: [
                { name_left: 'AGV', val_left: '1', name_right: 'PRODUCTION', val_right: '400 ton.' },
                { name_left: 'MAX SPEED', val_left: '2 m/s', name_right: 'MAX LOAD', val_right: '4 ton.' },
                { name_left: 'CYCLE TIME', val_left: '10 min.', name_right: 'LOOP CYCLE', val_right: '100 cyc.' },
                { name_left: 'DISTANCE', val_left: '500 m', name_right: 'CAMERA', val_right: 'YES' },
                { name_left: 'BATTERY TIME', val_left: '8 hour', name_right: 'LIDAR', val_right: 'YES' },
                { name_left: 'test', val_left: '0', name_right: 'test', val_right: '0' },
                { name_left: 'test', val_left: '0', name_right: 'test', val_right: '0' },
                { name_left: 'test', val_left: '0', name_right: 'test', val_right: '0' },
            ]
        }
    }
}
</script>

<style lang="scss" scoped>

</style>