<script>

import axios from 'axios';
import HeaderComp from "./components/HeaderComp.vue";
import MainComp from "./components/MainComp.vue";

import { store } from './store'


export default{
  name: "app",
  data(){
    return{
      store
    }
  },
  components: {
    HeaderComp,
    MainComp
  },
  created() {
    this.callApi();
  },
  methods: {
    callApi(){
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=3')
        .then((res) => {
          console.log( res.data.data )
          this.store.arrayCarte = res.data.data
        })
    }
  }
}
</script>

<template>

<HeaderComp/>
<MainComp/>
</template>

<style>
</style>
