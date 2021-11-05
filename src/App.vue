<template>
  <Header />
  <div class="home">Hello World</div>
</template>

<script>
import Header from "@/components/Header";
export default {
  components: {
    Header,
  },
  data() {
    return {
      loading: true,
      title: "Global",
      dataDate: "",
      state: {},
      countires: [],
      loadingImage: require(""),
    };
  },
  methods: {
    async fetchCovidData() {
      const res = await fetch("https://api.covid19api.com/summary");
      const data = await res.json();
      return data;
    },
  },
  async created() {
    const data = await this.fetchCovidData();
    console.log(data);
  },
};
</script>
