<template>
<div class="landing-container">
    <div id="header" class="section p-d-flex p-flex-column">
        <div class="header-menu-container p-shadow-3 p-d-flex p-ai-center p-jc-between">
            <a class="layout-topbar-logo" href="/">
                <img src="assets/layout/images/logo2x.png" alt="ultima-layout" style="height: 24px">
            </a>

            <a id="menu-button" href="#" class="p-d-lg-none" @click="onMenuButtonClick($event)">
                <i class="pi pi-bars fs-xlarge"></i>
            </a>
            <ul ref="menu" id="menu" class="p-shadow-4">
                <li><a class="p-d-flex p-p-3">Home</a></li>
                <li><a @click="smoothScroll('#header')" class="p-d-flex p-p-3">Introduction</a></li>
                <li><a @click="smoothScroll('#features')" class="p-d-flex p-p-3">Features</a></li>
                <li><a @click="smoothScroll('#promotion')" class="p-d-flex p-p-3">Promotion</a></li>
                <li><a @click="smoothScroll('#pricing')" class="p-d-flex p-p-3">Pricing</a></li>
                <li><a @click="smoothScroll('#video')" class="p-d-flex p-pl-3 p-py-3">Video</a></li>
            </ul>
        </div>

        <div class="header-text p-d-flex p-flex-column p-ai-center p-jc-center">
            <h1 class="p-mb-6 white-color">Your application slogan comes here</h1>
            <Button type="button" label="Sign Up Now" class="p-button-secondary"></Button>
        </div>
    </div>

    <div id="features" class="section p-d-flex p-flex-column p-ai-center">
        <h2>The Ultimate Material Application Template for PrimeVue</h2>
        <p class="p-text-center">PrimeVue is a collection of rich UI components for Angular. PrimeVue is developed by PrimeTek Informatics, a vendor with years of expertise in developing open source UI solutions.
            Allocate your valuable time on business logic rather than dealing with the complex user interface requirements.
        </p>

        <div class="p-grid p-mt-3 p-mx-0">
            <div class="p-col-12 p-md-4 p-text-center">
                <h3>Creative</h3>
                <Button type="button" class="feature-button p-button-rounded p-button-plain p-button-text p-button p-component p-button-icon-only">
                    <span class="p-button-icon pi pi-pencil fs-xlarge" aria-hidden="true"></span>
                    <span aria-hidden="true" class="p-button-label">&amp;nbsp;</span>
                </button>
            </div>
            <div class="p-col-12 p-md-4 p-text-center">
                <h3>Responsive</h3>
                <Button type="button" class="feature-button p-button-rounded p-button-plain p-button-text p-button p-component p-button-icon-only">
                    <span class="p-button-icon pi pi-mobile fs-xlarge" aria-hidden="true"></span>
                    <span aria-hidden="true" class="p-button-label">&amp;nbsp;</span>
                </button>
            </div>
            <div class="p-col-12 p-md-4 p-text-center">
                <h3>Cross Browser</h3>
                <Button type="button" class="feature-button p-button-rounded p-button-plain p-button-text p-button p-component p-button-icon-only">
                    <span class="p-button-icon pi pi-upload fs-xlarge" aria-hidden="true"></span>
                    <span aria-hidden="true" class="p-button-label">&amp;nbsp;</span>
                </button>
            </div>

            <div class="p-col-12 p-md-4 p-text-center">
                <Button type="button" class="feature-button p-button-rounded p-button-plain p-button-text p-button p-component p-button-icon-only">
                    <span class="p-button-icon pi pi-tag fs-xlarge" aria-hidden="true"></span>
                    <span aria-hidden="true" class="p-button-label">&amp;nbsp;</span>
                </button>
                <h3>Well Organized</h3>
            </div>
            <div class="p-col-12 p-md-4 p-text-center">
                <Button type="button" class="feature-button p-button-rounded p-button-plain p-button-text p-button p-component p-button-icon-only">
                    <span class="p-button-icon pi pi-palette fs-xlarge" aria-hidden="true"></span>
                    <span aria-hidden="true" class="p-button-label">&amp;nbsp;</span>
                </button>
                <h3>Beautiful</h3>
            </div>
            <div class="p-col-12 p-md-4 p-text-center">
                <Button type="button" class="feature-button p-button-rounded p-button-plain p-button-text p-button p-component p-button-icon-only">
                    <span class="p-button-icon pi pi-check-circle fs-xlarge" aria-hidden="true"></span>
                    <span aria-hidden="true" class="p-button-label">&amp;nbsp;</span>
                </button>
                <h3>Just For you</h3>
            </div>
        </div>
    </div>

    <div id="promotion" class="p-d-flex p-flex-column p-ai-center">
        <div class="p-grid p-m-0 p-py-3 p-pl-xl-6">
            <div class="p-col-12 p-lg-8 p-d-flex p-flex-column p-jc-center p-ai-center p-ai-lg-start p-pl-6">
                <h1 class="white-color">Boost Your Productivity.</h1>
                <Button type="button" class="p-button-raised p-button p-compBnent">
                    <span class="p-button-label">Sign Up Now</span>
                </button>
            </div>
            <div class="p-col-12 p-lg-4">
                <div class="card p-mt-3 p-mb-0">
                    <h3>Just</h3>
                    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ab perferendis nesciunt ad reiciendis
                        explicabo consequatur sapiente odit ipsa harum illum</p>
                </div>

                <div class="card p-mt-3 p-mb-0">
                    <h3>Like</h3>
                    <p>Ab perferendis nesciunt ad reiciendis explicabo consequatur sapiente odit ipsa harum illum</p>
                </div>

                <div class="card p-my-3">
                    <h3>That</h3>
                    <p>Necessitatibus quaerat voluptates aspernatur iure, aperiam possimus sint sit mollitia! </p>
                </div>
            </div>
        </div>
    </div>

    <div id="pricing" class="section p-d-flex p-flex-column p-ai-center">
        <h2>Pricing</h2>
        <p>Esse delectus sit velit, aspernatur voluptates molestiae, enim recusandae. Odit dicta, maiores quas ad
            nesciunt, illum expedita veritatis illo quam odio id!</p>

        <div class="p-grid p-m-0 pricing-content">
            <div class="p-col-12 p-xl-4">
                <div class="card p-p-0">
                    <div class="p-d-flex p-flex-column p-ai-center indigo-bgcolor white-color p-p-6 fs-large">
                        <span>BASIC</span>
                        <h1 class="p-text-bold">$5</h1>
                        <span>Monthly</span>
                    </div>
                    <ul class="options">
                        <li><i class="pi pi-check"></i><span>Responsive</span></li>
                        <li><i class="pi pi-check"></i><span>Push Messages</span></li>
                    </ul>
                </div>
            </div>
            <div class="p-col-12 p-xl-4">
                <div class="card p-p-0">
                    <div class="p-d-flex p-flex-column p-ai-center pink-bgcolor white-color p-p-6 fs-large">
                        <span>STANDARD</span>
                        <h1 class="p-text-bold">$25</h1>
                        <span>Monthly</span>
                    </div>
                    <ul class="options">
                        <li><i class="pi pi-check"></i><span>Responsive</span></li>
                        <li><i class="pi pi-check"></i><span>Push Messages</span></li>
                        <li><i class="pi pi-check"></i><span>7/24 Support</span></li>
                        <li><i class="pi pi-check"></i><span>Free Shipping</span></li>
                    </ul>
                </div>
            </div>
            <div class="p-col-12 p-xl-4 pricing-box pricing-professional">
                <div class="card p-p-0">
                    <div class="p-d-flex p-flex-column p-ai-center cyan-bgcolor white-color p-p-6 fs-large">
                        <span>PROFESSIONAL</span>
                        <h1 class="p-text-bold">$50</h1>
                        <span>Monthly</span>
                    </div>
                    <ul class="options">
                        <li><i class="pi pi-check"></i><span>Responsive</span></li>
                        <li><i class="pi pi-check"></i><span>Push Messages</span></li>
                        <li><i class="pi pi-check"></i><span>7/24 Support</span></li>
                        <li><i class="pi pi-check"></i><span>Free Shipping</span></li>
                        <li><i class="pi pi-check"></i><span>Unlimited Bandwidth</span></li>
                        <li><i class="pi pi-check"></i><span>Unlimited Storage</span></li>
                        <li><i class="pi pi-check"></i><span>Gift Cards</span></li>
                    </ul>
                </div>
            </div>
        </div>
    </div>

    <div id="video" class="section p-d-flex p-flex-column p-ai-center p-jc-center">
        <h2>Video</h2>
        <p>Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque.</p>
        <div class="p-m-3">
            <iframe src="https://www.youtube.com/embed/B_lYGUtCd0g" frameborder="0" class="videoFrame"></iframe>
        </div>
    </div>

    <div id="footer" class="section p-d-flex p-ai-center p-jc-between p-flex-column p-flex-lg-row">
        <p>PrimeVue ULTIMA</p>

        <div class="p-py-3 p-d-flex p-ai-center">
            <ul class="p-my-3 p-mx-6">
                <li><a href="#mobile">Promotion</a></li>
                <li><a href="#pricing">Pricing</a></li>
                <li><a href="#video">Video</a></li>
            </ul>
            <ul class="p-my-3 p-ml-3">
                <li><a href="#">Home</a></li>
                <li><a href="#introduction">Introduction</a></li>
                <li><a href="#features">Features</a></li>
            </ul>
        </div>
    </div>
