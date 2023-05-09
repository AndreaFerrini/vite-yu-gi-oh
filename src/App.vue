<script>

import axios from 'axios';
import HeaderComp from "./components/HeaderComp.vue";
import MainComp from "./components/MainComp.vue";
import SearchCards from "./components/SearchCards.vue";


import { store } from '../src/store'


export default{
  name: "app",
  data(){
    return{
      store
    }
  },
  components: {
    HeaderComp,
    MainComp,
    SearchCards
  },
  created() {
    this.callApi();
  },
  methods: {
    callApi(){
      if (store.valueArchetype !== '' ){
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=${encodeURIComponent(store.valueArchetype)}')
          .then((res) => {
            console.log( res.data.data )
            this.store.arrayCarte = res.data.data
      })
    } else {
        axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=3")
          .then((res) => {
            console.log(res.data.data)
            this.store.arrayCarte = res.data.data
          })
      }  
    }
  },
}
</script>

<template>

<HeaderComp/>
<SearchCards @nomeEmit="callApi()"/>
<MainComp/>
</template>

<style>
</style>
