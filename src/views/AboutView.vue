<template>
    <div class="section__wrapper">
        <div class="section__title">
            <span class="background__circle"></span>
            <h2><span class="highlight__text">About</span> Me</h2>
        </div>
        <div class="content__wrapper">
            <div class="intro__text">
                <p>
                    <span id="boldText">Hello! I'm Lazar Lalovic.</span>
                    Full stack web developer from Belgrade, Serbia.
                    My hobby is DJing. 
                    I have spent more than six years working as a DJ and expressing myself through music, 
                    and it remains my big passion that I hope to nourish in the future.
                </p>
                <div class="basic__info">
                    <p>
                        <span id="boldText">AGE</span> ........ 22
                        <br />
                        <br />
                        <span id="boldText">AVAILABLE</span> ........ YES
                    </p>
                    <p>
                        <span id="boldText">PREFER</span> ........ REMOTE WORK
                        <br />
                        <br />
                        <span id="boldText">ADDRESS</span> ........ TOŠIN BUNAR 147
                    </p>
                </div>
            </div>
        </div>
        <div class="section__title">
            <span class="background__circle"></span>
            <h2><span class="highlight__text">My</span> Services</h2>
        </div>
        <div class="services__wrapper">
            <InfoCard :informations="this.informations" />
        </div>
        <div class="section__title">
            <span class="background__circle"></span>
            <h2><span class="highlight__text">Pricing</span></h2>
        </div>
        <div class="pricing__wrapper">
            <PricingCard :prices="this.prices" />
        </div>
    </div>

</template>

<script>
    import InfoCard from '@/components/InfoCard'
    import PricingCard from '@/components/PricingCard'
    export default {
        name: 'AboutView',

        data() {
            return {
                informations: [
                    { id: 1, title: 'Front-end', description: 'Modern and mobile-ready website that will help you reach all of your marketing.', icon: 'fa-brands fa-vuejs'},
                    { id: 2, title: 'Back-end', description: 'UI/UX focus on the user, front-end focus on the settings of the user and back-end focus on the data.', icon: 'fa-brands fa-laravel'},      
                    { id: 3, title: 'SEO', description: 'Getting your page visible and high ranked in search results.', icon: 'fa-solid fa-magnifying-glass'},      
                    { id: 4, title: 'Services', description: 'Setting everything up and 24/7 support.', icon: 'fa-solid fa-screwdriver-wrench'} 
                ],
                prices: [
                    { id: 1, title: 'Basic', value: 22, primary: ['Static sites (Vue only)', 'Dynamic sites (Laravel only)'], icon: 'fa-solid fa-battery-half', additional: false },
                    { id: 2, title: 'Pro', value: 46, primary: ['Vue + Laravel API', 'Cyber Security'], icon: 'fa-solid fa-battery-full', additional: true }
                ]
            }
        },

        components: {
            InfoCard,
            PricingCard
        }
    }
</script>

<style lang="sass" scoped>
    .section__wrapper
        width:700px
        height:650px
        background-color: #fff
        border-radius: 0 4px 4px 0 
        overflow-y: auto
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
        .content__wrapper
            color: #585858
            #boldText
                font-weight: 700
            padding: 2em 1em 2em 2.5em
            line-height: 1.5rem
            p
                margin-bottom: 20px
            .basic__info
                display: flex
                align-items: center
                justify-content: space-around
        .services__wrapper
            display: grid
            grid-template-columns: repeat(2, 50%)
            margin-bottom: 30px
        .pricing__wrapper,
        .facts__wrapper
            display: flex
</style>