<template>
<div class="col-6 d-flex flex-column">
  <h1 class="text-center text-white">Array Project</h1>
  
         <button class="btn btn-primary m-2" @click="storeFilter('year')">List with start year</button>
         <button class="btn btn-primary m-2" @click="storeFilter('Naypyidaw')">Display Naypyidaw</button>
         <button class="btn btn-primary m-2" @click="storeFilter('between')">List between 1002-2005</button>
</div>
</template>

<script>
export default {
  name: 'HelloWorld',
  methods:{
    storeFilter(filter) {
      this.$emit('filtered', filter);
    },
  }
  

}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
