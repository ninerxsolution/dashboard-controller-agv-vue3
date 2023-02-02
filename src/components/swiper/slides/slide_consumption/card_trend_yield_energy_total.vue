<template>
    <div class="card">
        Show me more : {{ msg }}
        <div class="card-body">
            <div class="col-12 d-flex justify-content-between">
                <h5 class="d-flex">
                    TREND YIELD AND ENEGY TOTAL
                </h5>
                <div class="btn-group d-flex" role="group" aria-label="Basic example">
                    <!-- <button type="button" class="btn btn-outline-secondary">
                        Year 
                    </button> -->
                    <button type="button" class="btn btn-outline-secondary" @click="updateMsg('Month')">
                        Month
                    </button>
                    <button type="button" class="btn btn-outline-secondary" @click="updateMsg('Day')">
                        Day
                    </button>
                </div>
            </div>
            <BarChart :get_lists="msg" />
        </div>
    </div>
</template>

<script>
import BarChart from '@/components/Chart/BarChart.vue';
export default {
    components: {
        BarChart,
    },
    data() {
        return {
            // set_throw: this.msg,
        }
    },
    props: {
        msg: {
            type: String,
        }
    },
    methods: {
        updateMsg(value) {
            this.$emit('update:msg', value);
        }
    }
}
</script>

<style lang="scss" scoped>

</style>