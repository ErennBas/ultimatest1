<template>
	<div class="layout-topbar p-shadow-4">
		<div class="layout-topbar-left">
			<router-link class="layout-topbar-logo" to="/">
				<img id="logo" src="assets/layout/images/logo-light.svg" alt="ultima-layout" style="height: 2.25rem">
			</router-link>

			<a class="layout-menu-button p-shadow-6 p-ripple" @click="onMenuButtonClick($event)" v-ripple>
				<i class="pi pi-chevron-right"></i>
			</a>

			<a class="layout-topbar-mobile-button p-ripple" @click="onTopbarMobileButtonClick($event)" v-ripple>
				<i class="pi pi-ellipsis-v fs-large"></i>
			</a>
		</div>

		<div class="layout-topbar-right" :class="{'layout-topbar-mobile-active': mobileTopbarActive}">
			<div class="layout-topbar-actions-left">
				<MegaMenu :model="items" class="layout-megamenu"></MegaMenu>
			</div>

			<div class="layout-topbar-actions-right">
				<ul class="layout-topbar-items">
					<li class="layout-topbar-item layout-search-item">
						<a class="layout-topbar-action rounded-circle p-ripple" @click="onTopbarItemClick($event, 'search')" v-ripple>
							<i class="pi pi-search fs-large"></i>
						</a>

						<transition name="layout-search-panel" @enter="onEnter">
							<div class="layout-search-panel p-inputgroup" v-show="searchActive" @click="onSearchContainerClick">
								<span class="p-inputgroup-addon"><i class="pi pi-search"></i></span>
								<InputText ref="searchInput" type="text" placeholder="Search" @keydown="onSearchKeydown($event)" />
								<span class="p-inputgroup-addon">
									<Button icon="pi pi-times" class="p-button-rounded p-button-text p-button-plain" @click="changeSearchActive"></Button>
								</span>
							</div>
						</transition>
					</li>

					<li class="layout-topbar-item notifications">
						<a class="layout-topbar-action rounded-circle p-ripple" @click="onTopbarItemClick($event, 'notifications')" v-ripple>
							<span class="p-overlay-badge" v-badge.warning>
								<i class="pi pi-bell fs-large"></i>
							</span>
						</a>

						<transition name="layout-topbar-action-panel">
							<ul class="layout-topbar-action-panel p-shadow-6" v-show="activeTopbarItem === 'notifications'">
								<li class="p-mb-3">
									<span class="p-px-3 fs-small">You have <b>4</b> new notifications</span>
								</li>
								<li class="layout-topbar-action-item">
									<div class="p-d-flex p-flex-row p-ai-center">
										<img src="assets/demo/images/avatar/amyelsner.png"/>
										<div class="p-d-flex p-flex-column" :class="{'p-ml-3': !isRTL, 'p-mr-3': isRTL}" style="flex-grow: 1;">
											<div class="p-d-flex p-ai-center p-jc-between p-mb-1">
												<span class="fs-small p-text-bold">Jerome Bell</span>
												<small>42 mins ago</small>
											</div>
											<span class="fs-small">How to write content about your photographs?</span>
										</div>
									</div>
								</li>
								<li class="layout-topbar-action-item">
									<div class="p-d-flex p-flex-row p-ai-center">
										<img src="assets/demo/images/avatar/annafali.png"/>
										<div class="p-d-flex p-flex-column" :class="{'p-ml-3': !isRTL, 'p-mr-3': isRTL}" style="flex-grow: 1;">
											<div class="p-d-flex p-ai-center p-jc-between p-mb-1">
												<span class="fs-small p-text-bold">Cameron Williamson</span>
												<small>48 mins ago</small>
											</div>
											<span class="fs-small">Start a blog to reach your creative peak.</span>
										</div>
									</div>
								</li>
								<li class="layout-topbar-action-item">
									<div class="p-d-flex p-flex-row p-ai-center">
										<img src="assets/demo/images/avatar/bernardodominic.png"/>
										<div class="p-d-flex p-flex-column" :class="{'p-ml-3': !isRTL, 'p-mr-3': isRTL}" style="flex-grow: 1;">
											<div class="p-d-flex p-ai-center p-jc-between p-mb-1">
												<span class="fs-small p-text-bold">Anna Miles</span>
												<small>1 day ago</small>
											</div>
											<span class="fs-small">Caring is the new marketing</span>
										</div>
									</div>
								</li>
								<li class="layout-topbar-action-item">
									<div class="p-d-flex p-flex-row p-ai-center">
										<img src="assets/demo/images/avatar/stephenshaw.png"/>
										<div class="p-d-flex p-flex-column" :class="{'p-ml-3': !isRTL, 'p-mr-3': isRTL}" style="flex-grow: 1;">
											<div class="p-d-flex p-ai-center p-jc-between p-mb-1">
												<span class="fs-small p-text-bold">Arlene Mccoy</span>
												<small>4 day ago</small>
											</div>
											<span class="fs-small">Starting your traveling blog with Vasco.</span>
										</div>
									</div>
								</li>
							</ul>
						</transition>
					</li>

					<li class="layout-topbar-item app">
						<a class="layout-topbar-action rounded-circle p-ripple" @click="onTopbarItemClick($event, 'apps')" v-ripple>
							<i class="pi pi-table fs-large"></i>
						</a>

						<transition name="layout-topbar-action-panel">
								<div class="p-grid p-nogutter layout-topbar-action-panel p-shadow-6" v-show="activeTopbarItem === 'apps'">	
									<div class="layout-topbar-action-item p-col-4">
										<a class="p-d-flex p-ai-center p-flex-column text-color p-ripple" v-ripple>
											<i class="pi pi-image action indigo-bgcolor white-color"></i>
											<span>Products</span>
										</a>
									</div>
									<div class="layout-topbar-action-item p-col-4">
										<a class="p-d-flex p-ai-center p-flex-column text-color p-ripple" v-ripple>
											<i class="pi pi-file-pdf action orange-bgcolor white-color"></i>
											<span>Reports</span>
										</a>
									</div>
									<div class="layout-topbar-action-item p-col-4">
										<a class="p-d-flex p-ai-center p-flex-column text-color p-ripple" v-ripple>
											<i class="pi pi-dollar action teal-bgcolor white-color"></i>
											<span>Balance</span>
										</a>
									</div>
									<div class="layout-topbar-action-item p-col-4">
										<a class="p-d-flex p-ai-center p-flex-column text-color p-ripple" v-ripple>
											<i class="pi pi-cog action pink-bgcolor white-color"></i>
											<span>Settings</span>
										</a>
									</div>
									<div class="layout-topbar-action-item p-col-4">
										<a class="p-d-flex p-ai-center p-flex-column text-color p-ripple" v-ripple>
											<i class="pi pi-key action bluegrey-bgcolor white-color"></i>
											<span>Credentials</span>
										</a>
									</div>
									<div class="layout-topbar-action-item p-col-4">
										<a class="p-d-flex p-ai-center p-jc-center p-flex-column text-color p-ripple" v-ripple>
											<i class="pi pi-sitemap action cyan-bgcolor white-color"></i>
											<span>Sitemap</span>
										</a>
									</div>
								</div>
						</transition>
					</li>

					<li class="layout-topbar-item">
						<a class="layout-topbar-action p-d-flex p-dir-row p-jc-center p-ai-center p-px-2 rounded-circle p-ripple" @click="onTopbarItemClick($event, 'profile')" v-ripple>
							<img src="assets/demo/images/avatar/amyelsner.png" alt="avatar" style="width: 32px; height: 32px;">
						</a>

						<transition name="layout-topbar-action-panel">
							<ul class="layout-topbar-action-panel p-shadow-6" v-show="activeTopbarItem === 'profile'">
								<li class="layout-topbar-action-item">
									<a class="p-d-flex p-flex-row p-ai-center p-ripple" v-ripple>
										<i class="pi pi-cog" :class="{'p-mr-2': !isRTL, 'p-ml-2': isRTL}"></i>
										<span>Settings</span>
									</a>
								</li>
								<li class="layout-topbar-action-item">
									<a class="p-d-flex p-flex-row p-ai-center p-ripple" v-ripple>
										<i class="pi pi-file-o" :class="{'p-mr-2': !isRTL, 'p-ml-2': isRTL}"></i>
										<span>Terms of Usage</span>
									</a>
								</li>
								<li class="layout-topbar-action-item">
									<a class="p-d-flex p-flex-row p-ai-center p-ripple" v-ripple>
										<i class="pi pi-compass" :class="{'p-mr-2': !isRTL, 'p-ml-2': isRTL}"></i>
										<span>Support</span>
									</a>
								</li>
								<li class="layout-topbar-action-item">
									<a class="p-d-flex p-flex-row p-ai-center p-ripple" v-ripple>
										<i class="pi pi-power-off" :class="{'p-mr-2': !isRTL, 'p-ml-2': isRTL}"></i>
										<span>Logout</span>
									</a>
								</li>
							</ul>
						</transition>
					</li>

					<li class="layout-topbar-item">
						<a class="layout-topbar-action rounded-circle p-ripple" @click="onRightPanelButtonClick($event)" v-ripple>
							<i class="pi fs-large" :class="{'pi-arrow-left': !isRTL, 'pi-arrow-right': isRTL}"></i>
						</a>
					</li>
				</ul>
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		emits: ['menubutton-click', 'topbar-menubutton-click', 'topbaritem-click', 'rightpanel-button-click', 'topbar-mobileactive', 'search-click', 'search-toggle'],
		data() {
			return {
				searchText: '',
				items: [
					{
						label: 'UI KIT',
						items: [
							[
								{
									label: 'UI KIT 1',
									items: [
										{ label: 'Form Layout', icon: 'pi pi-fw pi-id-card', to: '/formlayout' },
										{ label: 'Input', icon: 'pi pi-fw pi-check-square', to: '/input' },
										{ label: 'Float Label', icon: 'pi pi-fw pi-bookmark', to: '/floatlabel' },
										{ label: 'Button', icon: 'pi pi-fw pi-mobile', to: '/button' },
										{ label: 'File', icon: 'pi pi-fw pi-file', to: '/file' }
									]
								}
							],
							[
								{
									label: 'UI KIT 2',
									items: [
										{ label: 'Table', icon: 'pi pi-fw pi-table', to: '/table' },
										{ label: 'List', icon: 'pi pi-fw pi-list', to: '/list' },
										{ label: 'Tree', icon: 'pi pi-fw pi-share-alt', to: '/tree' },
										{ label: 'Panel', icon: 'pi pi-fw pi-tablet', to: '/panel' },
										{ label: 'Chart', icon: 'pi pi-fw pi-chart-bar', to: '/chart' }
									]
								}
							],
							[
								{
									label: 'UI KIT 3',
									items: [
										{ label: 'Overlay', icon: 'pi pi-fw pi-clone', to: '/overlay' },
										{ label: 'Media', icon: 'pi pi-fw pi-image', to: '/media' },
										{ label: 'Menu', icon: 'pi pi-fw pi-bars', to: '/menus' },
										{ label: 'Message', icon: 'pi pi-fw pi-comment', to: '/messages' },
										{ label: 'Misc', icon: 'pi pi-fw pi-circle-off', to: '/misc' }
									]
								}
							]
						]
					},
					{
						label: 'UTILITIES',
						items: [
							[
								{
									label: 'UTILITIES 1',
									items: [
										{ label: 'Display', icon: 'pi pi-fw pi-desktop', to: '/display' },
										{ label: 'Elevation', icon: 'pi pi-fw pi-external-link', to: '/elevation' }
									]
								},
								{
									label: 'UTILITIES 2',
									items: [
										{ label: 'FlexBox', icon: 'pi pi-fw pi-directions', to: '/flexbox' }
									]
								}
							],
							[
								{
									label: 'UTILITIES 3',
									items: [
										{ label: 'Icons', icon: 'pi pi-fw pi-search', to: '/icons' }
									]
								},
								{
									label: 'UTILITIES 4',
									items: [
										{ label: 'Text', icon: 'pi pi-fw pi-pencil', to: '/text' },
										{ label: 'Widgets', icon: 'pi pi-fw pi-star-o', to: '/widgets' }
									]
								}
							],
							[
								{
									label: 'UTILITIES 5',
									items: [
										{ label: 'Grid System', icon: 'pi pi-fw pi-th-large', to: '/grid' },
										{ label: 'Spacing', icon: 'pi pi-fw pi-arrow-right', to: '/spacing' },
										{ label: 'Typography', icon: 'pi pi-fw pi-align-center', to: '/typography' }
									]
								}
							],
						]
					}
				],
			}
		},
		props: {
			horizontal: {
				type: Boolean,
				default: false
			},
			topbarMenuActive: {
				type: Boolean,
				default: false
			},
			activeTopbarItem: String,
			mobileTopbarActive: Boolean,
			searchActive: Boolean
		},
		methods: {
			onSearchContainerClick(event) {
				this.$emit("search-click", event);
			},
			changeSearchActive(event) {
				this.$emit('search-toggle', event);
			},
			onMenuButtonClick(event) {
				this.$emit('menubutton-click', event);
			},
			onTopbarMenuButtonClick(event) {
				this.$emit('topbar-menubutton-click', event);
			},
			onTopbarItemClick(event, item) {
				if(item === 'search') {
					this.$emit('search-toggle', event);
				}

				this.$emit('topbaritem-click', {originalEvent: event, item: item});
			},
			onTopbarMobileButtonClick(event) {
				this.$emit('topbar-mobileactive', event);
			},
			onRightPanelButtonClick(event) {
				this.$emit('rightpanel-button-click', event);
			},
			onSearchKeydown(event) { 
				if (event.keyCode == 13) {
					this.$emit('search-toggle', event);
				}
			},
			onEnter() {
				if (this.$refs.searchInput) {
					this.$refs.searchInput.$el.focus();
				}
			}
		},
		computed: {
			topbarItemsClass() {
				return ['topbar-items animated fadeInDown', {
					'topbar-items-visible': this.topbarMenuActive
				}];
			},
			isRTL() {
				return this.$appState.RTL;
			}
		}
	}
</script>
