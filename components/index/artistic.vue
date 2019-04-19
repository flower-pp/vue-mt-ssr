<template>
  <section class="m-istyle">
    <dl @mouseover="over">
      <dt>有格调</dt>
      <dd :class="{active:kind==='all'}" kind="all" keyword="景点">全部</dd>
      <dd :class="{active:kind==='part'}" kind="part" keyword="美食">约会聚餐</dd>
      <dd :class="{active:kind==='spa'}" kind="spa" keyword="丽人">丽人SPA</dd>
      <dd :class="{active:kind==='movie'}" kind="movie" keyword="电影">电影演出</dd>
      <dd :class="{active:kind==='travel'}" kind="travel" keyword="旅游">品质出游</dd>
    </dl>
    <ul class="ibody">
      <li v-for="item in cur" :key="item.title">
        <el-card :body-style="{ padding: '0px' }" shadow="never">
          <img :src="item.img" class="image">
          <ul class="cbody">
            <li class="title">{{ item.title }}</li>
            <li class="pos">
              <span>{{ item.pos }}</span>
            </li>
            <li class="price">
              ￥
              <em>{{ item.price }}</em>
              <span>/起</span>
            </li>
          </ul>
        </el-card>
      </li>
    </ul>
  </section>
</template>
<script>
export default {
  data: () => {
    return {
      kind: "all",
      list: {
        all: [
          {
            title: "日升昌酒店",
            pos: "学校周边",
            price: "530",
            img:
              "http://p0.meituan.net/scarlett/dd40062805e73a876692b9589339b1c6223571.png@460w_260h_1e_1c",
            url: "//abc.com"
          },
          {
            title: "必胜客",
            pos: "中六乐购店",
            price: "88",
            img:
              "http://p1.meituan.net/msmerchant/e79b718e32bdf3e2f2da447001a68d5d1591138.jpg@460w_260h_1e_1c",
            url: "//abc.com"
          },
          {
            title: "电影院",
            pos: "车陂国际",
            price: "88",
            img:
              "http://p0.meituan.net/deal/__8738457__1198596.jpg@460w_260h_1e_1c",
            url: "//abc.com"
          }
        ],
        part: [
          {
            title: "同湘会",
            pos: "直营23分店",
            price: "98",
            img:
              "http://p1.meituan.net/msmerchant/af8a048c1333e631a153c10b30a6bd5d523049.jpg@460w_260h_1e_1c",
            url: "//abc.com"
          },
          {
            title: "必胜客",
            pos: "中六乐购店",
            price: "88",
            img:
              "http://p1.meituan.net/msmerchant/e79b718e32bdf3e2f2da447001a68d5d1591138.jpg@460w_260h_1e_1c",
            url: "//abc.com"
          },
          {
            title: "披萨",
            pos: "xx分店",
            price: "188",
            img:
              "http://p0.meituan.net/msmerchant/d2188130de2de238eb324058cf5be095426775.jpg@460w_260h_1e_1c",
            url: "//abc.com"
          }
        ],
        spa: [
          {
            title: "同湘会",
            pos: "直营23分店",
            price: "98",
            img:
              "http://p1.meituan.net/msmerchant/af8a048c1333e631a153c10b30a6bd5d523049.jpg@460w_260h_1e_1c",
            url: "//abc.com"
          },
          {
            title: "必胜客",
            pos: "中六乐购店",
            price: "88",
            img:
              "http://p1.meituan.net/msmerchant/e79b718e32bdf3e2f2da447001a68d5d1591138.jpg@460w_260h_1e_1c",
            url: "//abc.com"
          },
          {
            title: "披萨",
            pos: "xx分店",
            price: "188",
            img:
              "http://p0.meituan.net/msmerchant/d2188130de2de238eb324058cf5be095426775.jpg@460w_260h_1e_1c",
            url: "//abc.com"
          }
        ],
        movie: [
          {
            title: "同湘会",
            pos: "直营23分店",
            price: "98",
            img:
              "http://p1.meituan.net/msmerchant/af8a048c1333e631a153c10b30a6bd5d523049.jpg@460w_260h_1e_1c",
            url: "//abc.com"
          },
          {
            title: "必胜客",
            pos: "中六乐购店",
            price: "88",
            img:
              "http://p1.meituan.net/msmerchant/e79b718e32bdf3e2f2da447001a68d5d1591138.jpg@460w_260h_1e_1c",
            url: "//abc.com"
          },
          {
            title: "披萨",
            pos: "xx分店",
            price: "188",
            img:
              "http://p0.meituan.net/msmerchant/d2188130de2de238eb324058cf5be095426775.jpg@460w_260h_1e_1c",
            url: "//abc.com"
          }
        ],
        travel: [
          {
            title: "同湘会",
            pos: "直营23分店",
            price: "98",
            img:
              "http://p1.meituan.net/msmerchant/af8a048c1333e631a153c10b30a6bd5d523049.jpg@460w_260h_1e_1c",
            url: "//abc.com"
          },
          {
            title: "必胜客",
            pos: "中六乐购店",
            price: "88",
            img:
              "http://p1.meituan.net/msmerchant/e79b718e32bdf3e2f2da447001a68d5d1591138.jpg@460w_260h_1e_1c",
            url: "//abc.com"
          },
          {
            title: "披萨",
            pos: "xx分店",
            price: "188",
            img:
              "http://p0.meituan.net/msmerchant/d2188130de2de238eb324058cf5be095426775.jpg@460w_260h_1e_1c",
            url: "//abc.com"
          }
        ]
      }
    };
  },
  computed: {
    cur: function() {
      return this.list[this.kind];
    }
  },
  // async mounted() {
  //   let self = this;
  //   let {
  //     status,
  //     data: { count, pois }
  //   } = await self.$axios.get("/search/resultsByKeywords", {
  //     params: {
  //       keyword: "景点",
  //       city: self.$store.state.geo.position.city
  //     }
  //   });
  //   if (status === 200 && count > 0) {
  //     let r = pois
  //       .filter(item => item.photos.length)
  //       .map(item => {
  //         return {
  //           title: item.name,
  //           pos: item.type.split(";")[0],
  //           price: item.biz_ext.cost || "暂无",
  //           img: item.photos[0].url,
  //           url: "//abc.com"
  //         };
  //       });
  //     self.list[self.kind] = r.slice(0, 9);
  //   } else {
  //     self.list[self.kind] = [];
  //   }
  // },
  methods: {
    over: async function(e) {
      let dom = e.target;
      let tag = dom.tagName.toLowerCase();
      let self = this;
      if (tag === "dd") {
        this.kind = dom.getAttribute("kind");
        let keyword = dom.getAttribute("keyword");
      //   let {
      //     status,
      //     data: { count, pois }
      //   } = await self.$axios.get("/search/resultsByKeywords", {
      //     params: {
      //       keyword,
      //       city: self.$store.state.geo.position.city
      //     }
      //   });
      //   if (status === 200 && count > 0) {
      //     let r = pois
      //       .filter(item => item.photos.length)
      //       .map(item => {
      //         return {
      //           title: item.name,
      //           pos: item.type.split(";")[0],
      //           price: item.biz_ext.cost || "暂无",
      //           img: item.photos[0].url,
      //           url: "//abc.com"
      //         };
      //       });
      //     self.list[self.kind] = r.slice(0, 9);
      //   } else {
      //     self.list[self.kind] = [];
      //   }
      }
    }
  }
};
</script>
<style lang="scss">
@import "@/assets/css/index/artistic.scss";
</style>
