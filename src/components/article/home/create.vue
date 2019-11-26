<template>
	<v-container
		fluid
		grid-list-lg
	>
		<v-layout
			row
			wrap
			align-center
			justify-center
		>
			<v-flex
				xs12
				sm12
				md12
				lg12
				xl10
			>
				<article-setting
					:title = "title"
					:content = "content"
					:with-preview = "true"
					:excerpt = "excerpt"
					:submit = "submit"
					form-title = "Create Blog"
					@input-title = "title = $event"
					@input-content = "content = $event"
					@input-excerpt = "excerpt = $event"
					@input-disabled = "disabled = $event ? true : false"
				/>
			</v-flex>
		</v-layout>
	</v-container>
</template>

<script>

import gql from '@/plugins/essential/graphql-tag';
import ArticleSetting from '../edit/setting';
import { clearApolloCache } from '@/utils';

export default {
	components: {
		ArticleSetting,
	},

	data() {
		return {
			title: '',
			content: '',
			excerpt: '',
		};
	},

	methods: {
		submit(data) {
			const mutation = gql`
                mutation CreateHomeArticle( $title: String! , $excerpt: String! ,$content: String! ){
                    createHomeArticle( title: $title, excerpt: $excerpt, content: $content ){
                        slug
                    }
                }
            `;
			return this.$apollo.mutate({
				mutation,
				variables: {
					title: data.title,
					content: data.content,
					excerpt: data.excerpt,
				},
			}).then((response) => {
				clearApolloCache().finally(
					() => {
						this.$router.push({
							name: 'BlogDetail',
							params: {
								slug: response.data.createHomeArticle.slug,
							},
						});
					},
				);
			});
		},
	},
};
</script>
