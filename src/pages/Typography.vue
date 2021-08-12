<template>
  <q-page class="flex column q-pa-md">

    <span class="text-h1">Headline 1</span>
    <span class="text-h2">Headline 2</span>
    <span class="text-h3">Headline 3</span>
    <span class="text-h4">Headline 4</span>
    <span class="text-h5">Headline 5</span>
    <span class="text-h6">Headline 6</span>

    <q-separator />

    <span class="text-subtitle1">Subtitle 1</span>
    <span class="text-subtitle2">Subtitle 2</span>

    <q-separator />
    <p class="text-body1">Quis occaecat irure labore aliqua anim dolore Lorem consequat ut minim ea in aliquip sit. Quis veniam cillum duis dolor. Pariatur et sit labore enim consectetur magna consectetur qui.</p>
    <p class="text-body2">Laboris Lorem velit magna ullamco ea sunt aute ullamco velit pariatur. Sit id cillum do excepteur eu tempor consectetur duis voluptate culpa magna ex eu. Quis nulla amet elit amet cupidatat adipisicing nulla enim et quis officia.</p>
    <q-separator />

    <span class="text-weight-thin">Veniam esse ex reprehenderit cillum elit.</span> 
    <span class="text-weight-light">Mollit proident esse est esse dolor aliquip nulla ea nostrud enim culpa Lorem.</span> 
    <span class="text-weight-regular">Culpa velit ullamco sunt aliqua enim excepteur incididunt mollit duis.</span> 
    <span class="text-weight-medium">Commodo mollit anim elit ea aliqua adipisicing.</span> 
    <span class="text-weight-bold">Elit voluptate reprehenderit sint ut fugiat sunt sit exercitation ad ex pariatur minim mollit.</span> 
    <span class="text-weight-bolder">Velit mollit dolore deserunt elit reprehenderit labore incididunt veniam est enim labore qui.</span> 

    <q-btn 
      color="primary"
      :label="sideMenuOpen ? 'Cerrar menú lateal' : 'Abrir menú lateral'"
      class="q-mt-md"
      @click="toggleSideMenu"
    />


  </q-page>
</template>

<script>
import { defineComponent } from 'vue';
import useUI from '../composables/useUI'


export default defineComponent({
  name: 'Typography',
  setup() {

      const { sideMenuOpen, toggleSideMenu } = useUI()


      return {
        sideMenuOpen, 
        toggleSideMenu,
      }
  }
})
</script>
