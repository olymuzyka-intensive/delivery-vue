<template>
            <section class="products">
                <div class="container">
                    <div class="products-wrapper" id="eats-container">
                        <div class="products-card"
                        v-for="eat in eatArray"
                        :key="eat.id"
                        >
                            <div class="products-card__image">
                                <img :src="getUrl(eat.image)" alt="eat1">
                            </div>
                            <div class="products-card__description">
                                <div class="products-card__description-row">
                                    <h5 class="products-card__description--name">
                                        {{eat.name}}
                                    </h5>                                    
                                </div>
                                <div class="products-card__description-row">
                                    <p class="products-card__description--text">
                                        {{eat.info}}
                                    </p>                                    
                                </div>
                                <div class="products-card__description-row">
                                      <div class="products-card__description-controls">
                                        <button class="btn btn-primary">
                                            В корзину
                                            <img src="../assets/img/icons/cart-white.svg" alt="cart"> 
                                        </button>
                                        <span class="products-card__description-controls--price">{{eat.price}} ₽</span>
                                      </div>                                    
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </section>            
                
</template>

<script setup>
import { eatArray } from '../constants/eats'
const getUrl = (name) => {
    return new URL(`../assets/img/goods/${name}`, import.meta.url)
}
</script>
