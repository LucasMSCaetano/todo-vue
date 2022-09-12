<template>
    <nav >
        <v-toolbar flat app>
            <v-app-bar-nav-icon class="grey--text" @click="drawer = !drawer"></v-app-bar-nav-icon>
            <v-toolbar-title class="text-uppercase grey--text">
                <span class="font-weight-light">Todo</span>
                <span >Ninja</span>
            </v-toolbar-title>
            <v-spacer></v-spacer>
            <span >Sing Out</span>
            <v-icon right>mdi-exit-to-app</v-icon>
        </v-toolbar>

        <v-navigation-drawer v-model="drawer" app class="primary">
            <p>test</p>
        </v-navigation-drawer>
    </nav>
</template>

<script>

export default {
    data(){
        return{
            drawer: false
        }
    }
}
</script>
