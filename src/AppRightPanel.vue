<template>
	<Sidebar v-model:visible="d_expanded" @hide="$emit('hide', d_expanded)" @click="$emit('content-click',$event)" :position="isRTL ? 'left' : 'right'" :showCloseIcon="false"
		:baseZIndex="1000" class="layout-rightmenu p-sidebar-sm fs-small p-py-3 " :class="isRTL ? 'p-pl-0 p-pr-3' : 'p-pl-3 p-pr-0'">
		<div class="online-members p-d-flex p-flex-column p-mt-3" :class="{'p-ml-3': !isRTL, 'p-mr-3': isRTL}">
			<h6 class="header">ONLINE MEMBERS</h6>
			<div class="p-d-flex p-flex-row p-flex-wrap">
				<img class="p-m-1" src="assets/demo/images/avatar/avatar-1.png" alt="avatar-1"/>
				<img class="p-m-1" src="assets/demo/images/avatar/avatar-2.png" alt="avatar-2"/>
				<img class="p-m-1" src="assets/demo/images/avatar/avatar-3.png" alt="avatar-3"/>
				<img class="p-m-1" src="assets/demo/images/avatar/avatar-4.png" alt="avatar-4"/>
				<img class="p-m-1" src="assets/demo/images/avatar/avatar-5.png" alt="avatar-5"/>
				<img class="p-m-1" src="assets/demo/images/avatar/avatar-6.png" alt="avatar-6"/>
				<img class="p-m-1" src="assets/demo/images/avatar/avatar-7.png" alt="avatar-7"/>
				<img class="p-m-1" src="assets/demo/images/avatar/avatar-8.png" alt="avatar-8"/>
				<img class="p-m-1" src="assets/demo/images/avatar/avatar-9.png" alt="avatar-9"/>
				<img class="p-m-1" src="assets/demo/images/avatar/avatar-10.png" alt="avatar-10"/>
				<img class="p-m-1" src="assets/demo/images/avatar/avatar-11.png" alt="avatar-11"/>
				<img class="p-m-1" src="assets/demo/images/avatar/avatar-12.png" alt="avatar-12"/>
				<img class="p-m-1" src="assets/demo/images/avatar/avatar-13.png" alt="avatar-13"/>
				<img class="p-m-1" src="assets/demo/images/avatar/avatar-14.png" alt="avatar-14"/>
				<img class="p-m-1" src="assets/demo/images/avatar/avatar-15.png" alt="avatar-15"/>
				<img class="p-m-1" src="assets/demo/images/avatar/avatar-16.png" alt="avatar-16"/>
			</div>
			<span class="p-mt-3"><b>+19</b> Costumers</span>
			</div>
			<div class="latest-activity p-d-flex p-flex-column p-mt-6" :class="{'p-ml-3': !isRTL, 'p-mr-3': isRTL}">
				<h6 class="header">LATEST ACTIVITY</h6>
				<div class="p-d-flex p-flex-row p-pt-2">
					<i class="pi pi-images p-as-start p-p-2" :class="{'p-mr-2': !isRTL, 'p-ml-2': isRTL}"></i>
				<div class="p-d-flex p-flex-column">
					<span class="p-text-bold p-mb-1">New Sale</span>
					<span class="p-mb-2">Richard Jones has purchased a blue t-shirt for $79.</span>
					<span class="p-d-flex p-ai-center">
						<img :class="{'p-mr-2': !isRTL, 'p-ml-2': isRTL}" src="assets/demo/images/avatar/activity-1.png" alt=""/>
						<small class="muted-text">Emmy Adams, 21.40</small>
					</span>
				</div>
			</div>
			<div class="p-d-flex p-flex-row p-pt-3">
				<i class="pi pi-images p-as-start p-p-2" :class="{'p-mr-2': !isRTL, 'p-ml-2': isRTL}"></i>
				<div class="p-d-flex p-flex-column">
					<span class="p-text-bold p-mb-1">Withdrawal Initiated</span>
					<span class="p-mb-2">Your request for withdrawal of $2500 has been initiated.</span>
					<span class="p-d-flex p-ai-center">
						<img :class="{'p-mr-2': !isRTL, 'p-ml-2': isRTL}" src="assets/demo/images/avatar/activity-2.png" alt="avatar-2"/>
						<small class="muted-text">Emily Walter, 21.40</small>
					</span>
				</div>
			</div>
			<div class="p-d-flex p-flex-row p-pt-3">
				<i class="pi pi-images p-as-start p-p-2" :class="{'p-mr-2': !isRTL, 'p-ml-2': isRTL}"></i>
				<div class="p-d-flex p-flex-column">
					<span class="p-text-bold p-mb-1">Question Received</span>
					<span class="p-mb-2">Jane Davis has posted a new question about your product.</span>
					<span class="p-d-flex p-ai-center">
						<img :class="{'p-mr-2': !isRTL, 'p-ml-2': isRTL}" src="assets/demo/images/avatar/activity-3.png" alt="avatar-3"/>
						<small class="muted-text">Jane Davis, 21.45</small>
					</span>
				</div>
			</div>
			</div>
			<div class="next-events p-d-flex p-flex-column p-mt-6" :class="{'p-ml-3': !isRTL, 'p-mr-3': isRTL}">
			<h6 class="header">NEXT EVENTS</h6>
			<ul>
				<li><i class="pi pi-eye" :class="{'p-mr-3': !isRTL, 'p-ml-3': isRTL}"></i>A/B Test</li>
				<li><i class="pi pi-video" :class="{'p-mr-3': !isRTL, 'p-ml-3': isRTL}"></i>Video Shoot</li>
				<li><i class="pi pi-sitemap" :class="{'p-mr-3': !isRTL, 'p-ml-3': isRTL}"></i>Board Meeting</li>
				<li><i class="pi pi-compass" :class="{'p-mr-3': !isRTL, 'p-ml-3': isRTL}"></i>Q4 Planning</li>
				<li><i class="pi pi-palette" :class="{'p-mr-3': !isRTL, 'p-ml-3': isRTL}"></i>Design Training</li>
			</ul>
		</div>
	</Sidebar>
</template>

<script>
	export default {
		name: "AppRightPanel",
		emits: ['content-click', 'hide'],
		props: {
			expanded: Boolean
		},
		data() {
			return {
				d_expanded: null
			}
		},
		watch: {
			expanded(value) {
				this.d_expanded = value;
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
