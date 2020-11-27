<template>
  <div class="container">
    <div class="row d-flex">
      <HelloWorld @filtered="setFilter" />
      <resultShow :filterArray="filter" :items="companies" />
    </div>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import resultShow from "./components/result";

export default {
  components: {
    HelloWorld,
    resultShow,
  },
  data: () => ({
    filter: null,
    companies: [
      {
        name: "Company One",
        category: "Finance",
        start: 1981,
        end: 2003,
        location: "Yangon",
      },
      {
        name: "Company Two",
        category: "Retail",
        start: 1992,
        end: 2008,
        location: "Mandalay",
      },
      {
        name: "Company Three",
        category: "Auto",
        start: 1999,
        end: 2007,
        location: "Naypyidaw",
      },
      {
        name: "Company Four",
        category: "Retail",
        start: 1989,
        end: 2010,
        location: "Naypyidaw",
      },
      {
        name: "Company Five",
        category: "Technology",
        start: 2009,
        end: 2014,
        location: "Mandalay",
      },
      {
        name: "Six",
        category: "Finance",
        start: 1987,
        end: 2010,
        location: "Nyipyidaw",
      },
      {
        name: "Company Seven",
        category: "Auto",
        start: 1986,
        end: 1996,
        location: "Yangon",
      },
      {
        name: "Company Eight",
        category: "Technology",
        start: 2011,
        end: 2016,
        location: "Nyipyidaw",
      },
      {
        name: "Nine",
        category: "Retail",
        start: 1981,
        end: 1989,
        location: "Mandalay",
      },
    ],
  }),
  created() {},
  methods: {
    setFilter(filter) {
      this.filter = filter;
    },
  },
  computed: {
    filteredList() {
      switch (this.filter) {
        case "year":
          return this.companies.sort((a, b) => a.start - b.start);
          break;
        case "Naypyidaw":
          return this.companies.filter((loc) => loc.location === "Naypyidaw");
          break;
        case "between":
          return this.companies.filter((loc) => loc.start > 1992);
          break;
        default:
          return this.companies;
          break;
      }

      //   if(this.inputText) {
      //  return   this.companies = this.companies.filter(d=>{
      //      let  allOf = [d.name.toLowerCase(),d.category.toLowerCase(),d.location.toLowerCase()]
      //    //   return allOf.toString().indexOf(this.inputText.toLowerCase())>-1
      // return allOf.includes(this.inputText.toLowerCase())

      //       });

      // }

      return this.companies;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
