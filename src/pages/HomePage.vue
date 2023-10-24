<template>
  <div class="container-fluid">
    <section class="row">
      <div class="col-12">
        <h1 class="text-center">Gifts</h1>
      </div>
    </section>
    <section class="row">

      <div v-for="gift in gifts" :key="gift.id" class="gifts col-md-6 p-3">
        <GiftCard :giftProp="gift" />
      </div>

    </section>
  </div>
</template>

<script>
import Pop from '../utils/Pop.js';
import { giftsService } from '../services/GiftsService.js'
import { computed, onMounted } from 'vue';
import { AppState } from '../AppState.js'
import GiftCard from '../components/GiftCard.vue';

export default {
  setup() {
    async function getGifts() {
      try {
        await giftsService.getGifts()
      } catch (error) {
        Pop.error(error)
      }
    }
    onMounted(() => {
      getGifts();
    });
    return {
      gifts: computed(() => AppState.gifts)
    };
  },
  components: { GiftCard }
}
</script>

<style scoped lang="scss"></style>
