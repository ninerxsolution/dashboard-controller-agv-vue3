<template>
    <div class="card">
        <div class="container py-2">
            <div class="row">
                <div class="h5">
                    DETAIL EXPRORT TOTAL
                </div>
            </div>
        </div>
        <div class="card-body mt-0 pt-0 pb-2">
            <div class="containner p-0 my-0">
                <div class="row">
                    <div class="scrollbar-top-left scrollbar-success mb-3">
                        <table class="table table-sm table-borderless force-overflow-topleft">
                        <tbody>
                            <tr v-for="tsa in detail_export" :key="tsa">
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
                        <button class="btn btn-primary px- text-dark">EXPORT EXCEL</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default{
    name: 'CardTopLeft',
    data(){
        return{
            detail_export:[
                {name:'ENERGY AGV TOTAL',check:true},
                {name:'PRODUCTION TOTAL',check:true},
                {name:'CYCLE TRANSPORT',check:false},
                {name:'POWER AGV TOTAL',check:true},
                {name:'TEST',check:false},
                {name:'TEST',check:false},
                {name:'TEST',check:true},
                {name:'TEST',check:false},
                {name:'TEST',check:false},

            ]
        }
    }
}
</script>

<style>
/* scrollbar */
.scrollbar-top-left {
  /* margin-left: 30px; */
  /* float: left; */
  height: 8rem;
  /* width: 65px; */
  /* background: #fff; */
  overflow-y: scroll;
  margin-bottom: 25px;
}
.force-overflow-top-left {
  min-height: 450px;
}

.scrollbar-success::-webkit-scrollbar {
  width: 12px;
  background-color: #F5F5F5;
}

.scrollbar-success::-webkit-scrollbar-thumb {
  border-radius: 10px;
  -webkit-box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.1);
  background-color: #4285F4;
}

.scrollbar-success {
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