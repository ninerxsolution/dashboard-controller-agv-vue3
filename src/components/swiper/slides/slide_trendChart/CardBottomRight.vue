<template>
    <div class="card">
        <div class="container py-2">
            <div class="row">
                <!-- <div class="col-1"></div> -->
                <div class="col-5">
                    <!-- <button-toggle/> -->
                    <button class="btn btn-dark p-0">Date-time</button>
                </div>
                <div class="col-7">
                    <span class="text-warning">STATUS: </span>
                    <span class="text-success">Online</span>
                </div>
            </div>
        </div>
        <div class="card-body bg-dark py-2">
            <div class="containner p-0 my-0">
                <div class="row">
                    <div class="scrollbar scrollbar-primary mb-3">
                        <table class="table table-sm table-borderless force-overflow">
                        <tbody>
                            <tr v-for="tsa in trend_select_agv" :key="tsa">
                                <td class="text-warning p-0">·</td>
                                <td scope="row" class="text-left text-warning p-0">{{tsa.name}}</td>
                                <td class="text-right">   
                                        <div class="form-check p-0">
                                            <input type="checkbox" class="form-check-input my-0" :checked="tsa.check">
                                        </div>                                                        
                                </td>
                            </tr>
                        </tbody>
                        </table>
                    </div>
                </div>
                <div class="row">                                              
                    <div class="col-md-6 p-0 pr-1">
                        <button class="btn btn-warning px-0 text-dark">SELECT ALL</button>
                    </div>
                    <div class="col-md-6 p-0">
                        <button class="btn btn-primary px-0 text-dark">EXPORT EXCEL</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
// import buttonToggle from '@/components/button/buttonToggle.vue';
export default{
    name:'CardBottomRight',
    components: {
        // buttonToggle,
    },
    data(){
        return{
            trend_select_agv:[
                {name:'SPEED AGV 1',check:true},
                {name:'SPEED AGV 2',check:false},
                {name:'SPEED AGV 3',check:false},
                {name:'POWER AGV 1',check:true},
                {name:'POWER AGV 2',check:false},
                {name:'POWER AGV 3',check:false},
                {name:'CURR AGV 1',check:true},
                {name:'CURR AGV 2',check:false},
                {name:'CURR AGV 3',check:false},

            ]
        }
    }
}
</script>

<style>
/* scrollbar */
.scrollbar {
  /* margin-left: 30px; */
  /* float: left; */
  height: 18rem;
  /* width: 65px; */
  /* background: #fff; */
  overflow-y: scroll;
  margin-bottom: 25px;
}
.force-overflow {
  min-height: 450px;
}

.scrollbar-primary::-webkit-scrollbar {
  width: 12px;
  background-color: #F5F5F5;
}

.scrollbar-primary::-webkit-scrollbar-thumb {
  border-radius: 10px;
  -webkit-box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.1);
  background-color: #4285F4;
}

.scrollbar-primary {
  scrollbar-color: #4285F4 #F5F5F5;
}
.btn{
    width: 100%;
    height: 100%;
}
.td{
    padding:unset !important;
}

</style>