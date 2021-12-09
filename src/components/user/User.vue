<template>
  <div class="user">
    <div>
      <div class="listUsers" v-for="item in listUsers" :key="item.id">
        <div>{{item.username}}</div>
      </div>
      <div class="listUsers" v-if="listUsers == ''">
          <p>not matches</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'user',
  props: {
    listUsers: [],
  }
}
</script>

<style>
 .listUsers{
   border: 1px solid rgb(168, 166, 166);
   padding: 10px;
 }
</style>
