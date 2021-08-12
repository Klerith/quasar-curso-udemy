<template>
  <q-item
    clickable
    tag="a"
    @click="navigateTo"
  >
    <q-item-section
      v-if="icon"
      avatar
    >
      <q-icon :name="icon" />
    </q-item-section>

    <q-item-section>
      <q-item-label>{{ title }}</q-item-label>
      <q-item-label caption>
        {{ caption }}
      </q-item-label>
    </q-item-section>
  </q-item>
</template>

<script>
import { defineComponent } from 'vue'
import { useRouter } from 'vue-router'

export default defineComponent({
  name: 'EssentialLink',
  props: {
    title: {
      type: String,
      required: true
    },

    caption: {
      type: String,
      default: ''
    },

    link: {
      type: String,
      default: '#'
    },

    icon: {
      type: String,
      default: ''
    }
  },
  setup( props ) {

    const router = useRouter()

    
    return {
      navigateTo() {

        props.link.startsWith('http')
          ? window.open( props.link, '_blank' )
          : router.push({ name: props.link })
        

      }
    }
  }
})
</script>
