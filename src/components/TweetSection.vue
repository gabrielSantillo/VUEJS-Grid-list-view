<template>
    <div >
        <button>Change Grid</button>
        <div class="tweet_card">
            
        </div>
    </div>
</template>

<script>
    export default {

        methods: {
            /* this function changes the changes the layout of the content after a click in the button */
            changeGrid() {
                /* getting the div tag by its class */
                let tweet_card = document.querySelector(`.tweet_card`);
                /* if the at this index of the array the result is true will make the grid display as columns */
                if(this.tweets_array[0][`isDisplay`]){
                    /* changes the value of the display to false */
                    this.tweets_array[0].isDisplay = false;
                    tweet_card[`style`][`display`] = `grid`
                    tweet_card[`style`][`grid-auto-flow`] = `column`
                } 
                /* if the at this index of the array the result is false will make the grid display as rows */
                else {
                     /* changes the value of the display to true */
                    this.tweets_array[0].isDisplay = true;
                    tweet_card[`style`][`display`] = `grid`
                    tweet_card[`style`][`grid-auto-flow`] = `row`
                }

            }
        },

        mounted () {
            /* getting the div tag by its class */
            let tweet_card = document.querySelector(`.tweet_card`);
            /* going throughout the array and inserting onto the page eache tweet user, tweet and date */
            for(let i = 0;i <  this.tweets_array.length; i++) {
            tweet_card.insertAdjacentHTML(`beforeend`,
            `
            <div class="tweet_grid">
            <p>${this.tweets_array[i][`user`]}</p>
            <p>${this.tweets_array[i][`tweet`]}</p>
            <p>${this.tweets_array[i][`date`]}</p>
            </div>
            `)
            }

            /* getting the button using query selector */
            let button = document.querySelector(`button`);
            /* after that button is clicked call the function changeGrid */
            button.addEventListener(`click`, this.changeGrid)
        },

        data() {
            return {
            /* array of object of tweets. Each object has its user, the tweet and date */
            tweets_array:  [
            {
                user: `Gabriel`,
                tweet: `hello`,
                date: new Date(),
                /* this variable has its only purposes. be true and false to the toggle button can work */
                isDisplay: true
            },

            {
                user: `Alex`,
                tweet: `hello`,
                date: new Date()
            },

            {
                user: `Colleen`,
                tweet: `hello`,
                date: new Date()
            }
            ] 
            }
        },
    }
</script>

<style scoped>

</style>