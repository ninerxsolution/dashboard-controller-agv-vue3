<template>
    <div class="card">
        <div class="tranbackground">
        <span></span>
        <span></span>
        <span></span>
        <span></span>
    </div>
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
            <div class="row mt-3">
                <div class="col-6 d-flex justify-content-center">
                    <button class="ml-4 btn btn-inverse-light text-warning m-auto">
                        STATUS: <small>{{label}}</small>
                    </button>
                </div>
                <div class="col-6">
                    <button class="btn btn-primary m-auto full-width">  CONFIRM  </button>
                    <!-- <button class="btn-animet">
                    CONFIRM
                    <span class="first"></span>
                    <span class="second"></span>
                    <span class="third"></span>
                    <span class="fourth"></span>
                    </button> -->
                </div>
            </div>
        </div>
    </div>
</template>

<script>
// import ButtonToggle from '@/components/button/buttonToggle.vue'
export default {
    data(){
        return{
            label:'',
            buttonValue:'',
        }
    },
    components:{
        // ButtonToggle,
    },
    props:{
        getJson:{
            type:Object
        }
    },
    created(){
        
        setInterval(() =>{
            this.label = this.getJson["label"];
            this.buttonValue = this.getJson.value;
        },1000)
    }
}
</script>

<style lang="scss" scoped>
.full-width{
    width: 100%;
}

</style>