<template>

<div>
    <div class="top-contact">
        <div>thing1</div>
        <div>thing2</div>
    </div>
    <section class="dynamic-header">HEDDER</section>
    <h2>hhehihihih</h2>
    <v-parallax src="https://cdn.vuetifyjs.com/images/parallax/material.jpg"></v-parallax>

    <div>
        HEP
        <v-item-group class="navigation-selector">
            <v-item v-model="current" v-for="n in 5" :key="`btn-${n}`"
            v-slot="{ active, toggle, current }">
                    <v-btn class="btn-nav-selector" :input-value="active" icon @click="toggle" >
                        {{current}}
                    </v-btn>

            </v-item>
        </v-item-group>


    </div>

<!--    <v-card flat tile>-->
<!--        <h1>fefefep</h1>-->
<!--        <v-window v-model="current">-->
<!--            <v-window-item v-for="n in length" :key="`card-${n}`">-->
<!--                <v-card color="grey" height="200">-->
<!--                    <v-row class="fill-height" align="center" justify="center">-->
<!--                        <h1 style="font-size: 5rem;" class="white&#45;&#45;text">-->
<!--                            SURAIDO {{ n }}-->
<!--                        </h1>-->
<!--                    </v-row>-->
<!--                </v-card>-->
<!--            </v-window-item>-->
<!--        </v-window>-->

<!--        <v-card-actions class="justify-center">-->

<!--            <v-item-group v-model="current" mandatory>-->
<!--                <v-item-->
<!--                    v-for="n in length" :key="`btn-${n}`"-->
<!--                    v-slot="{ active, toggle }">-->
<!--                    <v-btn-->
<!--                        :input-value="active" icon @click="toggle">-->
<!--                        test-->
<!--                        <v-icon>mdi-record</v-icon>-->
<!--                    </v-btn>-->
<!--                </v-item>-->
<!--            </v-item-group>-->
<!--        </v-card-actions>-->
<!--    </v-card>-->

<!--    <Slides/>-->

    </div>


</template>


<script>
import Slides from './Slides.vue'

export default {
    name: 'Main',
    components: {
        Slides
    },
    data: () => ({
        current: 3,
        elements: {}

    })
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

@font-face {
    font-family: Comfortaa;
    src: url("../assets/static/Comfortaa-Regular.ttf")
}
* {
    font-family: Comfortaa;
}
.top-contact {
    display: flex;
    justify-content: space-around;
}
.dynamic-header{

}
.btn-nav-selector{
    background: red;
    margin: 3px;
}
.navigation-selector{
    position: fixed;
    top: 50%;
    display: flex;
    flex-direction: column;
    right: 5px;
    z-index: 2;
    background-color: rgba(0, 0, 0, 0.8);
    border: 1px solid;
}
</style>
