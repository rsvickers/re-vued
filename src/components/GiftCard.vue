<template>
    <div class="rounded bg-dark shadow">
        <img :src="giftProp.url" :alt="giftProp.tag" class="img-fluid rounded-top">
        <div class="p-3">
            <h4>{{ giftProp.tag }}</h4>
        </div>
    </div>
</template>


<script>

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


<style lang="scss" scoped></style>