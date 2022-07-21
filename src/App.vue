<template>
  <div class="menu__wrapper">
    <MainSection @changeContent="this.changeContent" />
    <Transition name="fade">
      <AboutView v-show="aboutVisibility" />
    </Transition>
    <Transition name="fade">
      <ResumeView v-show="resumeVisibility" />
    </Transition>
    <Transition name="fade">
      <ProjectsView v-show="projectsVisibility" />
    </Transition>
    <Transition name="fade">
      <ContactView v-show="contactVisibility" />
    </Transition>
  </div>
</template>

<script>
  import MainSection from '@/components/MainSection'
  import AboutView from '@/views/AboutView'
  import ResumeView from '@/views/ResumeView'
  import ProjectsView from '@/views/ProjectsView'
  import ContactView from '@/views/ContactView'

  export default {
    components: {
      MainSection,
      AboutView,
      ResumeView,
      ProjectsView,
      ContactView
    },

    data() {
      return {
        aboutVisibility: true,
        resumeVisibility: false,
        projectsVisibility: false,
        contactVisibility: false
      }
    },

    methods: {
      falseAll() {
        this.aboutVisibility = false
        this.resumeVisibility = false
        this.projectsVisibility = false
        this.contactVisibility = false
      },

      changeContent(content) {
        switch(content) {
          case 'resume':
            this.falseAll()
            setTimeout(() => this.resumeVisibility = true, 1000)
            break
          case 'projects':
            this.falseAll()
            setTimeout(() => this.projectsVisibility = true, 1000)
            break
          case 'contact':
            this.falseAll()
            setTimeout(() => this.contactVisibility = true, 1000)
            break
          default: 
            this.falseAll()
            setTimeout(() => this.aboutVisibility = true, 1000)
            break
        }
      }
    }
  }
</script>

<style lang="sass">
  *
    margin: 0
    padding: 0
    box-sizing: border-box
    font-family: 'JetBrains Mono', monospace
  ::selection
    color: white
    background-color: teal
  ::-webkit-scrollbar
    width: 8px
  ::-webkit-scrollbar-track
    background: #ddd
  ::-webkit-scrollbar-thumb
    border-radius: 4px
    background: #aaa
  ::-webkit-scrollbar-thumb:hover 
    background: #999
  html
    body
      .fade-enter-from
        transform: scale(0)
        opacity: 0
      .fade-enter-to
        transform: scale(100%)
        opacity: 1
      .fade-enter-active,
      .fade-leave-active
        transition: all 1000ms ease
      .fade-leave-from
        transform: scale(100%)
        opacity: 1
      .fade-leave-to
        opacity: 0
        transform: scale(0)
      #app
        background: rgb(0,103,85)
        background: radial-gradient(circle, rgba(0,103,85,1) 0%, rgba(0,189,156,1) 70%, rgba(0,255,209,1) 100%)
        width: 100%
        height: 100vh
        display: flex
        align-items: center
        justify-content: center
        .menu__wrapper 
          display: flex
          align-items: center
          justify-content: center
          .section__wrapper
            overflow-y: auto
            width:700px
            height:650px
            background-color: #fff
            border-radius: 0 4px 4px 0 
            .section__title
                width: 100%
                border-bottom: 1px solid lightgrey
                padding: 30px 40px
                position: relative
                h2
                    position: relative
                    z-index: 2
                    font-weight: 400
                    .highlight__text 
                        color: #00B394
                .background__circle
                    position: absolute
                    z-index: 1
                    left: 15px
                    border-radius: 50%
                    width: 35px
                    height: 35px
                    background: lightgrey
                    background: linear-gradient(90deg, grey 0%, lightgrey 50%,#fff 100%)
</style>
