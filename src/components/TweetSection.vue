<template>
    <div>
        <button>Change tweet</button>
        <div class="tweet_card">
            
        </div>
    </div>
</template>

<script>
    export default {

        mounted () {
            let tweet_card = document.querySelector(`.tweet_card`);
            tweet_card.insertAdjacentHTML(`beforeend`,
            `
            <p>${this.data[0][`user`]}</p>
            `)
        },

        methods: {
            injectTweet() {

                
            }
        },

        data() {
            return [{
                tweets: [`01_tweet`, `02_tweet`, `03_tweet`],
                user: `Gabriel`,
                date_created: new Date()
            },
            {
                tweets: [`04_tweet`, `05_tweet`, `06_tweet`],
                user: `Nadine`,
                date_created: new Date()
            },
            {
                tweets: [`07_tweet`, `08_tweet`, `09_tweet`],
                user: `Dawn`,
                date_created: new Date()
            }
            ]
        },
    }
</script>

<style scoped>

</style>