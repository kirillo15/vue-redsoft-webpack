<template>
    <div class="picture"
    >
        <div class="container">
            <h2 class="heading">{{heading}}</h2>
            <div class="picture-wrap" 
            >
            <PictureItem
            v-for="(item,index) of picture"
            :key="index"
            :title="item.title"
            :src="item.src"
            :sale="item.sale"
            :price="item.price"
            :inStock="item.inStock"
            :class="!item.inStock ? isActive : ''"
            v-on="getItemPictureLocalStorage"
            ></PictureItem>
            </div>
        </div>
    </div>
</template>

<script>
import PictureItem from './PictureItem.vue'

export default {
    name: 'picture',
    components: {
        PictureItem
    },
    data: () => ({
        heading: 'Картины эпохи Возрождения',
        props: ['btn'],
        picture: [
            {
                title: '«Рождение Венеры» Сандро Боттичелли',
                src: 'src/assets/pic1.jpg',
                price: '1 000 000 $',
                sale: '2 000 000 $',
                inStock: true,
                disabled: false,
            },
            {
                title: '«Тайная вечеря»  Леонардо да Винчи',
                src: 'src/assets/pic2.jpg',
                price: '3 000 000 $',
                inStock: true,
                disabled: false,
            },
            {
                title: '«Сотворение Адама» Микеланджело',
                src: 'src/assets/pic3.jpg',
                price: '5 000 000 $',
                sale: '6 000 000 $',
                inStock: true,
                disabled: false,
            },
            {
                title: '«Урок анатомии»  Рембрандт',
                src: 'src/assets/pic4.jpg',
                price: '5 000 000 $',
                sale: '6 000 000 $',
                inStock: false,
                disabled: true,
            },
        ],
        isActive: {
            isActive: 0.5
        }  
    }),
    computed: {
        getItemPictureLocalStorage() {

            let arr = []
            
            for(let i = 0; i < localStorage.length; i++) {
                if(!arr.includes(localStorage.key(i))) {
                    arr.push(localStorage.key(i))
                }
            }

         for(let i = 0; i < this.picture.length; i++) {
         if(arr.some(item => this.picture[i].title)) {
                
            }
         }
            
        }
    },
    mounted() {
        
        const itemPicture = document.querySelectorAll('.picture__item')
        let arr = []
            
            for(let i = 0; i < localStorage.length; i++) {
                if(!arr.includes(localStorage.key(i))) {
                    arr.push(localStorage.key(i))
                }
            }

            for(let i = 0; i < itemPicture.length; i++) {
            if(arr.includes(itemPicture[i].children[1].innerText) && !itemPicture[i].classList.contains('isActive')) {
                let chechCart = document.createElement('img')
                chechCart.src = 'src/assets/Vector.png'
                chechCart.classList.add('absolut-img')
                itemPicture[i].children[2].children[1].disabled = true
                itemPicture[i].children[2].children[1].innerText = 'В Корзине'
                itemPicture[i].children[2].children[1].style.background = '#5B3A32'
                itemPicture[i].children[2].children[1].appendChild(chechCart)
            }
         }
        arr = []
    }
}
</script>

<style lang="scss">
    .picture {

        min-height: 742px;

        &-wrap {
            display: flex;
            justify-content: space-between;
            margin: 41px 0 0;
        }

        & .isActive {
            opacity: 0.5;
        }

        &__bottom {
            display: flex;
            align-items: center;
            justify-content: space-around;
            padding: 0 0 24px 7px;
            margin: 7px 0px 0 0;
        }

        &__price-wrap {
            display: flex;
            flex-direction: column;
        }


        &__price--sale {
            color: #A0A0A0;
            text-decoration-line: line-through;
            font-weight: 300;
            font-size: 14px;
        }

        &__price {
            font-style: normal;
            font-weight: bold;
            font-size: 16px;
        }

        & .btn {
            padding: 14px 29px;
            margin: 0 12px 0 0;
        }

    }

    
</style>