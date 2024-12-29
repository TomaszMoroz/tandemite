<template>
  <div class="header">
    <div class="header__text">
      <div class="header__text_title">
        {{ title }}
      </div>
      <div class="header__text_text_bold">
        {{ textBold }}
      </div>
      <div class="header__text_text_regular">
        {{ textRegular }}
      </div>
    </div>
    <img 
      :src="require('../assets/layout images/magazines2x.png')"
      class="header__image"
      height="408"
      width="428"
    />
  </div>
</template>

<script setup>
const title = 'Czasopisma'

const textBold = `Mamy przyjemność oddać w Państwa ręce kolejny numer „Kazusu Podatkowego”, który 
tym razem poświęcony jest w dużej części zmianom w podatkach w roku 2019.`

const textRegular = `Omówiliśmy najważniejsze zagadnienia takie jak zmiany w zakresie rozliczania kosztów 
używania samochodów osobowych, wprowadzenie „exit tax” czy zmiany dotyczące poboru 
podatku u źródła na gruncie podatków dochodowych, poświęcając im odrębne artykuły.`
</script>

<style lang="sass" scoped>
$header_title_fontsize_lg: 56px
$header_text_fontsize_lg: 14px
$header_textcolor: #FFFFFF

.header
  position: relative
  display: flex
  justify-content: space-between
  width: 100%
  height: 360px
  background-color: #0A655E
  background-image: url('../assets/logo/header_logo.svg')
  background-repeat: no-repeat
  background-position: 85px -80px

.header__text
  display: flex
  height: 80%
  flex-direction: column
  justify-content: space-between
  white-space: pre-line
  margin: 0 0 0 18.75%

.header__text_title
  font-family: Roboto
  color: $header_textcolor
  font-size: $header_title_fontsize_lg
  margin: 63px 0 32px 0

.header__text_text_bold
  font-family: Roboto-Bold
  color: $header_textcolor
  font-size: $header_text_fontsize_lg
  margin-bottom: 32px

.header__text_text_regular
  font-family: Roboto
  color: $header_textcolor
  font-size: $header_text_fontsize_lg

.header__image
  position: relative
  bottom: -15%
  left: -5%
  margin: 0 18.75% 0 0

</style>