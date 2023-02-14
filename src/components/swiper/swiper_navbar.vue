<template>
    <nav class="navbar swiper-nav ">
        <div class="navbar-brand-wrapper d-flex d-lg-none align-items-center justify-content-center">
            <a class="navbar-brand brand-logo-mini" href="index.html"><img src="../../assets/images/logo-mini.svg"
                    alt="logo" /></a>
        </div>
        <div class="navbar-menu-wrapper flex-grow d-flex align-items-stretch">
            <button class="navbar-toggler navbar-toggler align-self-center" type="button" data-toggle="minimize">
                <span class="mdi mdi-menu"></span>
            </button>
            <ul class="navbar-nav">
                <li class="nav-item">
                    <h3 class="m-0 align-self-center">
                        CONSUMPTION
                    </h3>
                </li>
            </ul>
            <ul class="navbar-nav navbar-nav-right">
                <li class="nav-item nav-settings d-none d-lg-block">
                    <a class="nav-link" href="#">
                        ENG
                    </a>
                </li>
                <li class="nav-item">
                    TIME DATE : {{ currentDate.toLocaleString('en-GB') }}
                </li>
            </ul>
            <button class="navbar-toggler navbar-toggler-right d-lg-none align-self-center" type="button"
                data-toggle="offcanvas">
                <span class="mdi mdi-format-line-spacing"></span>
            </button>
        </div>
    </nav>
</template>

<script>
import { inject } from 'vue';
import { provide } from 'vue';
export default {
    props: {
        headerSet: {
            type: String
        }
    },
    setup() {
        const headerSet = "CONSUMPTION";
        provide('setHeader',headerSet);

        const parentData = inject('parentData');
        return {
            parentData
        };
    },
    emits: ['update:headerSet'],
    data() {
        return {
            currentDate: new Date(),
            returnHeader: this.headerSet,
        }
    },
    computed: {
        localMessage: {
            get() {
                return this.headerSet
            },
            set() {
                this.$emit('update:headerSet', "CONSUMPTION")
            }
        }
    },
    created() {
        setInterval(() => {
            this.currentDate = new Date()
        }, 1000);
    }
}
</script>

<style>

</style>