<template>
    <div class="card  mb-4">
        <div class="tranbackground">
        <span></span>
        <span></span>
        <span></span>
        <span></span>
    </div>
        <div class="card-body">

            <div class="d-flex justify-content-between">
                <h5 class="d-flex mb-0 mt-1">
                    <span>MAP FOR ROUTE</span>
                </h5>
                <div class="d-flex">
                    <button class="btn-dark text-warning">
                        <div>
                            Non drawback AGV 1
                        </div>
                    </button>
                    <i class="mdi mdi-eye px-2  align-self-center"></i>
                    <button class="btn-dark text-success">
                        <div>
                            Battery AGV 1 OK
                        </div>
                    </button>
                    <i class="mdi mdi-truck px-2  align-self-center"></i>
                </div>

                <div class="d-flex">
                    <div class="text align-self-center">
                        CONNECT :
                    </div>
                    <button-toggle class="mx-2 align-self-center" />
                    <!-- <button class="btn btn-warning text-dark mx-2 px-4" >
                      UPDATE MAP
                    </button> -->
                    <a href="#" style="--clr:#00ccbb;--i:1;"><span>UPDATE MAP</span></a>
                    

                </div>
                
            </div>
            <div class="row">
                <div class="col-12 mt-4">
                    <div class="card-body bg-dark p-2">
                        <div class="card-title d-flex justify-content-between">
                            <div>
                                Point Station
                            </div>
                            <div>
                                Point End
                            </div>
                        </div>
                        <div class="d-flex justify-content-between">
                            <ul>
                                <li>
                                    AGV 1
                                </li>
                            </ul>
                            <div class="progress mt-1 mx-3" style="width:85%;">
                                <div class="progress-bar bg-warning" style="width:47%;">
                                    <div class="text-dark">
                                        AGV 1 Running : SPEED 0.5 m/s
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div class="d-flex justify-content-between">
                            <ul>
                                <li>
                                    AGV 2
                                </li>
                            </ul>
                            <div class="progress mt-1 mx-3" style="width:85%;">
                                <div class="progress-bar bg-warning" style="width:0%;">
                                </div>
                            </div>
                        </div>
                        <div class="d-flex justify-content-between">
                            <ul>
                                <li>
                                    AGV 3
                                </li>
                            </ul>
                            <div class="progress mt-1 mx-3" style="width:85%;">
                                <div class="progress-bar bg-warning" style="width:0%;">

                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="d-flex justify-content-between mt-3">
                    <div class="col-3 bg-dark mt-4 p-4">

                        <div class="d-flex align-self-middle">
                            <ul class="m-0">
                                <li>
                                    <div class="align-self-middle">
                                        <span class="">AGV 1</span>
                                    </div>
                                </li>
                            </ul>
                            <div class="text-success align-self-middle">
                                <div class="div mx-4 align-self-middle">
                                    <span>Running</span>
                                </div>
                            </div>
                        </div>

                        <div class="d-flex align-self-middle">
                            <ul class="mb-0">
                                <li>
                                    <div>
                                        <span>AGV 2</span>
                                    </div>
                                </li>
                            </ul>
                            <div class="text-danger">
                                <div class="div mt-1 mx-4">
                                    <span> Offline</span>
                                </div>
                            </div>
                        </div>
                        <div class="d-flex align-self-middle">
                            <ul class="mb-0">
                                <li>
                                    <div>
                                        <span>AGV 3</span>
                                    </div>
                                </li>
                            </ul>
                            <div class="text-danger">
                                <div class="div mt-1 mx-4">
                                    <span>Offline</span>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="col-3 bg-dark mt-4 p-4">
                        <div class="d-flex ">
                            <ul class="mb-0">
                                <li>
                                    <div>
                                        <span> AGV 1</span>
                                    </div>
                                </li>
                            </ul>
                            <div class="text-primary m-0">
                                <div class="div mt-1 mx-4">
                                    <span>200 ton</span>
                                </div>
                            </div>
                        </div>
                        <div class="d-flex">
                            <ul class="mb-0">
                                <li>
                                    <div>
                                        <span>AGV 2</span>
                                    </div>
                                </li>
                            </ul>
                            <div class="text-warning">
                                <div class="div mt-1 mx-4">
                                    <span>0 ton</span>
                                </div>
                            </div>
                        </div>
                        <div class="d-flex">
                            <ul class="mb-0">
                                <li>
                                    <div>
                                        <span> AGV 3</span>
                                    </div>
                                </li>
                            </ul>
                            <div class="text-warning">
                                <div class="div mt-1 mx-4">
                                    <span> 0 ton</span>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="col-3  bg-dark mt-4 pt-4">
                        <div class="d-flex">
                            <ul class="mb-0">
                                <li>
                                    <div>
                                        <span>AGV 1</span>
                                    </div>
                                </li>
                            </ul>
                            <div class="text-primary">
                                <div class="div mt-1 mx-4">
                                    <span>200 ton</span>
                                </div>
                            </div>
                        </div>
                        <div class="d-flex">
                            <ul class="mb-0">
                                <li>
                                    <div>
                                        <span>AGV 2</span>
                                    </div>
                                </li>
                            </ul>
                            <div class="text-warning">
                                <div class="div mt-1 mx-4">
                                    <span>0 ton</span>
                                </div>
                            </div>
                        </div>
                        <div class="d-flex">
                            <ul class="mb-0">
                                <li>
                                    <div>
                                        <span>AGV 3</span>
                                    </div>
                                </li>
                            </ul>
                            <div class="text-warning">
                                <div class="div mt-1 mx-4">
                                    <span> 0 ton</span>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="col-3  bg-dark pt-4 mt-4">
                        <div class="d-flex text-warning justify-content-between">
                            <ul class="mb-0">
                                <li>
                                    <div>
                                        <span> DISTANCE TOTAL</span>
                                    </div>
                                </li>
                            </ul>
                            <div class="text-right">
                                <div class="div mt-1 mx-2">
                                    500 m
                                </div>
                            </div>
                        </div>
                        <div class="d-flex text-primary justify-content-between">
                            <ul class="mb-0">
                                <li>
                                    <div>
                                        <span>MAXIMUM CYCLE</span>
                                    </div>
                                </li>
                            </ul>
                            <div class="text-right">
                                <div class="div mt-1 mx-2">
                                    10 min
                                </div>
                            </div>
                        </div>
                        <div class="d-flex text-warning justify-content-between">
                            <ul class="mb-0">
                                <li>
                                    <div>
                                        <span>MAXIMUX SPEED</span>
                                    </div>
                                </li>
                            </ul>
                            <div class="text-right">
                                <div class="div mt-1 mx-2">
                                    2 m/s
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import buttonToggle from '@/components/button/buttonToggle.vue';

