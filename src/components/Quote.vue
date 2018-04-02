<template>
    <div class="col s6 m4 l3">
    	<div class="card-panel quote">
    		<slot></slot>
        </div>
    </div>
</template>

<style>
	.card-panel {
		font-family: 'Arizonia', cursive;
		font-size: 24px;
		color: #6e6e6e;
	}

	.quote {
		cursor: pointer;
	}

	.quote:hover {
		color: #ffe2e2;
	}

	.nota-font {
		font-family: 'Arizonia', cursive;
	}
</style>
