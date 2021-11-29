<template>
	<div class="pages-body accessdenied-page p-d-flex p-flex-column">
		<div class="topbar p-p-3 p-d-flex p-jc-between p-flex-row p-ai-center">
			<router-link class="topbar-left p-ml-3 p-d-flex" to="/">
				<div class="logo">
					<img src="assets/layout/images/logo2x.png" alt=""/>
				</div>
			</router-link>
			<router-link class="topbar-right p-mr-3 p-d-flex" to="/">
				<Button type="button" label="DASHBOARD" class="p-button-text p-button-plain topbar-button"></button>
			</router-link>
		</div>

		<div class="p-as-center p-mt-auto p-mb-auto">
			<div class="pages-panel card p-d-flex p-flex-column">
				<div class="pages-header p-px-3 p-py-1">
					<h2>ACCESS DENIED</h2>
				</div>
				<div class="card p-mt-3 p-px-6">
					<img src="assets/layout/images/pages/error.png" alt=""/>
				</div>
				<div class="pages-detail p-pb-6">Requested resource is not available.</div>
				<router-link to="/">
					<Button type="button" label="GO BACK TO DASHBOARD" class="p-button-text"></Button>
				</router-link>
			</div>
		</div>
	</div>

</template>

<script>
</script>

<style scoped>

</style>
