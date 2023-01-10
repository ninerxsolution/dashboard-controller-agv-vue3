<template>
    <div class="card card-full-height">
        <div class="container py-2 px-2">
            <div class="row">
                <div class="col-5">
                    TREND SELECT AGV
                </div>
                <div class="col-3">
                    <div class="input-group-prepend">
                        <button class="btn btn-dark dropdown-toggle text-warning" type="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">AGV1</button>
                        <div class="dropdown-menu">
                            <a class="dropdown-item" href="#">Action</a>
                            <a class="dropdown-item" href="#">Another action</a>
                            <a class="dropdown-item" href="#">Something else here</a>
                            <div role="separator" class="dropdown-divider"></div>
                            <a class="dropdown-item" href="#">Separated link</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="card-body bg-dark py-2 px-2">
            <div class="container">
            </div>
            <div class="scrollbar-bottom-left scrollbar-info">
                <table class="table table-sm table-borderless force-overflow-bottom-left m-0">
                <tbody>
                    <tr>
                        <!-- <LineChart/> -->
                    </tr>
                </tbody>
                </table>
            </div>
        </div>
    </div>
</template>

<script>
// import LineChart from '@/components/Chart/LineChart.vue'

export default{
    name:'CardBottomLeft',
    components:{
        // LineChart,
    }
}
</script>

<style>
/* scrollbar */
.scrollbar-bottom-left {
  /* margin-left: 30px; */
  /* float: left; */
  height: 20rem;
  /* width: 65px; */
  /* background: #fff; */
  overflow-y: scroll;
  /* margin-bottom: 25px; */
}
.force-overflow-bottom-left {
  min-height: 450px;
}

.scrollbar-info::-webkit-scrollbar {
  width: 12px;
  background-color: #F5F5F5;
}

.scrollbar-info::-webkit-scrollbar-thumb {
  border-radius: 10px;
  -webkit-box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.1);
  background-color: #4285F4;
}

.scrollbar-info {
  scrollbar-color: #4285F4 #F5F5F5;
}
.card-full-height{
    height:100%;
}

</style>