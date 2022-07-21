<template>
    <div class="card__wrapper" :class="addBorder ? 'border__right' : ''" >
        <div class="title">
            <i :class="icon"></i> <h3>{{ title }}</h3>
        </div>
        <div class="circles__container">
            <div 
                v-for="skill in skills"
                :key="skill.id"
            
                class="circle__container"
            >
                <div class="progress__bar" :style=" { background: `conic-gradient(teal calc(${skill.quantity} * 3.6deg), #cacdcf calc(${skill.quantity} * 3.6deg))` }">
                    <div class="value__container">
                        {{ skill.quantity }}%
                    </div>
                </div>
                <h4>{{ skill.language }}</h4>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'CircularProgress',

        props: {
            skills: { Type: Array },
            title: { Type: String },
            icon: { Type: String },
            addBorder: { Type: Boolean, Default: false}
        },

        methods: {
            loadBar(bar, value) {
                console.log(bar)
            }
        }
    }
</script>

<style lang="sass" scoped>
    .card__wrapper
        display: flex
        flex-direction: column
        border-bottom: 1px solid lightgrey
        .border__right
            border-right: 1px solid lightgrey
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
        .circles__container
            padding: 1.5em 2em
            display: grid
            grid-template-columns: repeat(2, 50%)
            .circle__container
                width: 100%
                display: flex
                flex-direction: column
                align-items: center
                margin-bottom: 25px
                .progress__bar
                    display: grid
                    place-content: center
                    position: relative
                    width: 100px
                    height: 100px
                    border-radius: 50%
                    margin-bottom: 10px
                    .value__container
                        position: relative
                    &::before
                        position: absolute
                        content: ''
                        background-color: #fff
                        width: 90px
                        height: 90px
                        left: 5px
                        top: 5px
                        border-radius: 50%
                h4

                    font-size: 14px
                    font-weight: 300
</style>