</div>

</template>

<script>
export default {
    data() {
        return {
            isMenuActive: false
        }
    },
    methods:  {
        onMenuButtonClick(e) {
            let menu = document.getElementById('menu');

            if (this.isMenuActive) {
                this.addClass(menu, 'fadeOutUp');
                this.isMenuActive = false;
            }
            else {
                this.addClass(menu, 'menu-active fadeInDown');
                this.isMenuActive = true;
            }
            e.preventDefault();
        },

        smoothScroll(id){
            document.querySelector(id).scrollIntoView({
                behavior: 'smooth'
            });
        },

        addClass(element, classNames) {
            let classNamesArr = classNames.split(' ');
            for (var i = 0; i < classNamesArr.length; i++) {
                let className = classNamesArr[i];
                if (element.classList)
                    element.classList.add(className);
                else
                    element.className += ' ' + className;
            }
        },

        removeClass(element, classNames) {
            let classNamesArr = classNames.split(' ');
            for (var i = 0; i < classNamesArr.length; i++) {
                let className = classNamesArr[i];
                if (element.classList)
                    element.classList.remove(className);
                else
                    element.className = element.className.replace(new RegExp('(^|\\b)' + className.split(' ').join('|') + '(\\b|$)', 'gi'), ' ');
            }
        }
    }
}
</script>

<style lang="scss" scoped>
.videoFrame{
    width: 560px;
    height: 300px;
    
    @media screen and (max-width: 960px) {
        width: 300px;
    }
}
</style>