<template>
  <div id="app">
    <!-- <label>
      切换为横向
      <input type="checkbox" v-model="landscape" value="1">
    </label>-->
    <!-- <TreeChart :json="data" :class="{landscape: landscape.length}" @click-node="clickNode"/> -->
    <TreeChart id="chart" :json="data" @click-node="clickNode"/>
  </div>
</template>

<script>
import TreeChart from "@/components/TreeChart";

export default {
  name: "app",
  components: {
    TreeChart
  },
  data() {
    return {
      landscape: [],
      data: {
        name: "root",
        title: "111",
        date: "2019-02-27",
        person: "普通会员",
        level: "层1",
        extend: true,
        children: [
          {
            name: "children1",
            title: "333",
            date: "2019-02-27",
            person: "普通会员",
            level: "层2",
            extend: true
          },
          {
            name: "children2",
            title: "4444",
            date: "2019-02-27",
            person: "普通会员",
            level: "层2",
            extend: true,
            children: [
              {
                name: "grandchild",
                title: "555",
                date: "2019-02-27",
                person: "普通会员",
                level: "层3"
              },
              {
                name: "grandchild2",
                title: "666",
                date: "2019-02-27",
                person: "普通会员",
                level: "层3"
              },
              {
                name: "grandchild3",
                title: "777",
                date: "2019-02-27",
                person: "普通会员",
                level: "层3"
              }
            ]
          }
        ]
      }
    };
  },
  methods: {
    clickNode: function(node) {
      // eslint-disable-next-line
      console.log(node);
    }
  },
  mounted() {
    let that = this;
    window.addEventListener("scroll", function() {
      // eslint-disable-next-line
      var chart = document.getElementById("chart");
      // eslint-disable-next-line
      console.log(that.data);
      // console.log(chart.scrollTop);
    });
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  list-style: none;
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
#app .avat {
  border-radius: 2em;
  border-width: 2px;
}
#app .name {
  font-weight: 700;
}
</style>
