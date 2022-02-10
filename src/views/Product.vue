<template>
  <container>
    
    <v-card class="d-flex mb-6" color="lighten-2" flat tile>
      <div
        v-for="n in 2"
        :key="n"
        :class="n === 1 && 'mr-auto'"
        class="pa-2"
        outlined
        tile
      >
        <h1 v-if="n == 1">Product</h1>
        <Buy :buy="money" v-if="n == 2"></Buy>
      </div>
    </v-card>

    <All @explor_pro="see_pro" @buy="addMoney" class=""></All>
  </container>
</template>

<script>
import All from "../components/Sub_product.vue";
import Buy from "../components/BuyProduct.vue";

export default {
  components: {
    All,
    Buy,
  },
  data: () => ({
    currun_id: "",
    money: 0,
  }),
  methods: {
    see_pro(id_pro) {
      this.$router.push({ name: "detail", params: { Pid: id_pro } });
    },
    addMoney(i) {
      
      this.money = i + this.money;
    },
  },
};
</script>

<style>
</style>