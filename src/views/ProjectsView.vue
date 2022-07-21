<template>
    <div class="section__wrapper">
        <div class="section__title">
            <span class="background__circle"></span>
            <h2><span class="highlight__text">My</span> projects</h2>
            <div class="select__filter">
                <span>Sort by date: </span>
                <input type="radio" name="sortFilter" id="desc" v-model="this.sortFilter" value="desc">
                <label for="desc" v-if="this.sortFilter=='asc'">
                    <i class="material-icons">keyboard_arrow_down</i>
                </label>
                <input type="radio" name="sortFilter" id="asc" v-model="this.sortFilter" value="asc">
                <label for="asc" v-if="this.sortFilter=='desc'">
                    <i class="material-icons">keyboard_arrow_up</i>
                </label>
            </div>
        </div>
        <div class="projects__wrapper">
            <ProjectSample :projects="this.projects" />
        </div>
    </div>
</template>

<script>
    import ProjectSample from '@/components/ProjectSample'

    export default {
        name: 'ProjectsView',

        components: { ProjectSample },

        computed: {
            projects() {
                const projectsArray = [
                    { id: 1, name: 'worldCraft', img: 'worldcraft.jpg', date: '2022-03-03' },
                    { id: 2, name: 'wireframe', img: 'wireframe.jpg', date: '2022-03-09' },
                    { id: 3, name: 'crossfader', img: 'crossfader.jpg', date: '2021-12-18' },
                    { id: 4, name: 'traktor-shop', img: 'traktor.jpg', date: '2021-03-13' },
                    { id: 5, name: 'portfolio-old', img: 'portfolio.jpg', date: '2021-02-22' },
                    { id: 6, name: 'codeus', img: 'codeus.jpg', date: '2020-12-15' }
                ]

                if(this.sortFilter == 'desc') return projectsArray.sort((prev, next) => prev.date < next.date ? 1 : -1)
                return projectsArray.sort((prev, next) => prev.date > next.date ? 1 : -1)
            }
        },

        data() {
            return {
                sortFilter: 'desc'
            }
        }
    }
</script>

<style lang="sass" scoped>
    .projects__wrapper
        display: grid
        grid-template-columns: repeat(2, 50%)
    .section__title
        display: flex
        justify-content: space-between
        align-items: center
        .select__filter
            display: flex
            align-items: center
            input[type="radio"]
                display: none
            i
                cursor: pointer
                font-size: 2rem
                color: teal
</style>