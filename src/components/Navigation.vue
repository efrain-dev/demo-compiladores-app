<template>
  <div>
    <div>
      <b-navbar toggleable="lg" type="dark"  variant="dark">
        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav >
            <b-nav-item v-if="session" v-bind:active="setActive($route.name,'Home')">
              <router-link  class="text-white" to="/home"><b-icon icon="distribute-vertical" class="mx-1" aria-hidden="true"> </b-icon>Home</router-link>
            </b-nav-item>
            <b-nav-item v-bind:active="setActive($route.name,'analizador')">
              <router-link class="text-white" to="/analizador"><b-icon icon="card-text" class="mx-1" aria-hidden="true"> </b-icon>Analizador</router-link>
            </b-nav-item>
            <b-nav-item v-bind:active="setActive($route.name,'implementacion')">
              <router-link class="text-white"  to="/implementacion"><b-icon icon="book" class="mx-1" aria-hidden="true"> </b-icon>Implementacion</router-link>
            </b-nav-item>
            <b-nav-item v-bind:active="setActive($route.name,'about')">
              <router-link class="text-white" to="/about"><b-icon icon="info-circle" class="mx-1" aria-hidden="true"> </b-icon>Sobre Nosotros</router-link>
            </b-nav-item>
          </b-navbar-nav>

          <!-- Right aligned nav items -->
          <b-navbar-nav class="ml-auto">
            <b-nav-item-dropdown right>
              <template #button-content>
                <b-icon icon="person" class="mx-1" aria-hidden="true"> </b-icon>Usuario
              </template>
              <b-dropdown-item v-if="session" to="/cuenta">Cuenta</b-dropdown-item>
              <b-dropdown-item v-if="session===false"><router-link class="text-dark" to="/">Login</router-link></b-dropdown-item>
              <b-dropdown-item v-if="session===false"><router-link class="text-dark" to="/register">Registro</router-link></b-dropdown-item>
              <b-dropdown-item v-if="session" v-on:click="cerrarSesion">Cerrar Sesion</b-dropdown-item>
            </b-nav-item-dropdown>
          </b-navbar-nav>
        </b-collapse>
      </b-navbar>
    </div>
  </div>
</template>

<script>
import auth from "@/logic/auth";
import router from "@/router";

export default {
  name: "Navigation",

  data: () => ({
    session: false,

  }),

  updated() {
    this.session= auth.getActiveSession()
  },
  mounted() {
    this.session= auth.getActiveSession()
  },
  methods: {
    cerrarSesion(){
      auth.unsetUserLogged()
      router.push('/').catch(error => {
        if (error.name !== "NavigationDuplicated") {
          throw error;
        }
      });
    },
    setActive(name,now) {
      return name === now;
    }

  }
};
</script>

<style scoped>

</style>