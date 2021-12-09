<template>
  <div class="searchBox">
        <input type="text" @change="onChange" @keyup="onChange" v-model="filterInput">
  </div>
</template>

<script>

export default {
  name: 'searchBox',
  data() {
    return {
      filterInput:''
    }
  },
  methods: {
    onChange: function(){
      this.$emit('search', this.filterInput)
    }
  },
}
</script>

<style>
  .searchBox{
    border: 1px solid rgb(168, 166, 166);
    padding: 10px;
  }
  .searchBox input{
    border-radius: 20px;
    width: 90%;
  }
</style>