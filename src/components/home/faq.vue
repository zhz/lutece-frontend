<template>
	<v-container>
		<v-layout
			row
			fill-height
			align-center
			justify-center
			wrap
		>
			<v-flex
				xs12
				sm12
				md12
				lg12
				xl10
			>
				<div class = "font-weight-bold display-1 text-xs-center">
					{{ title }}
				</div>
				<async-mixrend-component-with-loading-spinner
					:content = "require('@/docs/faq.md')"
					class = "mt-3 markdown-body"
					style = "fontSize: 14px; padding-top:20px;"
				/>
			</v-flex>
		</v-layout>
	</v-container>
</template>

<script>

import { AsyncMixrendComponentWithLoadingSpinner } from '@/components/async/mixrend/index';

export default {
	components: {
		AsyncMixrendComponentWithLoadingSpinner,
	},
	data() {
		return {
			title: 'Lutece FAQ',
		};
	},
};
</script>

<style scope>
	p {
		margin-bottom: 6px !important;
	}
</style>
