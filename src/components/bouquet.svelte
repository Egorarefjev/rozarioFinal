<script>
    import { bouquets } from  '../Store/stores.js';

    /** Очень долго провозился с ленивой загрузкой, хотел сделать с помощью svelte,
     *  поджимает время, поэтому сделал стандартным, для себя, методом.
     **/
</script>



{#each $bouquets as bouquet, i}
    {#if i == 0}
        <div class="bigBouquet">
            <div class="bigBouquet__photo">
                <a href="https://russia.rozarioflowers.ru/uploads/email/2020/05/22/{bouquet.image}" class="progressive replace">
                    <img src="https://sun9-57.userapi.com/c5089/u86674108/a_25f6f385.jpg?ava=1" class="preview" alt="photo of the bouquet" />
                </a>
            </div>
            <div class="bigBouquet__description">
                <h2 class="bigBouquet__name">{bouquet.title}</h2>
                <p class="bigBouquet__recipe">{bouquet.recipe}</p>
                <div class="bouquet__price">{bouquet.price} ₽</div>
                <button class="bigBouquet__button">Купить</button>
            </div>
        </div>
    {:else}
    <div class="bouquet">
        <div class="bouquet__photo">
            <a href="https://russia.rozarioflowers.ru/uploads/email/2020/05/22/{bouquet.image}" class="progressive replace bouquet__img">
                <img src="https://sun9-57.userapi.com/c5089/u86674108/a_25f6f385.jpg?ava=1" class="preview" alt="photo of the bouquet" />
            </a>
        </div>
        <h2 class="bouquet__name">{bouquet.title}</h2>
        <p class="bouquet__time">Доставим  в течение <span class="bouquet__time_minutes">120</span>  мин</p>
        <div class="bouquet__footer">
            <div class="bouquet__price">{bouquet.price}  ₽</div>
            <div class="bouquet__rating"><i class="fa fa-star" aria-hidden="true"></i>4,5</div>
        </div>
    </div>
    {/if}
{/each}


<style lang="scss">
    .progressive {
        width: 238px;
        height: 203px;
    }
    .bouquet {
        width: 254px;
        height: 376px;
        border: 1px solid #E9E9E9;
        box-sizing: border-box;
        box-shadow: 0px 4px 15px rgba(51, 0, 51, 0.15);
        margin-bottom: 25px;
        padding: 5px 5px 5px 5px;

        &__photo {
            margin-bottom: 25px;
            margin-top: 10px;
        }
        &__img {
            width: 246px;
            height: 224px;
        }
        &__name {
            font-style: normal;
            font-weight: 600;
            font-size: 16px;
            line-height: 22px;
            margin-left: 18px;
            color: #330033;
        }
        &__time {
            font-weight: 600;
            font-size: 14px;
            line-height: 19px;
            color: #C4C4C4;
            margin-left: 18px;
            &_minutes {
                font-size: 14px;
                line-height: 22px;
                color: #330033;
            }
        }
        &__footer {
            margin-top: 18px;
            display: flex;
            justify-content: space-between;
            margin-right: 18px;
            margin-left: 18px;
        }
        &__price {
            font-size: 18px;
            line-height: 20px;
            color: #330033;
            font-weight: 600;
        }
        &__rating {
            font-size: 18px;
            line-height: 20px;
            color: #330033;
        }

    }
    .bigBouquet {
        width: auto;
        max-width: 550px;
        min-height: 246px;
        border: 1px solid #E9E9E9;
        box-sizing: border-box;
        box-shadow: 0px 4px 15px rgba(51, 0, 51, 0.15);
        margin-bottom: 25px;
        display: flex;
        &__photo {
            margin-top: 5px;
            margin-left: 20px;
        }
        &__name {
            font-style: normal;
            font-weight: 600;
            font-size: 16px;
            line-height: 130%;
            color: #330033;
            margin-bottom: 8px;
            margin-top: 24px;
        }
        &__recipe {
            margin-bottom: 10px;
            font-style: normal;
            font-weight: normal;
            font-size: 14px;
            line-height: 130%;
            color: #666666;
        }
        &__description {
            margin-left: 5px;
        }

        &__button {
            width: 218px;
            height: 49px;
            background: #E9E9E9;
            border-radius: 4px;
            font-style: normal;
            font-weight: normal;
            font-size: 18px;
            line-height: 25px;
            color: #666666;
            margin-top: 20px;
        }
    }

    @media (max-width: 560px) {
        .bouquet {
            width: 284px;
        }
        .bigBouquet {
            width: 284px;
            height: 428px;
            flex-wrap: wrap;
            &__button {
                width: 248px;
                height: 42px;
            }
            &__description {
                margin-left: 18px;
            }
            &__name {
                margin-top: 12px;
            }
        }
    }
    .fa-star {
       color: #FFE033;
        font-size: 14px;
    }


</style>
