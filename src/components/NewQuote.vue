<template>
    <div class="row">
    	<form>
    		<div class="col s8 offset-s2 xl-12 m6 offset-m3">
    			<label>Quote</label>
    			<textarea class="materialize-textarea" rows="3" v-model="quote"></textarea>
    		</div>
    		<div class="col s8 offset-s2 xl-12 m6 offset-m3">
    			<v-btn color="blue-grey" dark @click.prevent="createNew">Add Quote</v-btn>
    		</div>
    	</form>
    </div>
</template>

<script>
	import Quote from '../components/Quote.vue';
	
	export default {
		data() {
			return {
				quote: ''
			}
		},
		methods: {
			createNew() {
				this.$emit('quoteAdded', this.quote);
				this.quote = '';
			}
		}
	}
</script>

<style>

</style>
