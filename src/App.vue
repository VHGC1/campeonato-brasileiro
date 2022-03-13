<template>
  <v-app>
    <AppTopBar />

    <v-navigation-drawer v-model="drawer" absolute temporary>
      <v-list nav dense>
        <v-list-item-group
          v-model="group"
          active-class="green--text text--lighten-2"
        >
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-home</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Inicio</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-soccer</v-icon>
            </v-list-item-icon>
            <v-list-item-title> Classificação </v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>

    <v-main>
      <Inicio />
    </v-main>
  </v-app>
</template>

<script>
import Inicio from './components/Inicio.vue';
import AppTopBar from './components/shared/AppTopBar.vue';

export default {
  name: "App",
  components: {
    Inicio,
    AppTopBar,
  },
  data: () => ({
    drawer: false,
    group: null,
  }),
};
</script>
