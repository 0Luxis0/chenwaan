<template>
    <div><h2>hhehihihih</h2>
        <div class="hello">

            <p>
                CHANGED a guide and recipes on how to configure / customize this project,<br>
                check out the
                <a href="https://cli.vuejs.org" target="_blank" rel="noopener">vue-cli documentation</a>.
            </p>
            <h3>Installed CLI Plugins</h3>
            <ul>
            </ul>
            <h3>Essential Links</h3>
            <ul>
                <li><a href="https://vuejs.org" target="_blank" rel="noopener">Core Docs</a></li>
                <li><a href="https://forum.vuejs.org" target="_blank" rel="noopener">Forum</a></li>
                <li><a href="https://chat.vuejs.org" target="_blank" rel="noopener">Community Chat</a></li>
                <li><a href="https://twitter.com/vuejs" target="_blank" rel="noopener">Twitter</a></li>
                <li><a href="https://news.vuejs.org" target="_blank" rel="noopener">News</a></li>
            </ul>
            <h3>Ecosystem</h3>
            <ul>
                <li><a href="https://router.vuejs.org" target="_blank" rel="noopener">vue-router</a></li>
                <li><a href="https://vuex.vuejs.org" target="_blank" rel="noopener">vuex</a></li>
                <li><a href="https://github.com/vuejs/vue-devtools#vue-devtools" target="_blank"
                       rel="noopener">vue-devtools</a></li>
                <li><a href="https://vue-loader.vuejs.org" target="_blank" rel="noopener">vue-loader</a></li>
                <li><a href="https://github.com/vuejs/awesome-vue" target="_blank" rel="noopener">awesome-vue</a></li>
            </ul>

        </div>

        <v-card flat tile>

            <v-window v-model="current">
                <v-window-item v-for="n in length" :key="`card-${n}`">
                    <v-card color="grey" height="200">
                        <v-row class="fill-height" align="center" justify="center">
                            <h1 style="font-size: 5rem;" class="white--text">
                                Slid1es {{ n }}
                            </h1>
                        </v-row>
                    </v-card>
                </v-window-item>
            </v-window>

            <v-card-actions class="justify-center">

                <v-item-group v-model="current"  mandatory>
                    <v-item
                        v-for="n in length" :key="`btn-${n}`"
                        v-slot="{ active, toggle }">
                        <v-btn
                            :input-value="active" icon @click="toggle">
                            <v-icon>mdi-record</v-icon>
                        </v-btn>
                    </v-item>
                </v-item-group>
            </v-card-actions>
        </v-card>
    </div>
</template>

<script>
export default {
    name: 'Contact', id: 'contact',
    data: () => ({
        length: 3,
        current: 0,
    }),

    methods: {
        next() {
            this.current = this.current + 1 === this.length ? 0 : this.current + 1
        },
        prev() {
            this.current = this.current - 1 < 0 ? this.length - 1 : this.current - 1
        },
    },
}


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
    margin: 40px 0 0;
}
ul {
    list-style-type: none;
    padding: 0;
}
li {
    display: inline-block;
    margin: 0 10px;
}
a {
    color: #42b983;
}

</style>
