<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="las la-bars"
          aria-label="Menu"
          @click="toggleSideMenu"
        />

        <q-toolbar-title>
          Quasar App
        </q-toolbar-title>

        <!-- TODO: <div>Quasar v{{ $q.version }}</div> -->
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="sideMenuOpen"
      show-if-above
      bordered
      class="bg-grey-1"
    >
      <q-list>
        <q-item-label
          header
          class="text-grey-8"
        >
          Essential Links
        </q-item-label>

        <EssentialLink
          v-for="link in linksList"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>

import { defineComponent } from 'vue'

import EssentialLink from 'components/EssentialLink.vue'
import { linksList } from '../router/link-list'

import useUI from '../composables/useUI'

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink
  },

  setup () {

    const { sideMenuOpen, toggleSideMenu } = useUI()


    return {
      linksList,
      sideMenuOpen,
      toggleSideMenu,
    }
  }
})
</script>
