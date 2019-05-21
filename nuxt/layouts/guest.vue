<template>
  <div class="app">
      <AppHeader />
      <nuxt />
      <AppFooter class="fixed-bottom p-3"/>
  </div>
</template>

<script>
import nav from './menu'
import { Header as AppHeader,
    Footer as AppFooter,
} from '~/components/'

export default {
  name: 'full',
  components: {
    AppHeader,
    AppFooter
  }
}
</script>