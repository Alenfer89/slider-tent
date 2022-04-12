<template>
    <div class="ax-carousel-element shadow position-absolute"
    :class='sliderQualifier()'>
        <div class="img-wrapper">
            <img :src="require(`../assets/images/${thumb}`)" :alt="name">
        </div>
        <div class="d-flex justify-content-between">
            <h6 class="ax-bold p-2"> {{ name }} </h6>
            <p class="m-0 p-2"> {{ category }} </p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'CarouselCard',
    props:{
        name: String,
        category: String,
        thumb: String,
        index: Number
    },
    data: function(){
        return{
            variatingClass: '',
        }
    },
    methods:{
        sliderQualifier(){
            const flag = this.index;
            switch(flag){
                case 0:
                    return this.variatingClass ='position-one';
                case 1:
                    return this.variatingClass ='position-two';
                case 2:
                    return this.variatingClass ='position-three';
                case 3:
                    return this.variatingClass ='position-four';
                case 4:
                    return this.variatingClass ='position-five';
            }
        }
    }
}
</script>

<style lang='scss' scoped>
@import '../assets/styles/style.scss';
div.ax-carousel-element{
    width: calc((100% / 3) - .5rem);
    border-radius: 2rem;
    &:hover{
        color: white;
        cursor: pointer;
        @include bgGradientLeftToRight ($secondaryColor , $secondaryLightColor);
    }
    div.img-wrapper{
        border-radius: 2rem;
        width: 100%;
        img{
            width: 100%;
            border-radius: 2rem
        }
    }
}
div.ax-carousel-element.position-one{
    //left: -452px;
    left: calc(( 432px + .5rem) * -1 );
    top: 50%;
    transform: translateY(-50%);
}
div.ax-carousel-element.position-two{
    left: 0;
    top: 50%;
    transform: translateY(-50%);
}
div.ax-carousel-element.position-three{
    left: calc( 432px + .5rem);
    top: 50%;
    transform: translateY(-50%);
}
div.ax-carousel-element.position-four{
    left: calc( (432px + .5rem) * 2 );
    top: 50%;
    transform: translateY(-50%);
}
div.ax-carousel-element.position-five{
    left: calc( (432px + .5rem) * 3 );;
    top: 50%;
    transform: translateY(-50%);
}
</style>