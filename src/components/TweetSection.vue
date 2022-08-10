<template>
    <div >
        <button class="button_column">Change Grid</button>
        <div class="tweet_card">
            
        </div>
    </div>
</template>

<script>
    export default {

        methods: {
            changeGrid() {
                let tweet_card = document.querySelector(`.tweet_card`);
                tweet_card[`style`][`display`] = `grid`
                tweet_card[`style`][`grid-auto-flow`] = `column`
            },

            changeGridRow() {
                let tweet_card = document.querySelector(`.tweet_card`);
                tweet_card[`style`][`display`] = `grid`
                tweet_card[`style`][`grid-auto-flow`] = `row`
            }
        },

        mounted () {
            let tweet_card = document.querySelector(`.tweet_card`);
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

            let button = document.querySelector(`.button_column`);
            if(this.tweets_array[0][`isDisplay`]) {
                this.tweets_array[0].isDisplay = false;
                button.addEventListener(`click`, this.changeGrid);
            } else {
                this.tweets_array[0].isDisplay = true;
                button.addEventListener(`click`, this.changeGridRow);
            }            
        },

        data() {
            return {

            tweets_array:  [
            {
                user: `Gabriel`,
                tweet: `hello`,
                date: new Date(),
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