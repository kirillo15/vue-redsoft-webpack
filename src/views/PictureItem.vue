<template>
    <div class="picture__item">
        <div class="picture__img">
            <img :src="src" alt="">
        </div>
        <h3 class="picture__title">{{title}}</h3>
        <div class="picture__bottom" v-if="inStock">
            <div class="picture__price-wrap"
            >
                <span class="picture__price--sale">{{sale}}</span>
                <span class="picture__price">{{price}}</span>
            </div>
            <button class="btn"
            @click.once.prevent="addToCart"
            >
            {{btnName}}</button>
            
        </div>
        <div v-else class="picture__bottom">{{soldOut}}</div>
    </div>
</template>

<script>
import Button from './Button.vue'

export default {
    name: 'pictureItem',
    components: {
        Button
    },
    data: () => ({
        btnName: 'Купить',
        soldOut: 'Продана на аукционе'
    }),
    props: {
        title: String,
        price: String,
        sale: String,
        price: String,
        src: String,
        inStock: {
            type: Boolean,
            default: true,
        },
        srcCheck: String
    },

    methods: {
        addToCart(event) {
            const promise = fetch('https://reqres.in/api/products/3')
            .then(respons => {
                if(respons.ok) {
                    event.target.innerText = ''
                    event.target.classList.add('loader')
                }
                return respons
            })
            .then(respons => {
                let chechCart = document.createElement('img')
                chechCart.src = 'src/assets/Vector.png'
                chechCart.classList.add('absolut-img')
                localStorage.setItem(event.target.parentElement.previousElementSibling.innerText,event.target.parentElement.previousElementSibling.innerText)
                event.target.innerText = 'В корзине'
                event.target.style.background = '#5B3A32'
                event.target.appendChild(chechCart)
            })
        },
        
    },
}
</script>

<style lang="scss">
    
    .picture__item {
        flex: 0 0 20%;
        border: 1px solid #ccc;
        display: flex;
        flex-direction: column;
    }

    .picture__title {
        padding: 0 24px;
    }

    .btn {

        &__img {
            position: absolute;
            content: '';
            top: 0;
            left: 0;
        }
    }

    .loader {
            animation-duration: 1s;
            animation-name: slidein;
        }

        @keyframes slidein { 
            from {
                background: #ccc;
                width: 20%;
            }

            to {
                background:#C1B4B1;
                width: 70%;
            }
        }

    .absolut-img {
        position: absolute;
        top: 39%;
        left: 5px;
    }
</style>