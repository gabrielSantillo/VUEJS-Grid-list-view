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
            let button = document.querySelector(`button`);
            button.addEventListener(`click`, this.injectTweet)
        },

methods: {
    injectTweet() {
        let tweet_card = document.getElementsByClassName(`tweet_card`);
        tweet_card
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