<template>
    <div 
        class="card__wrapper"
        v-for="information in informations"
        :key="information.id"
    >
        <span 
            id="period"
            :class="information.end ? 'finished' : 'active' "
        >
            {{ information.start }} - {{ information.end ?  information.end : 'Present' }}
        </span>
        <h3>{{ information.school }}</h3>
        <span id="location">{{ information.location }}</span>
        <p>
            {{ information.description }}
        </p>
    </div>
</template>

<script>
    export default {
        name: 'ResumeCards',

        props: {
            informations: { Type: Array }
        }
    }
</script>

<style lang="sass" scoped>
    .card__wrapper
        width: 100%
        padding: 2em
        border-bottom: 1px solid lightgrey
        h3
            margin-top: 15px
        #location
            color: grey
            font-size: 12px
        #period
            border-radius: 5px
            padding: 3px
            font-size: 12px
        .active
            border: 1px solid teal
            color: teal
        .finished
            border: 1px solid lightgrey
            color: lightgrey
        p
            margin-top: 20px
            
</style>