<template>
    <div><h2>hhehihihih</h2>
        <v-parallax src="https://cdn.vuetifyjs.com/images/parallax/material.jpg"></v-parallax>
        <v-card flat tile>
            <v-window v-model="onboarding">
                <v-window-item
                    v-for="n in length"
                    :key="`card-${n}`">
                    <v-card
                        color="grey"
                        height="200">
                        <v-row
                            class="fill-height"
                            align="center"
                            justify="center">
                            <h1
                                style="font-size: 5rem;"
                                class="white--text">
                                Slide {{ n }}
                            </h1>
                        </v-row>
                    </v-card>
                </v-window-item>
            </v-window>

            <v-card-actions class="justify-center">
<!--                <v-btn text @click="prev">-->
<!--                    <v-icon>mdi-chevron-left</v-icon>-->
<!--                </v-btn>-->
                <v-item-group v-model="onboarding" class="text-center" mandatory>
                    <v-item
                        v-for="n in length"
                        :key="`btn-${n}`"
                        v-slot="{ active, toggle }">
                        <v-btn
                            :input-value="active" icon @click="toggle">
                            <v-icon>mdi-record</v-icon>
                        </v-btn>
                    </v-item>
                </v-item-group>
<!--                <v-btn text @click="next">-->
<!--                    <v-icon>mdi-chevron-right</v-icon>-->
<!--                </v-btn>-->
            </v-card-actions>
        </v-card>
    </div>
</template>

<script>
export default {
    name: 'Slides',
    data: () => ({
        length: 3,
        onboarding: 0,
    }),

    methods: {
        next() {
            this.onboarding = this.onboarding + 1 === this.length
                ? 0 : this.onboarding + 1
        },
        prev() {
            this.onboarding = this.onboarding - 1 < 0 ? this.length - 1 : this.onboarding - 1
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
