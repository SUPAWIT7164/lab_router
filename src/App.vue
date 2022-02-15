<template>
  <div id="app">
    <div class="container">
      <h2 align="center">GenshinShop</h2>
      <hr />
      <div class="row">
        <div class="col-md-3" v-for="item in products" :key="item">
          <div class="card h-100">
            <img
              :src="item.image"
              class="card-img-top"
              width="200"
              height="300,"
            />
            <div class="card-body">
              <h3 class="card-title">{{ item.name }}</h3>
              <p class="card-text">ราคา {{ item.Price }} บาท</p>
            </div>
            <div class="card-footer"></div>
            <input
              type="checkbox"
              class="form-control"
              @change="selected(item)"
            />
          </div>
        </div>
      </div>
      <h2>ยอดชำระเงิน {{total()}} บาท</h2>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      products: [
        {
          id: 1,
          name: "Figure Amber",
          Price: 10000,
          image:
            "https://cdna.artstation.com/p/assets/images/images/033/146/090/large/gerom-20201221-142547.jpg?1608567351",
          active: false,
        },
        {
          id: 2,
          name: "Figure Beidou",
          Price: 13000,
          image:
            "https://preview.redd.it/mpcgjfuguwl71.jpg?width=640&crop=smart&auto=webp&s=c8d106d5dbe06b71061b9b718da03733727fbc29",
          active: false,
        },
        {
          id: 3,
          name: "Figure Keqing",
          Price: 12000,
          image: "https://cu.lnwfile.com/q9644m.jpg",
          active: false,
        },
        {
          id: 4,
          name: "Figure Mona",
          Price: 8500,
          image:
            "https://images.goodsmile.info/cgm/images/product/20210712/11468/87048/large/63da58e1f78ad22517c964a4d559f452.jpg",
          active: false,
        },
        {
          id: 5,
          name: "Figure Ganyu",
          Price: 8000,
          image: "https://cj.lnwfile.com/so3s6l.jpg",
          active: false,
        },
        {
          id: 6,
          name: "Figure Ningguang",
          Price: 10000,
          image:
            "https://www.thecollectorbase.sg/wp-content/uploads/2021/06/Genshin-Impact-1_7-Figure-Ningguang-3-600x600.jpeg",
          active: false,
        },
        {
          id: 7,
          name: "Figure Klee",
          Price: 5000,
          image:
            "https://th-live-05.slatic.net/p/02d841de7957177fb534ee66d787860a.jpg_720x720q80.jpg_.webp",
          active: false,
        },
        {
          id: 8,
          name: "Figure barbara",
          Price: 7000,
          image:
            "https://i.lagmcdn.com/latestappgames/20211229/1476080641706692608.jpeg",
          active: false,
        },
      ],
    };
  },
  methods: {
    selected: function (item) {
      item.active = !item.active;
    },
    total: function () {
      var sum = 0;
      this.products.forEach(function (item) {
        if (item.active) {
          sum += item.Price;
        }
      });
      return sum;
    },
  },
};
</script>
