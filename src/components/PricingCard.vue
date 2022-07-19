<template>
    <div 
        class="card__wrapper"
        v-for="price in prices"
        :key="price.id"
    >
        <i :class="price.icon"></i>
        <h3>{{ price.title }}</h3>
        <p><span id="currency">&euro;</span><span id="price">{{ price.value }}</span>hour</p>
        <ul
            v-for="(service, index) in price.primary"
            :key="index"
        >
            <li>{{ service }}</li>
        </ul>
        <ul>
            <li>Deployment and service</li>
            <li>SEO audit</li>
        </ul>
        <ul>
            <li :class="!price.additional ? 'striked' : ''">Linux administration</li>
            <li :class="!price.additional ? 'striked' : ''">DBMS (MySQL, SQL Server)</li>
        </ul>
        <a href="!#">BUY {{ price.title }}</a>
    </div>
</template>

<script>
    export default {
        name: 'PricingCard',
        props: {
            prices: { Type: Array }
        }
    }
</script>

<style lang="sass" scoped>
    .card__wrapper
        flex: 1
        display: flex
        flex-direction: column
        align-items: center
        justify-content: space-space-around
        padding: 2em
        border-bottom: 1px solid lightgrey
        a
            margin-top: 25px
            text-align: center
            text-decoration: none
            color: #000
            cursor: pointer
        &:first-of-type
            border-right: 1px solid lightgrey
        i
            font-size: 2rem
            color: teal
        i, h3, p
            margin-bottom: 20px
        p
            position: relative
            #currency
                font-size: 1rem
                position: absolute
                left: -15px
                
            #price
                font-size: 2rem
                font-weight: 700
                margin-right: 10px
        li
            text-align: center
            list-style: none
            margin-bottom: 12px
            font-weight: 300
            &.striked
                color: grey
                text-decoration: line-through
</style>