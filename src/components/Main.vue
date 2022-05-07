<template>

    <div>
        <div class="top-contact">
            <div>thing1</div>
            <div>thing2</div>
        </div>
        <section class="dynamic-header">HEDDER</section>
        <h2>Main</h2>

        <div>
            <v-item-group class="navigation-selector">
                <v-item v-model="currentPanel" v-for="n in panels.length" :key="`btn-${n}`"
                v-slot="{ active, toggle, currentPanel }">
                        <v-btn class="btn-nav-selector" :input-value="active" icon @click="toggle" >
                            {{n}}
                        </v-btn>

                </v-item>
            </v-item-group>
        </div>

        <section v-for="p in panels" :key="p.panelNumber">
            <v-window id="allPanels">
                <v-window-item>
                    <!--            <v-card color="grey">-->
                    <!--                <v-row align="center" justify="center">-->
                    <component :is="p.component"></component>
                    <!--                </v-row>-->
                    <!--            </v-card>-->
                </v-window-item>
            </v-window>
        </section>

    </div>


</template>


<script>
import Slides from './Slides.vue'
import CompanyCard from './CompanyCard.vue'

export default {
    name: 'Main',
    components: {
        CompanyCard,
        Slides,

    },
    data: () => ({
        currentPanel: 0,
        panels: {},
    }),
    methods:{
        getPanels(){
            let panelOrder = [Slides, CompanyCard]

            let allPanels = []
            panelOrder.forEach( (p, n) => {
                allPanels.push({panelNumber: n, component: p})
            })
            return allPanels
        }
    },
    mounted() {
        this.panels = this.getPanels()
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

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

.dynamic-header {

}

.btn-nav-selector {
    background: red;
    margin: 3px;
}

.navigation-selector {
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
