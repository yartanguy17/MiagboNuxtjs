<template lang="html">
    <div class="ps-home-banner ps-home-banner--1" v-if="!$fetchState.pending">
        <div class="ps-container">
            <div class="ps-section__left">
                <div class="ps-carousel" v-swiper:mySwiper="swiperOption">
                    <div class="swiper-wrapper">
                        <div class="swiper-slide">
                            <div class="ps-banner">
                                <nuxt-link to="/shop">
                                    <a>
                                        <img
                                            src="@/static/images/slider-2-1.jpeg"
                                            alt="martfury"
                                            width="1230px"
                                            height="700px"
                                        />
                                    </a>
                                </nuxt-link>
                            </div>
                        </div>
                        <div class="swiper-slide">
                            <div class="ps-banner">
                                <nuxt-link to="/shop">
                                    <a>
                                        <img
                                            src="@/static/images/slider-2-2.jpeg"
                                            alt="martfury"
                                            width="1230px"
                                            height="700px"
                                        />
                                    </a>
                                </nuxt-link>
                            </div>
                        </div>
                        <div class="swiper-slide">
                            <div class="ps-banner">
                                <nuxt-link to="/shop">
                                    <a>
                                        <img
                                            src="@/static/images/slider-2-3.jpeg"
                                            alt="martfury"
                                            width="1230px"
                                            height="700px"
                                        />
                                    </a>
                                </nuxt-link>
                            </div>
                        </div>
                        <div class="swiper-slide">
                            <div class="ps-banner">
                                <nuxt-link to="/shop">
                                    <a>
                                        <img
                                            src="@/static/images/slider-2-4.jpeg"
                                            alt="martfury"
                                            width="1230px"
                                            height="700px"                                            
                                        />
                                    </a>
                                </nuxt-link>
                            </div>
                        </div>
                    </div>
                    <!--Carousel controls-->
                    <div class="swiper-nav">
                        <span class="swiper-arrow swiper-prev"
                            ><i class="icon-chevron-left"></i
                        ></span>
                        <div class="swiper-arrow swiper-next">
                            <i class="icon-chevron-right"></i>
                        </div>
                    </div>
                    <div
                        class="swiper-pagination swiper-pagination-bullets"
                    ></div>
                </div>
            </div>
            <div class="ps-section__right">
                <nuxt-link to="/shop" class="ps-collection">
                    <img
                        src="@/static/images/slider-1.jpeg"
                        alt="martfury"
                    />
                </nuxt-link>
                <nuxt-link to="/shop" class="ps-collection">
                    <img
                        src="@/static/images/slider-3.jpeg"
                        alt="martfury"
                    />
                </nuxt-link>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'HomeBanner',
    data() {
        return {
            swiperOption: {
                loop: true,
                slidesPerView: 1,
                spaceBetween: 1,
                navigation: {
                    nextEl: '.swiper-next',
                    prevEl: '.swiper-prev'
                }
            },
            baseUrl : 'http://51.89.97.33:5500',
            products: [],
        };
    }, 
    async fetch(){
        this.products = await fetch('http://51.89.97.33:5500/api/products')
            .then(res => res.json());
    }
};
</script>

<style lang="scss" scoped></style>
