<template>
    <div class="section__wrapper">
        <div class="section__title">
            <span class="background__circle"></span>
            <h2><span class="highlight__text">Resume</span></h2>
        </div>
        <div class="resume__wrapper">
            <div class="education__wrapper border__right">
                <div class="resume__title">
                    <i class="fa-solid fa-building-columns"></i> EDUCATION
                </div>
                <ResumeCards :informations="this.educations" />
            </div>
            <div class="experience__wrapper">
                <div class="resume__title">
                    <i class="fa-solid fa-briefcase"></i> EXPERIENCE
                </div>
                <ResumeCards :informations="this.experiences" />
            </div>
        </div>
        <div class="section__title">
            <span class="background__circle"></span>
            <h2><span class="highlight__text">My</span> skills</h2>
        </div>
        <div class="skills__wrapper">
            <div class="backend__wrapper">
                <CircularProgress :skills="this.skills.backend" :title="'BACK-END'" :icon="'fa-solid fa-code'" :addBorder="true"/>
            </div>
            <div class="knowledge__wrapper">
                <div class="title">
                    <i class="fa-solid fa-list-check"></i><h3>Knowledge</h3>
                </div>
                <ul v-for="(thing, index) in things" :key="index">
                    <li>
                        <span id="checkSymbol">&check;</span> {{ thing }}
                    </li>
                </ul>
            </div>
            <div class="frontend__wrapper">
                <CircularProgress :skills="this.skills.frontend" :title="'FRONT-END'" :icon="'fa-solid fa-compass-drafting'" :addBorder="true" />
            </div>     
            <div class="learning__wrapper">
                <div class="title">
                    <i class="fa-solid fa-graduation-cap"></i><h3>Learning/improving</h3>
                </div>
                <ul v-for="(lecture, index) in lectures" :key="index">
                    <li>
                        <span id="checkSymbol">&check;</span> {{ lecture }}
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
    import ResumeCards from '@/components/ResumeCards'
    import CircularProgress from '@/components/CircularProgress'

    export default {
        name: 'ResumeView',

        components: { ResumeCards, CircularProgress },

        data() {
            return {
                educations: [
                    { id: 1, school: 'Gymnasium', start: 2015, end: 2017, location: 'Vlasenica', description: 'Started education at Milorad Vlačić high school.'},
                    { id: 2, school: 'Gymnasium', start: 2017, end: 2019, location: 'Milići', description: 'Ended education and got a high school diploma at Milutin Milanković'},
                    { id: 3, school: 'Programming', start: 2020, end: '', location: 'Belgrade', description: 'Bachelor\'s Degree in Computer science, ICT - College of Vocational Studies.'}
                ],

                experiences: [
                    { id: 1, school: 'Gymnasium', start: 2015, end: 2017, location: 'Vlasenica', description: 'Started education at Milorad Vlačić high school.'},
                    { id: 2, school: 'Gymnasium', start: 2017, end: 2019, location: 'Milići', description: 'Ended education and got a high school diploma at Milutin Milanković'},
                    { id: 3, school: 'Programming', start: 2020, end: '', location: 'Belgrade', description: 'Bachelor\'s Degree in Computer science, ICT - College of Vocational Studies.'}
                ],

                skills: {
                    backend: [
                        { id: 1, quantity: 85, language: 'PHP'},
                        { id: 2, quantity: 71, language: 'Laravel'},
                        { id: 3, quantity: 69, language: 'C# (ASP.NET)'},
                        { id: 4, quantity: 92, language: 'MySQL/MSSQL'}
                    ],

                    frontend: [
                        { id: 1, quantity: 95, language: 'HTML/CSS'},
                        { id: 2, quantity: 86, language: 'JavaScript'},
                        { id: 3, quantity: 69, language: 'Vue'},
                        { id: 4, quantity: 32, language: 'Angular'}
                    ],
                },
                
                things: [
                    'Website hosting', 
                    'SEO Optimization', 
                    'Responsive designs', 
                    'Linux Administration', 
                    'Windows Administration'
                ],

                lectures: [
                    'Laravel',
                    'Angular',
                    'Xamarin - iOS/Android',
                    'OOP Java',
                    'Cyber security',
                ]
            }
        }
    }
</script>

<style lang="sass" scoped>
    .border__right
        border-right: 1px solid lightgrey
    .resume__wrapper
        width: 100%
        display: flex
        margin-bottom: 30px
        .experience__wrapper,
        .education__wrapper
            width: 50%
            display: flex
            flex-direction: column
            justify-content: flex-start
            .resume__title
                width: 100%
                display: flex
                align-items: center
                border-bottom: 1px solid lightgrey
                padding: 1em 2em
            i
                margin-right: 10px
                color: teal
                font-size: 2rem
    .skills__wrapper
        display: grid
        grid-template-columns: repeat(2, 50%)
        .knowledge__wrapper,
        .learning__wrapper
            border-bottom: 1px solid lightgrey
        .title
            padding: 1.5em 2em
            width: 100%
            display: flex
            border-bottom: 1px solid lightgrey
            align-items: center
            i
                margin-right: 10px
                color: teal
                font-size: 1.75rem
            h3
                font-weight: 300
        ul
            padding: 1em
            li
                list-style-type: none
        #checkSymbol
            color: teal
</style>