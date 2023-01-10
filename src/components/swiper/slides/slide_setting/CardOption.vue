<template>
    <div class="card option-card">
        <div class="container pt-2 h6">
            OPTION
        </div>
        <dvi class="container contain-option pb-2">
            <div class="d-flex flex-column justify-content-around card-option-content">
                <div class="text-primary text-center"><small>WORNNING REPORT</small></div>
                <div class="app-option">
                    <div class="container card-option-content">
                        <div class="row option-item-row">
                            <div class="col-md-6 d-flex flex-column justify-content-center">
                                <div>
                                    <img class="img-social" src="https://static.newmobilelife.com/wp-content/uploads/2014/10/LineforiPad00-210x210.png" alt="">
                                </div>
                            </div>
                            <div class="col-md-6 d-flex flex-column justify-content-center text-center">
                                <div class="text-warning mb-2"><small>LINE APP</small> </div>
                                <div class="mb-2"><button-toggle/></div>
                                <div class="text-warning"><small>CONFIRM</small> </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="app-option">
                    <div class="container card-option-content">
                        <div class="row option-item-row">
                            <div class="col-md-6 d-flex flex-column justify-content-center">
                                <div>
                                    <img class="img-social" src="https://logos-download.com/wp-content/uploads/2016/05/Gmail_logo_icon.png" alt="">
                                </div>
                            </div>
                            <div class="col-md-6 d-flex flex-column justify-content-center text-center">
                                <div class="text-warning mb-2"><small>GMAIL</small> </div>
                                <div class="mb-2"><button-toggle/></div>
                                <div class="text-warning"><small>CONFIRM</small> </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </dvi>
    </div>
</template>

<script>
import ButtonToggle from '@/components/button/buttonToggle.vue'
export default{
    name:'CardOption',
    components:{
        ButtonToggle,
    }
}
</script>
<style>
.option-item-row{
 height: 100%;
}
.card-option-content{
    height: 100%;
}
.contain-option{
    height: 100%;
}
.option-card{
    height:130%;
}
.card-content{
    background-color: #13151D;
}
.app-option{
    height: 100%;
}
.img-social{
    border-radius: 20%;
}
</style>