<template>
  <header>
      <div class="navbar container">
        <div class="logo">
          <a href="/"><img src="@/assets/img/dc-logo.png" alt="logo.png"></a>
        </div>
        <div class="navbar-list">
          <ul class="navbar-items">
            <li v-for="(link, index) in links" :key="index" class="navbar-item" :class="(link == currentLink) ? 'active' : null" @click="currentPage(index)">
              <a :href="link.url">{{link.text.toUpperCase()}}</a>
            </li>
          </ul>
        </div>
      </div>
  </header>
</template>

<script>
import { headerLinks} from '@/assets/data/Links.js'
export default {
  name: 'Header',
  data(){
    return{
      links: headerLinks,
      currentLink: '',
    }
  },
  methods: {
    currentPage(i){
      let tmpLink = this.links[i];
      this.currentLink = tmpLink;
    }
  },
  mounted(){
    this.currentLink = this.links[1];
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "@/style/general";

.header-top{
  height: 60px; 
  width: 100%; 
  background-color: $black;

  .container{
     @include center(vertical); 
     justify-content: flex-end;
  }
}
.navbar{
  height: 120px; 
  @include center(vertical); 
  justify-content: space-between;
  }

.logo {
  width: 90px;
  padding: 20px 0px;

  img{
    width: 100%;
  }

}
.navbar-items{list-style: none; display: flex; font-size: $fs-xs ; font-weight: $bold; line-height: 100px;}
.navbar-item{
  padding: 0px 15px;
  color: $black;
  cursor: pointer;
  border-bottom: 4px solid transparent;
  a{
    text-decoration: none;
    color: inherit;

    &:hover{
      color: $blue;
    }

  }

  &:hover{
    color: $txt-blue;
    border-bottom: 4px solid $blue;
  }

  &.active{
      color: $blue;
      border-bottom: 4px solid $blue;
  }

}



</style>
