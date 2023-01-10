<template>
    <div class="card card-top-left pb-0">
        <div class="container mt-2">
            <div class="h5">CONFIRM RUNNING SYSTEM</div>
        </div>
        <div class="card-body pt-0 pb-0">
            <div class="container bg-dark start-stop-button-area">
                <div class="d-flex flex-row justify-content-around flex-button">
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
            </div>
        </div>
        <div class="container mb-2">
            <div class="d-flex flex-row justify-content-center">
                <div><button class="btn btn-inverse-light text-warning">
                    STATUS: <small>Running</small>
                </button></div>
                <div class="mt-2">
                    <ButtonToggle/>
                </div>
                <div class="h6 text-warning mt-2">
                    CONFIRM
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import ButtonToggle from '@/components/button/buttonToggle.vue'
export default{
    name:'CardTopLeft',
    components: { ButtonToggle },
}
</script>

<style>
.card-top-left{
    height:100%
}
.start-stop-button-area{
    height: 120px;
}
.start-big-button{
    width: 90px;
    height: 90px;
    margin-top: auto;
    margin-bottom: auto;
    border: solid 4px gray;
    border-radius: 50%;
    text-align: center;
    padding-top:1.25rem ;
}
.stop-big-button{
    width: 90px;
    height: 90px;
    margin-top: auto;
    margin-bottom: auto;
    border: solid 4px gray;
    border-radius: 50%;
    text-align: center;
    padding-top:1.25rem ;
}
.flex-button{
    height: 100%;
}
/* .status-button-control{
    height:100% ;
} */
</style>