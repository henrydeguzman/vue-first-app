<template>
	<li>
		<h2>{{ name }}</h2>
		<button @click="toggleDetails">
			{{ detailsAreVisible ? "Hide" : "Show" }} Details
		</button>
		<ul v-if="detailsAreVisible">
			<li>
				<strong>Phone:</strong>
				{{ phoneNumber }}
			</li>
			<li>
				<strong>Email:</strong>
				{{ emailAddress }}
			</li>
		</ul>
	</li>
</template>

<script>
export default {
     // props: [
     //      'name',
     //      'phoneNumber',
     //      'emailAddress'
     // ],
     props: {
          name: {
               type: String,
               required: true
          },
          phoneNumber: String,
          emailAddress: String,
          isFavorite: String
     },
	data() {
		return {
			detailsAreVisible: false
		};
	},
	methods: {
		toggleDetails() {
			this.detailsAreVisible = !this.detailsAreVisible;
          }
     }     
};
</script>
