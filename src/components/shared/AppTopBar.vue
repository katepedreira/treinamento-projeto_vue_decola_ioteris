<template>
    <div class="app-top-bar">
        <v-app-bar app color="green" dark>
            <v-app-bar-nav-icon @click="drawer = true">
            </v-app-bar-nav-icon> 
            <v-toolbar-title class="mr-8">
                Campeonato Brasileiro ⚽
            </v-toolbar-title>
            <v-tooltip v-if="!$vuetify.theme.dark" bottom>
                <template v-slot:activator="{ on, attrs }">
                    <v-btn v-on="on" v-bind="attrs" color="transparent" small fab @click="darkMode">
                        <v-icon class="mr-1">mdi-moon-waxing-crescent</v-icon>
                    </v-btn>
                </template>
                <span>Dark Mode Off</span>
            </v-tooltip>

            <v-tooltip v-else bottom>
                <template v-slot:activator="{ on, attrs }">
                    <v-btn v-on="on" v-bind="attrs" color="transparent" small fab @click="darkMode">
                        <v-icon>mdi-white-balance-sunny</v-icon>
                    </v-btn>
                </template>
                <span>Dark Mode On</span>
            </v-tooltip>
        </v-app-bar>

        <v-navigation-drawer v-model="drawer" absolute temporary>
            <v-list nav dense>
                <v-list-item-group v-model="group" active-class="green--text textlighten-2">

                    <router-link to="/">
                        <v-list-item>
                            <v-list-item-icon>
                                <v-icon>mdi-home</v-icon>
                            </v-list-item-icon>
                            <v-list-item-title>
                            Início
                            </v-list-item-title>
                        </v-list-item>
                    </router-link>

                    <router-link to="/classificacao">
                        <v-list-item>
                            <v-list-item-icon>
                                <v-icon>mdi-soccer</v-icon>
                            </v-list-item-icon>
                            <v-list-item-title>
                            Classificação
                            </v-list-item-title>
                        </v-list-item>
                    </router-link>

                </v-list-item-group>
            </v-list>
        </v-navigation-drawer>
    </div>
</template>

<script>
export default {
    name: 'AppTopBar',
    data: () => ({
        drawer: false,
        group: null,
    }),
    methods: {
        darkMode() {
            this.$vuetify.theme.dark = !this.$vuetify.theme.dark;
        }
    }
}
</script>

<style scoped>

.app-top-bar a {
    text-decoration: none;
}

</style>