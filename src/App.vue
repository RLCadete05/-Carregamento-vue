<template>
  <div id="app">
    <PageLoader />

    <h1>Discover</h1>

    <div>
      <iframe width="560" height="315" src="https://www.youtube.com/embed/iCk22ADjQPU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
    </div>

    <div class="grid-wrapper">
      <Card v-for="(card, index) in cards" 
            :key="'card'+index"
            :item="card" :index="index" />
    </div>
  </div>
</template>

<script>
import Card from './components/Card'
import PageLoader from './components/PageLoader'

export default {
  data: () => {
    return {
      cards: [
        { img: '/cao1.jpg', grid: 'card-2-1' },
        { img: '/cao2.jpg', grid: 'card-1-1' },
        { img: '/cao3.jpg', grid: 'card-1-1' },
        { img: '/cao4.jpg', grid: 'card-2-1' },
        /*{ img: '/img-5.jpg', grid: 'card-1-1' },
        { img: '/img-6.jpg', grid: 'card-1-1' }*/
      ],
    }
  },
  components: {
    Card,
    PageLoader
  }
}
</script>

<style lang="scss">
  * {
    font-size: 1rem;
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }

  h1 { font-size: 2rem; }

  body {
    width: 100%;
    font-family: 'Segoe UI', Tahoma;
    background-color: #efefef;
    color: #333;
  }

  #app {
    padding: 10px;
    width: 100%;
    min-height: 100vh;
  }

  .grid-wrapper {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-gap: 10px;
  }
</style>
