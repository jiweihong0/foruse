
<template>
  <div class="about">
    <h1>This is an ab</h1>
    <button @click="fetchData">clickme!</button>
    <img :src="asd!=='12345'?asd.products.output[1].img:'123'" alt="asd" >
    <p>{{asd!=="12345"?asd.products.output[1].title:"wait"}}</p>
    <button @click="fetchData2">clickme for cal100!</button>
    <p>{{qwe!=="123"?qwe.async.output:"wait"}}</p>
  </div>
</template>
<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>

<script>

export default {
  name: 'AboutView',
  components: {},
  data() {
    return {
      asd:"12345",
      qwe:"123"
    };
  },
  computed: {},
  methods: {
      fetchData(){
        fetch('http://localhost:8088/products')
        .then(async res => { this.asd = await res.json()})
        .then(data => console.log(data))
      },
      fetchData2(){
        fetch('http://localhost:8088/cal100')
        .then(async res => {this.qwe = await res.json()})
        .then(data => console.log(data))
  }
  },
};
</script>