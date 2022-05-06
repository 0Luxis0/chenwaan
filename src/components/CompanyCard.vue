<template>
    <div>
        <h2>COMPANY FRONT</h2>
        <div id="companyFront">
<!--            <v-parallax src="https://cdn.vuetifyjs.com/images/parallax/material.jpg"></v-parallax>-->

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
            </ul>
            <h3>Ecosystem</h3>
            <ul>
                <li><a href="https://router.vuejs.org" target="_blank" rel="noopener">vue-router</a></li>
                <li><a href="https://vuex.vuejs.org" target="_blank" rel="noopener">vuex</a></li>
            </ul>

        </div>
    </div>
</template>

<script>
export default {
    name: 'CompanyCard',
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
.main{

}
.main-overlay{
    position: fixed;
    display: flex;
    flex-direction: column;
}
</style>
