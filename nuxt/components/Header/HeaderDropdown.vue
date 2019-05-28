<template>
      <b-nav-item-dropdown right no-caret>
        <template slot="button-content">
          <img src="~static/img/avatars/1.jpg" class="img-avatar" alt="admin@bootstrapmaster.com">
        </template>
        <span v-show="authenticated">
            <b-dropdown-header tag="div" class="text-center"><strong>Cuenta</strong></b-dropdown-header>
            <b-dropdown-item><i class="fa fa-bell-o"></i> Actualizaciones<b-badge variant="info">{{itemsCount}}</b-badge></b-dropdown-item>
            <b-dropdown-item><i class="fa fa-envelope-o"></i> Mensajes<b-badge variant="success">{{itemsCount}}</b-badge></b-dropdown-item>
            <b-dropdown-item><i class="fa fa-tasks"></i> Tareas<b-badge variant="danger">{{itemsCount}}</b-badge></b-dropdown-item>
            <b-dropdown-item><i class="fa fa-comments"></i> Comentarios<b-badge variant="warning">{{itemsCount}}</b-badge></b-dropdown-item>
            <b-dropdown-header tag="div" class="text-center"><strong>Configuraciones</strong></b-dropdown-header>
            <b-dropdown-item><i class="fa fa-user"></i> Perfil</b-dropdown-item>
            <b-dropdown-item><i class="fa fa-wrench"></i> Configuración</b-dropdown-item>
            <b-dropdown-item><i class="fa fa-usd"></i> Pagos<b-badge variant="secondary">{{itemsCount}}</b-badge></b-dropdown-item>
            <b-dropdown-item><i class="fa fa-file"></i> Proyectos<b-badge variant="primary">{{itemsCount}}</b-badge></b-dropdown-item>
            <b-dropdown-divider></b-dropdown-divider>
            <b-dropdown-item><i class="fa fa-shield"></i> Eliminar Cuenta</b-dropdown-item>
            <b-dropdown-item @click.prevent="singOut"><i class="fa fa-lock"></i> Salir</b-dropdown-item>
        </span>
          <span v-show="!authenticated">
              <b-dropdown-header tag="div" class="text-center"><strong>Cuenta</strong></b-dropdown-header>

                  <nuxt-link to="/auth/login" class="text-decoration-none dropdown-item">
                      <i class="fa fa-user"></i> Ingresar
                  </nuxt-link>

              <nuxt-link to="/auth/register" class="text-decoration-none dropdown-item">
                  <i class="fa fa-lock"></i> Registrarse
              </nuxt-link>

          </span>
      </b-nav-item-dropdown>
</template>

<script>
  export default {
    name: 'header-dropdown',
    data: () => {
      return { itemsCount: 77 }
    },
    methods: {
      singOut(){
          this.$auth.logout();
          this.$router.push({ name: 'index' });

      }
    }
  }
</script>

