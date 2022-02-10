<template>
  <div>
    
    <v-row no-gutters>
      <v-col v-for="(product, index) in list_product" :key="index" cols="sm">
        <v-card class="pa-2 mx-auto mb-5" outlined tile max-width="400">
          <v-img
            class="white--text align-end"
            height="200px"
            :src="product.img_pic"
          >
          </v-img>
          <v-card-title class="name_font">
            <h3>{{ product.pro_name }}</h3>
          </v-card-title>

          <v-card-text class="text--primary">
            <h2>{{ product.price }}บาท</h2>

            <div>{{ product.tell }}</div>
          </v-card-text>

          <v-card-actions>
            <v-spacer />
            <v-btn color="orange" text class="justify-center" @click="explor(product.id)">ดูสินค้า</v-btn>
            <v-spacer />
            <v-btn color="primary" elevation="3" rounded x-large class="" @click="buy_TOaddMoney(product.price)">ซื้อ</v-btn>
         </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  name: "Allproduct",
  data: () => ({
    list_product: [
      {
        id: "001",
        pro_name: "มาม่าต้ม",
        price: 10,
        img_pic:
          "https://static.bigc.co.th/media/catalog/product/8/8/8850987101205_1_2.jpg",
        tell: "มาม่าอร่อย",
      },
      {
        id: "002",
        pro_name: "ข้าวผัด",
        price: 30,
        img_pic: "https://www.boldsky.com/img/2012/08/17-cook.jpg",
        tell: "ข้าวผัดอร่อย",
      },
      {
        id: "003",
        pro_name: "ต้มยำกุ้ง",
        price: 50,
        img_pic: "https://food.mthai.com/app/uploads/2016/10/Tomyum.jpg",
        tell: "ต้มยำกุ้งอร่อย",
      },
      {
        id: "004",
        pro_name: "ผัดฉ่า",
        price: 40,
        img_pic:
          "https://img.wongnai.com/p/800x0/2018/12/17/64d37477fe5646c39a96e66638434d09.jpg",
        tell: "ผัดฉ่าอร่อย",
      },
      {
        id: "005",
        pro_name: "สุกี้",
        price: 100,
        img_pic:
          "https://elainesporkandpie.com/wp-content/uploads/2020/12/%E0%B8%AA%E0%B8%B8%E0%B8%81%E0%B8%B5%E0%B9%89%E0%B8%9C%E0%B8%B1%E0%B8%81%E0%B8%A3%E0%B8%A7%E0%B8%A1%E0%B8%9B%E0%B8%B0%E0%B8%9A%E0%B8%99-800x445.jpg",
        tell: "สุกี้อร่อย",
      },
      {
        id: "006",
        pro_name: "หมูกระทะ",
        price: 200,
        img_pic:
          "https://img.wongnai.com/p/984x0/2019/10/31/b9e09b9a9df6456db2360a45f18f682a.jpg",
        tell: "หมูกระทะอร่อย",
      },
    ],
  }),
  methods:{
    explor(i){
       this.$emit("explor_pro",i);
    
    },
    buy_TOaddMoney(i){
      
      this.$emit("buy",i);
    }
  }
};
</script>

<style>
.name_font {
  color: black;
}
.position {
  position: relative;
  left: 280px;
}
</style>