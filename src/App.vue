<template>
    <v-app>
        <div class="container">
            <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    		<app-new-quote @quoteAdded="newQuote"></app-new-quote>
        	<app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>
            <div class="row">
                <div class="s12 center-align">
                    <v-alert color="info" icon="info" value="true">
                      Info: Click in a quote to delete it!
                    </v-alert>
                </div>
            </div>
        </div>
    </v-app>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue';
    import NewQuote from './components/NewQuote.vue';
    import Header from './components/Header.vue';

    export default {
        data() {
        	return {
                quotes: [
                    'Quote'
                ],
        		maxQuotes: 10
        	}
        },
        methods: {
        	newQuote(quote) {
                if (quote <= 0) {
                    return Materialize.toast('The quote must have at least one character!', 5000);
                }
                if (this.quotes.length >= this.maxQuotes) {
                    return Materialize.toast('Quotes limit reached! Delete one to continue!', 5000);
                }
        		this.quotes.push(quote);
        	},
            deleteQuote(index) {
                this.quotes.splice(index, 1);
            }
        },
        components: {
        	appQuoteGrid: QuoteGrid,
        	appNewQuote: NewQuote,
            appHeader: Header
        }
    }
</script>

<style>
</style>
