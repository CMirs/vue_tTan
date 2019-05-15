<template>
    <div>
        <Gheader></Gheader>
        <div class="wrap">
            <div class="wrap_left">
                <ol>
                    <li></li>
                    <li></li>
                    <li></li>
                    <li></li>
                    <li></li>
                    <li></li>
                    <li></li>
                    <li></li>
                    <li></li>
                    <li></li>
                </ol>
            </div>
        </div>

    </div>

</template>
<script>
    import Gheader from '../components/Gheader.vue';
    export default {
        components: {
            Gheader
        },
        data() {
            return {

            };
        }
    }
</script>
<style scoped>
    .wrap {
        position: absolute;
        z-index: 1;
        bottom: 0;
        left: 0;
        width: 100%;
        height: 93%;
        display: -webkit-box;
        display: -ms-flexbox;
        display: flex;
    }
</style>