export default {
    components: {
        buttonToggle,
    }
}
</script>

<style lang="scss" scoped>

a {
   
   position: relative;
   padding: 10px 50px;
   display: flex;
   justify-content: center;
   align-items: center;
   background: rgba(0, 0, 0, 0.5);
   transition: 1s;
   overflow: hidden;
   text-decoration: none;
   -webkit-box-reflect: below 1px linear-gradient(transparent,
   transparent,#0004);
   border-radius: 20px;
}

a:hover {
   background: var(--clr);
   box-shadow: 0 0 10px var(--clr),
   0 0 30px var(--clr),
   0 0 60px var(--clr),
   0 0 100px var(--clr);
}

a::before {
   content: '';
   position: absolute;
   width: 50px;
   height: 900%;
   background: var(--clr);
   transition: 1s;
   animation: animate 2s linear infinite;
   animation-delay: calc(0.33s * var(--i));
   
}
a:hover:before{
   width: 120%;
}
@keyframes animate {
   0%
   {
       transform: rotate(0deg);
   }
   100%
   {
       transform: rotate(360deg);
   }
}

a::after {
   content: '';
   position: absolute;
   inset: 4px;
   background: #191c24;

   transition: 0.5;
   border-radius: 20px;
}
a:hover::after {
   background: var(--clr);
}

a span {
   position: relative;
   z-index: 1;
   font-size: 1 vw;
   color: #fff;
   opacity: 0.5;
   text-transform: uppercase;
   letter-spacing: 4px;
   transition: 0.5s;
}

a:hover span {
   opacity: 1;
}


</style>