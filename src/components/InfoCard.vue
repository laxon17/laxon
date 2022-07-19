<template>
    <div
        v-for="information in informations"
        :key="information.id"
        class="card__wrapper"
    >
        <i :class="information.icon"></i>
        <h3>{{ information.title }}</h3>
        <p>
            {{ information.description }}
        </p>
    </div>
</template>

<script>
    export default {
        name: 'InfoCard',
        props: {
            informations: { Type: Array }
        }
    }
</script>

<style lang="sass" scoped>
    .card__wrapper
        padding: 2rem
        border-bottom: 1px solid lightgrey
        &:nth-of-type(2n + 1)
            border-right: 1px solid lightgrey
        i
            display: grid
            place-content: center
            font-size: 1.75rem
            background-color: lightgrey
            width: 50px
            height: 50px
            border-radius: 50%
            margin-bottom: 10px
            &:first-of-type
                color: teal
        h3
            margin-bottom: 10px
</style>