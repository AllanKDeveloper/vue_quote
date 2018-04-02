<template>
	<div class="row">
		<div class="s12 center-align">
			<h3 class="nota-font">Quotes Added</h3>
			<v-progress-circular
		      v-bind:size="100"
		      v-bind:width="15"
		      v-bind:rotate="360"
		      v-bind:value="(quoteCount / maxQuotes) * 100"
		      color="teal"
		    >
		      {{ quoteCount }} / {{ maxQuotes }}
		    </v-progress-circular>

<!-- 		<div class="progress">
				<div class="determinate" :style="{ width: (quoteCount / maxQuotes) * 100  + '%' }"></div>
			</div> -->
			<span> </span>
		</div>
	</div>
</template>

<script>
	export default {
		props: ['quoteCount', 'maxQuotes']
	}
</script>