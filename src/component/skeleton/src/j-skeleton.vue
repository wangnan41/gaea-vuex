<template>
    <div class="vue-skeleton-loading">
        <div class="skeleton-bac-animation"></div>
        <slot></slot>
    </div>
</template>

<script>
    import circleSkeleton from './basic/circle.vue';
    import squareSkeleton from './basic/square.vue';
    export default {
        data() {
            return {};
        },
        components: {
            circleSkeleton,
            squareSkeleton
        }
    }
</script>

<style lang="scss">
    .vue-skeleton-loading {
        
        background:#fff;
        position:fixed;
        top:0;
        right:0;
        bottom:0;
        left:0;
        z-index: 9999;
        @keyframes backpos {
            from {
                background-position-x: -200px;
            }

            to {
                background-position-x: calc(200px + 100%);
            }

        }
        .skeleton-bac-animation {
            position: absolute;
            z-index: auto;
            width: 100%;
            height: 100%;
            background: linear-gradient(to right, rgba(255,255,255,0), rgba(255,255,255,0.5) 50%, rgba(255,255,255,0) 80%);
            background-size: 30% 100%;
            background-repeat: no-repeat;
            -webkit-animation: backpos 0.9s ease-in-out 0s infinite;
            animation: backpos 0.9s ease-in-out 0s infinite;
        }
    }
</style>