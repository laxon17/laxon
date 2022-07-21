<template>
    <div 
        class="sample__wrapper" 
        v-for="project in projects" 
        :key="project.id"
    >
        <img :src="this.getPic(project.img)" alt="Site screenshot" />
        <h3> {{ project.name }}</h3>
        <div class="links">
            <a :href="getUrl(project.name, 'source')" target="_blank">
                <i class="fa-solid fa-eye"></i>
            </a>
            <a :href="getUrl(project.name)" target="_blank" >
                <i class="fa-brands fa-github"></i>
            </a>
        </div>
        <span id="date">
            {{ project.date }}
        </span>
    </div>
</template>

<script>
    export default {
        name: 'ProjectSample',

        props: {
            projects: { Type: Array }
        },

        methods: {
            getPic(img) {
                return require('../assets/' + img)
            },

            getUrl(name, urlFor = 'git') {
                if(name == 'wireframe' && urlFor == 'source') return 'http://wireframe.codeus.me/'
                if(urlFor == 'git') return `https://www.github.com/laxon17/${name}`
                if(urlFor == 'source') return `https://laxon17.github.io/${name}`
            }
        }
    }
</script>

<style lang="sass" scoped>
    .sample__wrapper
        display: flex
        flex-direction: column
        align-items: center
        padding: 1em
        width: 100%
        border-bottom: 1px solid lightgrey
        &:nth-of-type(2n+1)
            border-right: 1px solid lightgrey
        img
            transition: all 500ms
            width: 90%
            
            &:hover
                transform: scale(110%)
        h3, img, .links
            margin-bottom: 15px
        .links
            a
                i
                    font-size: 20px
                    color: teal
                    margin-right: 10px
        #date
            font-weight: 300
            font-size: 15px
            color: grey
</style>