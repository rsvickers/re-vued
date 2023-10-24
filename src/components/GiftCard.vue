<template>
    <div class="rounded bg-dark shadow">
        <img :src="giftProp.url" :alt="giftProp.tag" class="rounded-top">
        <div class="p-3">
            <h4 class="text-center">{{ giftProp.tag }}</h4>
        </div>
    </div>
</template>


<script>

// import { AppState } from '../AppState.js';
import { Gift } from '../models/Gift.js';

export default {
    props: {
        giftProp: { type: Gift, required: true }
    },
    setup() {
        return {

        }
    }


}
</script>


<style lang="scss" scoped>
img {
    height: 45vh;
    width: 100%;
    object-position: center;
}
</style>