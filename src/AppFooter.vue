<template>
	<div class="layout-footer p-d-flex p-ai-center p-p-4 p-shadow-2">
        <img id="footer-logo" :src="'assets/layout/images/footer-' + (layoutMode === 'light' ? 'ultima' : 'ultima-dark') + '.svg'" alt="ultima-footer-logo">
        <Button icon="pi pi-github fs-large" class="p-button-rounded p-button-text p-button-plain" :class="{'p-ml-auto p-mr-2': !isRTL, 'p-ml-2 p-mr-auto': isRTL}"></Button>
        <Button icon="pi pi-facebook fs-large" class="p-button-rounded p-button-text p-button-plain" :class="{'p-mr-2': !isRTL, 'p-ml-2': isRTL}"></Button>
        <Button icon="pi pi-twitter fs-large" class="p-button-rounded p-button-text p-button-plain" :class="{'p-mr-2': !isRTL, 'p-ml-2': isRTL}"></Button>
    </div>
</template>

<script>
	export default {
		name: "AppFooter",
		props: {
			layoutMode: {
				type: String,
				default: 'light'
			}
		},
		computed: {
			isRTL() {
				return this.$appState.RTL;
			}
		}
	}
</script>

<style scoped>

</style>