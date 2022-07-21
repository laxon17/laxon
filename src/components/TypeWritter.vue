<template>
    <div>
        <span>
            {{ this.jobToDisplay }}
        </span>
        <span id="blinker"></span>
    </div>
</template>

<script>
    export default {
        name: 'TypeWritter',

        data() {
            return {
                jobToDisplay: '',
                jobIndex: 0,
                isDeleting: false,
                jobs: ['Back-end Developer', 'Front-end Developer', 'Freelancer', 'Creator']
            }
        },

        mounted() {
            this.typeJobs()
        },
        
        methods: {
            typeJobs() {
                const currentIndex = this.jobIndex % this.jobs.length
                const currentWord = this.jobs[currentIndex]

                if (this.isDeleting) {
                    this.jobToDisplay = currentWord.substring(0, this.jobToDisplay.length - 1)
                } else {
                    this.jobToDisplay = currentWord.substring(0, this.jobToDisplay.length + 1)
                }

                let typeSpeed = 300

                if (this.isDeleting)
                    typeSpeed /= 3

                if (!this.isDeleting && this.jobToDisplay === currentWord) {
                    typeSpeed = 3000
                    this.isDeleting = true
                } else if (this.isDeleting && this.jobToDisplay === '') {
                    this.isDeleting = false
                    this.jobIndex++
                    typeSpeed = 1000
                }
                setTimeout(() => this.typeJobs(), typeSpeed)
            }
        }
    }
</script>

<style lang="sass" scoped>
    #blinker 
        padding: 1px
        margin-left: 1px
        background-color: grey
        animation: blink infinite 500ms alternate

    @keyframes blink
        from
            opacity: 0
        to
            opacity: 100
</style>