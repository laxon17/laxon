<template>
    <div class="navigation__wrapper">
        <input type="radio" name="navItem" value="about" id="about" checked />
        <label for="about" @click="$emit('changeContent', 'about')" ><i class="material-icons">person</i>ABOUT</label>
        <input type="radio" name="navItem" value="resume" id="resume" />
        <label for="resume" @click="$emit('changeContent', 'resume')"><i class="material-icons tiny">description</i>RESUME</label>
        <input type="radio" name="navItem" value="projects" id="projects" />
        <label for="projects" @click="$emit('changeContent', 'projects')"><i class="material-icons">build</i>PROJECTS</label>
        <input type="radio" name="navItem" value="contact" id="contact" />
        <label for="contact" @click="$emit('changeContent', 'contact')"><i class="material-icons">mail</i>CONTACT</label>
    </div>
</template>

<script>
    export default {
        name: 'Navigation'
    }
</script>

<style lang="sass" scoped>
    .navigation__wrapper
        position: absolute
        left: -80px
        top: 60px
        display: flex
        flex-direction: column
        align-items: flex-start
        z-index: 5
        label
            border-bottom: 1px solid lightgrey
            width: 70px
            height: 70px
            text-align: center
            background-color: #fff
            font-size: 12px
            display: flex
            flex-direction: column
            align-items: center
            justify-content: center
            cursor: pointer
            color: grey
            transition: 200ms all
            & i
                margin-bottom: 5px
            &:first-of-type
                border-radius: 5px 5px 0 0
            &:last-of-type
                border-radius: 0 0 5px 5px
        input[type="radio"] 
            display: none
            &:checked
                & + label 
                    color: #00997E
    @media screen and (max-width: 1380px)
        .navigation__wrapper 
            left: 0
            top: -80px
            width: 100%
            flex-direction: row
            justify-content: space-evenly
            label
                width: 25%
                border-right: 1px solid lightgrey   
                &:first-of-type
                    border-radius: 0
                &:last-of-type
                    border-radius: 0
</style>