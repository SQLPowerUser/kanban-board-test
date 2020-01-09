<template>
	<div class="container">
		<Card
			v-for="(arrValues, category) in cards"
			:key="category"
			:notes="arrValues"
			:caption="category"
		></Card>
		
		<router-view name="fogOver"></router-view>
		<router-view name="editCard"></router-view>
	</div> <!-- class="container" -->
</template>

<script>
import Card     from './components/card.vue';
import EditCard from './components/editCard.vue';
import FogOver  from './components/fogOver.vue';

export default {
	computed: {
		cards() {
			return this.$store.state.cards;
		},
	},

	components: {
		Card,
		EditCard,
		FogOver
	}
}
</script>