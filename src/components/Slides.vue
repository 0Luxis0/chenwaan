<template>
    <div>
        <h2>Slides</h2>

        <v-card flat tile>
            <v-window
                v-model="onboarding">
                <v-window-item
                    v-for="(i, n) in images"
                    :key="`card-${n}`">
                    <v-card color="grey">
                        <v-row class="fill-height" align="center"  justify="center">
                            <v-img :src="i" :aspect-ratio="16/9">

                            </v-img>
                        </v-row>
                    </v-card>
                </v-window-item>
            </v-window>

            <v-card-actions class="justify-space-between">
                <v-item-group v-model="onboarding" class="text-center" mandatory>
                    <v-item v-for="n in images.length"
                            :key="`btn-${n}`"
                            v-slot="{ active, toggle }">
                        <v-btn :input-value="active" icon @click="toggle">
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
    data: () => ({
        length: 3,
        onboarding: 0,
        images: []
    }),

    methods: {
        next() {
            this.onboarding = this.onboarding + 1 === this.length ? 0 : this.onboarding + 1
        },
        prev() {
            this.onboarding = this.onboarding - 1 < 0
                ? this.length - 1
                : this.onboarding - 1
        },
        // async getAllFilesAtFolder(folder){
        // import { opendir } from 'node:fs/promises';
        //     try {
        //         const dir = await opendir('./');
        //         for await (const dirent of dir)
        //             console.log(dirent.name);
        //     } catch (err) {
        //         console.error(err);
        //     }
        // },
    },
    mounted() {
        // this.images.push(require('./../assets/mainPanelSlides/boxer.png'))
        // this.images.push(require('./../assets/mainPanelSlides/labrador.jpg'))
        // this.images.push(require('./../assets/mainPanelSlides/wild.jpg'))
    }
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
