<template>
    <div class="card">
        <div class="container mt-2">
            <div class="h5">
                SET PARAMETER SYSTEM
            </div>
        </div>
        <div class="container">
            <div class="card-body pt-0 px-2 pb-2">
                <div class="row pb-0 ">
                    <div class="scrollbar-setting scrollbar-setting-setpara">
                        <table class="table table-sm table-borderless force-overflow-setting">
                        <tbody>
                            <tr v-for="sps in set_param_sys" :key="sps">
                                <td class="text-warning p-0 dot">·</td>
                                <td scope="row" class="text-left text-warning p-0">{{sps.name_left}}</td>
                                <td class="text-center text-primary sup-val">
                                    <div class="val bg-dark">
                                        {{ sps.val_left }}
                                    </div>
                                </td>
                                <td class="space"></td>
                                <td class="text-warning p-0 dot">·</td>
                                <td scope="row" class="text-left text-warning p-0">{{sps.name_right}}</td>
                                <td class="text-center text-primary sup-val">
                                    <div class="val bg-dark">
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
    </div>
</template>
<script>
export default{
    name:'CardTopRight',
    data(){
        return{
            set_param_sys:[
                {name_left:'AGV',val_left:'1',name_right:'PRODUCTION',val_right:'400 ton.'},
                {name_left:'MAX SPEED',val_left:'2 m/s',name_right:'MAX LOAD',val_right:'4 ton.'},
                {name_left:'CYCLE TIME',val_left:'10 min.',name_right:'LOOP CYCLE',val_right:'100 cyc.'},
                {name_left:'DISTANCE',val_left:'500 m',name_right:'CAMERA',val_right:'YES'},
                {name_left:'BATTERY TIME',val_left:'8 hour',name_right:'LIDAR',val_right:'YES'},
                {name_left:'test',val_left:'0',name_right:'test',val_right:'0'},
                {name_left:'test',val_left:'0',name_right:'test',val_right:'0'},
                {name_left:'test',val_left:'0',name_right:'test',val_right:'0'},
            ]
        }
    }
}
</script>

<style>
/* scrollbar */
.scrollbar-setting {
  /* margin-left: 30px; */
  /* float: left; */
  height: 10rem;
  /* width: 65px; */
  /* background: #fff; */
  overflow-y: scroll;
  /* margin-bottom: 25px; */
}
.force-overflow-setting {
  min-height: 450px;
}

.scrollbar-setting-setpara::-webkit-scrollbar {
  width: 10px;
  background-color: #F5F5F5;
}

.scrollbar-setting-setpara::-webkit-scrollbar-thumb {
  border-radius: 10px;
  -webkit-box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.1);
  background-color: #4285F4;
}

.scrollbar-setting-setpara {
  scrollbar-color: #4285F4 #F5F5F5;
}
.btn{
    width: 100%;
    height: 100%;
}
/* .td{
    padding:unset !important;
} */
.space{
    width: 10%;
}
.dot{
    width: 5%;
}
.val{
    width: 100%;
    height: 30px;
    padding-top:9px;
}
.sup-val{
 width: 20%;
}

</style>