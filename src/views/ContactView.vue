<template>
    <div class="section__wrapper">
        <div class="section__title">
            <span class="background__circle"></span>
            <h2><span class="highlight__text">Get</span> in Touch</h2>
        </div>
        <div class="contact__wrapper">
            <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2829.844194200485!2d20.39617861580451!3d44.82473868390302!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x475a65835fcd6159%3A0x2da02120473da87e!2sTo%C5%A1in%20bunar%20147%2C%20Beograd%2011000%2C%20Serbia!5e0!3m2!1sen!2sba!4v1658434311989!5m2!1sen!2sba" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
            <div class="info__wrapper">
                <p>
                    <span id="boldText">E-MAIL</span> => lazarlalovic@gmail.com
                    <br />
                    <br />
                    <span id="boldText">PHONE</span> => +381/64-923-8252
                </p>
                <p>
                    <span id="boldText">ADDRESS</span> => TOŠIN BUNAR 147
                    <br />
                    <br />
                    <span id="boldText">LinkedIn</span> => <a href="https://www.linkedin.com/in/lazar-lalovi%C4%87-1a59a1233/">Profile</a>
                </p>
            </div>
            <span>Feel free to write!</span>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'ContactView'
    }
</script>

<style lang="sass" scoped>
    .section__title
        margin-bottom: 20px
    .contact__wrapper
        width: 100%
        padding: 1em
        display: flex
        flex-direction: column
        align-items: center
        .info__wrapper
            width: 100%
            display: flex
            align-items: center
            justify-content: space-around
            font-weight: 300
            margin: 50px 0
            a
                text-decoration: none
                color: teal
                cursor: pointer
                font-weight: 700
            #boldText
                font-weight: 700
        iframe
            border: 0
            height: 300px
            width: 100%
    @media screen and (max-width: 600px)
        .info__wrapper
            flex-direction: column
            p
                width: 100%
                margin-bottom: 20px
</style>