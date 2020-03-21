<template lang="html">

	<section class="load-more-content">
		<div :class="classname" v-for="data in datas" :key="data">{{data.content}}</div>
		<div :id="id">Load More</div>
	</section>

</template>

<script>
import $ from 'jquery';

	export default {
		name: 'LoadMoreContent',
		props: {
			id: {
				type: String
			},
			classname: {
				type: String
			},
			datas: {
				type: Array
			},
			count: {
				type: Number
			}
		},
		mounted () {
			let cln = "." + this.classname;
      const idn = "#" + this.id;
      let cnt = this.count;
			$(document).ready(function() {
				$(cln).slice(0, cnt).show();
				$(cln).slice(cnt, $(cln).length).hide();
				if ($(cln + ":hidden").length !== 0) {
					$(idn).show();
				}
				$(idn).on('click', function(e) {
					e.preventDefault();
					$(cln + ":hidden").slice(0, cnt).slideDown();
					if ($(cln + ":hidden").length === 0) {
						$(idn).fadeOut('slow');
					}
				});
			});
		},
		data () {
			return {

			}
		},
		methods: {

		},
		computed: {

		}
}


</script>

<style scoped lang="scss">
	.load-more-content {

	}
</style>
