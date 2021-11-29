<template>
    <div class="layout-inline-menu" :class="{'layout-inline-menu-active': active}">
    <a class="layout-inline-menu-action p-d-flex p-dir-row p-ai-center" :class="menuMode === 'horizontal' ? 'p-p-3 p-p-lg-1 p-py-3' : 'p-p-3'" :style="{'min-width': menuMode === 'horizontal' ? '165px' : 0} " @click="onClick($event)">
        <img src="assets/demo/images/avatar/amyelsner.png" alt="avatar" style="width: 32px; height: 32px;">
        <span class="p-d-flex p-flex-column" :class="{'p-ml-2': !isRTL, 'p-mr-2': isRTL}">
            <span class="p-text-bold">Amy Elsner</span>
            <small>Webmaster</small>
        </span>
        <i class="layout-inline-menu-icon pi pi-angle-down" :class="{'p-ml-auto': !isRTL, 'p-mr-auto': isRTL}"></i>
    </a>
    <span class="layout-inline-menu-tooltip p-tooltip">
		<span class="layout-inline-menu-tooltip-arrow p-tooltip-arrow"></span>
		<span class="layout-inline-menu-tooltip-text p-tooltip-text">Amy Elsner</span>
	</span>
    
    <transition :name="menuMode === 'horizontal' && !isMobile() ? 'layout-inline-menu-action-panel-horizontal' : 'layout-inline-menu-action-panel'">
        <ul v-show="active" :class="['layout-inline-menu-action-panel', { 'layout-inline-menu-action-panel-horizontal' : menuMode === 'horizontal' && !isMobile()}]">
            <li class="layout-inline-menu-action-item">
                <a class="p-d-flex p-flex-row p-ai-center">
                    <i class="pi pi-cog pi-fw"></i>
                    <span>Settings</span>
                </a>
                <span class="layout-inline-menu-tooltip p-tooltip">
					<span class="layout-inline-menu-tooltip-arrow p-tooltip-arrow"></span>
					<span class="layout-inline-menu-tooltip-text p-tooltip-text">Settings</span>
				</span>
            </li>
            <li class="layout-inline-menu-action-item">
                <a class="p-d-flex p-flex-row p-ai-center">
                    <i class="pi pi-file-o pi-fw"></i>
                    <span>Terms of Usage</span>
                </a>
                <span class="layout-inline-menu-tooltip p-tooltip">
					<span class="layout-inline-menu-tooltip-arrow p-tooltip-arrow"></span>
					<span class="layout-inline-menu-tooltip-text p-tooltip-text">Terms of Usage</span>
				</span>
            </li>
            <li class="layout-inline-menu-action-item">
                <a class="p-d-flex p-flex-row p-ai-center">
                    <i class="pi pi-compass pi-fw"></i>
                    <span>Support</span>
                </a>
                <span class="layout-inline-menu-tooltip p-tooltip">
					<span class="layout-inline-menu-tooltip-arrow p-tooltip-arrow"></span>
					<span class="layout-inline-menu-tooltip-text p-tooltip-text">Support</span>
				</span>
            </li>
            <li class="layout-inline-menu-action-item">
                <a class="p-d-flex p-flex-row p-ai-center">
                    <i class="pi pi-power-off pi-fw"></i>
                    <span>Logout</span>
                </a>
                <span class="layout-inline-menu-tooltip p-tooltip">
					<span class="layout-inline-menu-tooltip-arrow p-tooltip-arrow"></span>
					<span class="layout-inline-menu-tooltip-text p-tooltip-text">Logout</span>
				</span>
            </li>
    </ul>
    </transition>
</div>

</template>

<script>
	export default {
        name: "AppInlineMenu",
        props: {
            active: {
                type: Boolean,
                default: false
            },
            menuMode: String,
            inlineMenuKey: String
        },
		methods: {
			onClick(event) {
                this.$emit('change-inlinemenu', !this.active, this.inlineMenuKey);
				event.preventDefault();
			},
            isMobile() {
                return window.innerWidth <= 991;
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
