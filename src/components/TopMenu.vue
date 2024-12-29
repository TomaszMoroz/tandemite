<template>
  <div class="menu">
    <div class="menu_wrapper">
      <img :src="logo" alt="Logo" width="167" height="43" />
      <div class="menu_wrapper__btn_group">
        <a
          v-for="(btn, index) in buttons"
          :key="index"
          :href="btn.link"
          class="menu_wrapper__btn"
          >
          {{ btn.name }}
        </a>
      </div>
      <div class="menu_wrapper__icons_group">
        <div
          v-for="(icon, index) in icons"
          :key="index"
          :class="icon.rounded ? 'menu_wrapper__icon-rounded' : 'menu_wrapper__icon'"
          @click="navigateTo(icon.name)"
        >
          <img :src="require(`../assets/icons/${icon.name}.png`)"/>
          <span v-if="icon.badge" class="menu_wrapper__icon_badge">{{ shoppingBag.length }}</span>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>
import { ref } from 'vue'
import logo from '../assets/logo/kazus_logo.png'

const buttons = [
  { name: 'O Kazusie', link: '' },
  { name: 'O Firmie', link: ''},
  { name: 'Czasopisma', link: '' },
  { name: 'Szkolenia', link: '' },
  { name: 'Baza Wiedzy', link: '' },
  { name: 'Kazus TV', link: '' },
  { name: 'Kontakt', link: '' }
]

const icons = [
  { name: 'magnifying-glass', rounded: true },
  { name: 'user' },
  { name: 'bag', badge: true }
]

const shoppingBag = ref([])

const navigateTo = name => {
  // trigger modal or use router...
  return name
}
</script>
<style lang="sass" scoped>
$bg-white: #FFFFFF
$menu-border: solid 1px #F1F5F5

.menu
  display: flex
  align-items: center
  background-color: $bg-white
  border: $menu-border
  height: 90px

.menu_wrapper
  width: 100%
  display: flex
  align-items: center
  justify-content: space-between
  margin: 0 18.75%

// .menu_wrapper__btn_group
//   width: 66%

.menu_wrapper__btn
  font-family: Roboto
  color: #2E3838
  font-size: 14px
  text-decoration: none
  &:hover
    color: #0A655E

.menu_wrapper__btn + .menu_wrapper__btn
  margin: 0 20px

.menu_wrapper__icons_group
  display: flex
  justify-content: space-between
  align-items: center
  min-width: 126px

.menu_wrapper__icon
  position: relative
  cursor: pointer

.menu_wrapper__icon-rounded
  display: flex
  justify-content: center
  align-items: center
  width: 40px
  height: 40px
  background-color: #0A655E
  border-radius: 50%
  cursor: pointer

.menu_wrapper__icon-rounded img
  margin: auto

.menu_wrapper__icon_badge
  display: flex
  justify-content: center
  align-items: center
  position: absolute
  top: -5px
  right: -5px
  background: radial-gradient(circle, #0A655E, #025C55)
  color: white
  font-size: 10px
  border-radius: 50%
  min-width: 13px
  height: 13px
  text-align: center
</style>
