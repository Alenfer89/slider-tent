<template>
    <section id="portfolio" class="py-5">
        <div class="container">
            <div class="row">
                <div class="col-12 d-flex justify-content-between align-items-center py-5">
                    <div>
                        <p class="text-capitalize">our services</p>
                        <h2 class=" mb-3"><span class="ax-bold">latest</span> work</h2>
                    </div>
                    <div class="d-flex">
                        <div class="ax-swapper me-3">
                            <i class="fa-solid fa-arrow-left-long"></i>
                        </div>
                        <div class="ax-swapper">
                            <i class="fa-solid fa-arrow-right-long"></i>
                        </div>
                    </div>
                </div>
            </div>
            <div class="row">
                <div class="col-12 position-relative ax-slider-container p-0">
                    <CarouselCard
                    v-for='(element, index) in worksList'
                    :key='index'
                    :name='element.name'
                    :category='element.category'
                    :thumb='element.thumbnail'
                    :index='index' />
                </div>
                <div class="col-12 d-flex justify-content-center align-items-center p-5 mt-5">
                    <div class="slider-counter mx-1"
                    v-for='(element, index) in worksList'
                    :key="'slider' + index"
                    :class="(activeElement == index)? 'active' : ''">
                    </div>
                </div>
            </div>
        </div>
        
    </section>
</template>

<script>
import CarouselCard from './CarouselCard.vue';

export default {
    name: 'SectionPortfolio',
    components:{
        CarouselCard,
    },
    data: function(){
        return{
            activeElement: 2,
            worksList:[
                {
                    name: 'Purinky Products',
                    category: 'Digital Experience',
                    thumbnail: 'DRY-1-790x576.jpg'
                },
                {
                    name: 'Satisfy Poster',
                    category: 'Branding Strategy',
                    thumbnail: 'a247b00b-3621-470f-b4b8-b3ac46f25907-1-790x576.jpg'
                },
                {
                    name: 'Mock-Up',
                    category: 'something-else',
                    thumbnail: '84316050-0af0-49db-a53a-241d47ddad0e-2-790x576.jpg'
                },
                {
                    name: 'Something',
                    category: 'Digital Experience',
                    thumbnail: 'a247b00b-3621-470f-b4b8-b3ac46f25907-1-790x576.jpg'
                },
                {
                    name: 'Basket of flower on table',
                    category: 'Branding Strategy',
                    thumbnail: '8wa60okr-1-790x576.jpg'
                }
            ]
        }
    }
}
</script>

<style lang='scss' scoped>
@import '../assets/styles/style.scss';

section#portfolio{
    -ms-overflow-style: none;  /* IE and Edge */
    scrollbar-width: none;  /* Firefox */
    &::-webkit-scrollbar {
        display: none;
    }
    p:first-child{
        color: $secondaryLightColor;
    }

    div.ax-swapper{
        width: 40px;
        height: 40px;
        line-height: 40px;
        text-align: center;
        border-radius: 50%;
        border: 1px solid $secondaryLightColor;
        color: $secondaryLightColor;
        &:hover{
            cursor: pointer;
        }
    }
    div.ax-slider-container{
        height: 500px;
        background-color: aquamarine;
        //overflow: hidden;
        -ms-overflow-style: none;  /* IE and Edge */
        scrollbar-width: none;  /* Firefox */
        &::-webkit-scrollbar {
            display: none;
        }
    }
    div.slider-counter{
        height: 10px;
        width: 10px;
        border-radius: 50%;
        background-color: grey;
        &:hover{
            cursor: pointer;
        }

    }
    div.slider-counter.active{
        background-color: $secondaryLightColor;
    }
}
</style>