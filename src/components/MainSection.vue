<template>
    <div class="main__wrapper">
        <Navigation @changeContent="this.changeContent"/>
        <div class="info__container">
            <div class="image__container">
                <img src="../assets/lakson.jpg" alt="Web Dev as a DJ" />
            </div>
            <div class="personal__info">
                <h1>Lazar Lalović</h1>
                <TypeWritter />
            </div>
            <div class="social__container">
                <i class="fa-brands fa-github"></i>
                <i class="fa-brands fa-instagram"></i>
                <i class="fa-brands fa-stack-overflow"></i>
                <i class="fa-brands fa-codepen"></i>
            </div>
            <a href="!#">DOWNLOAD CV <i class="material-icons">cloud_download</i></a>
        </div>
    </div>
</template>

<script>
    import Navigation from './Navigation'
    import TypeWritter from './TypeWritter'

    export default {
        name: 'MainSection',
        components: {
            Navigation,
            TypeWritter
        },
        methods: {
            changeContent(contentType) {
                this.$emit('changeContent', contentType)
            }
        }
    }
</script>

<style lang="sass" scoped>
    .main__wrapper
        border-radius: 4px
        position: relative
        width: 500px
        box-shadow: -20px -10px 3px 0px lightgrey
        background-color: #fff
        .info__container
            width: 100%
            display: flex
            flex-direction: column
            align-items: center
            justify-content: space-around
            box-shadow: 0 0 15px 0px grey
            .image__container
                position: relative
                width: 100%
                img
                    border-radius: 4px
                    width: 100%
                &::before, &::after
                    content: ''
                    position: absolute
                    bottom: 0
                    width: 500px
                    height: 70px
                    background-color: white
                &::before
                    clip-path: polygon(0 0, 0% 100%, 100% 100%)
                &::after
                    clip-path: polygon(100% 0, 0% 100%, 100% 100%)
                    right: 0px
            .personal__info
                display: flex
                flex-direction: column
                align-items: center
                justify-content: space-between
                margin-bottom: 20px
                h1
                    font-weight: 300
                    margin-bottom: 10px
            .social__container
                margin-bottom: 100px
                i
                    cursor: pointer
                    font-size: 16px
                    margin-right: 15px
            a
                color: #000
                width: 100%
                padding: 1.3em 0 1em 0
                border-top: 1px solid lightgrey
                display: flex
                align-items: center
                justify-content: center
                text-decoration: none
                transition: 300ms all
                &:hover
                    color: rgb(0,138,114)
                i
                    margin-left: 10px
    @media screen and (max-width: 1380px)
        .main__wrapper
            width: 90%
            margin-bottom: 30px
            box-shadow: none
            .info__container
                .image__container
                    img
                    &::before, &::after
                        width: 60%
    @media screen and (max-width: 600px)
        .main__wrapper
            width: 80%
            

</style>