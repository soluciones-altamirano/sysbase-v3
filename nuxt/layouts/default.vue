<template>
  <div class="app">
    <AppHeader />
    <div class="app-body mt-1 pt-5">
      <Sidebar :navItems="nav"/>
      <main class="main">
        <!--<breadcrumb :list="list"/>-->
        <div class="container-fluid pt-4 pb-5">
          <nuxt />
        </div>
      </main>
      <!--<AppAside/>-->
    </div>
    <AppFooter class="fixed-bottom p-3"/>
  </div>
</template>

<script>
import nav from './menu'
import { Header as AppHeader,
    Sidebar,
    // Aside as AppAside,
    Footer as AppFooter,
    // Breadcrumb
} from '~/components/'

export default {
  name: 'full',
  components: {
    AppHeader,
    Sidebar,
    // AppAside,
    AppFooter,
    // Breadcrumb
  },
  data () {
    return {
      nav: nav.items
    }
  },
  computed: {
    name () {
      return this.$route.name
    },
    list () {
      return this.$route.matched
    }
  }
}
</script>