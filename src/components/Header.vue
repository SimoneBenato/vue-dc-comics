<template>
  <div id="header">
    <img src="@/images/dc-logo.png" alt="">

    <!-- lista links -->
    <ul>
      <li v-for="(link, index) in links" :key="index">
        <a href="">{{ link.nome }}</a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      links: [
        {
          nome: 'CHARACTERS',
          active: false,
        },
        {
          nome: 'COMICS',
          active: true,
        },
        {
          nome: 'MOVIE',
          active: false,
        },
        {
          nome: 'TV',
          active: false,
        },
        {
          nome: 'GAMES',
          active: false,
        },
        {
          nome: 'COLLECTIBLES',
          active: false,
        },
        {
          nome: 'VIDEOS',
          active: false,
        },
        {
          nome: 'FANS',
          active: false,
        },
        {
          nome: 'NEWS',
          active: false,
        },
        {
          nome: 'SHOP',
          active: false,
        }
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  #header {
    display: flex;
    justify-content: space-between;
    width: 70%;
    margin: 0 auto;
    padding: 15px 0;
    align-items: center;
    height: 100px;

    ul li {
      list-style: none;
      display: inline-block;
      padding: 1rem;

      a {
        text-decoration: none;
        color: rgb(70, 70, 70);

        &:hover {
          color: rgb(2, 130, 249);
        }
      }
    }
  }
</style>
