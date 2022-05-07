<template>
  <nav class="nav">
    <div class="nav__container">
      <div class="nav__logo">
        <img src="../assets/images/logo.png" class="nav__logo__image" />
      </div>
      <div class="nav__menu">
        <ul class="nav__menu__list">
          <li class="nav__menu__list__item">
            Dashboard
          </li>
          <li class="nav__menu__list__item">
            Farmers
          </li>
          <li class="nav__menu__list__item">
            Blocks
          </li>
          <li class="nav__menu__list__item">
            Tools
          </li>
          <li class="nav__menu__list__item">
            Info
          </li>
        </ul>
      </div>
      <div class="nav__actions">
        <i
          class="theme-toggle"
          @click="$emit('toggleDarkMode')">
          <Brightness6 />
        </i>
        <button class="btn btn--small btn--primary">Join</button>
      </div>
    </div>
  </nav>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Brightness6 from 'vue-material-design-icons/Brightness6.vue';
export default defineComponent({
  name: 'NavigationComponent',
  components:{
    Brightness6
  }

});
</script>

<style scoped lang="scss">
.nav{
  padding-top:.5rem;
  padding-bottom:.5rem;
  border-bottom:solid 4px var(--info);
  background-color: var(--nav-background-color);
  &__logo{
    display: flex;
    align-items:center;
    &__image{
      max-width:250px;
      height:auto;
    }
  }
  &__container{
    display:grid;
    grid-template-columns: 1fr 1fr 1fr;
    max-width:1140px;
    margin: 0 auto;
  }
  &__menu{
    display: flex;
    align-items:center;
    justify-content: center;
    &__list{
      list-style: none;
      padding:0;
      display:flex;
      &__item{
        margin-right:1rem;
        font-weight:600;
        &:last-child{
          margin-right:0;
        }
      }
    }
  }
  &__actions{
    display: flex;
    justify-content: end;
    align-items:center;

  }
}

.theme-toggle{
  margin-right:1rem;
  cursor:pointer;
}
</style>
