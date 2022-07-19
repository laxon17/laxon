<template>
    <div class="content__wrapper">
        <AboutView v-if="aboutVisibility" />
        <ContactView v-if="contactVisibility" />
        <ProjectsView v-if="projectsVisibility" />
        <ResumeView v-if="resumeVisibility" />
    </div>
</template>

<script>
    import AboutView from '@/views/AboutView'
    import ContactView from '@/views/ContactView'
    import ProjectsView from '@/views/ProjectsView'
    import ResumeView from '@/views/ResumeView'

    export default {
        name: 'ContentSection',
        components: {
            AboutView,
            ContactView,
            ResumeView,
            ProjectsView
        },

        props: {
            loadView: { Type: String }
        },
    
        data() {
            return {
                aboutVisibility: true,
                resumeVisibility: false,
                contactVisibility: false,
                projectsVisibility: false
            }
        }
    }
</script>

<style lang="sass" scoped>
    .content__wrapper
        padding: 1em
        background-color: #fff
        border-radius: 0 4px 4px 0
        height: 650px
        width: 700px
</style>
