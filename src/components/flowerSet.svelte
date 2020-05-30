<script>
    import { flowerSets } from  '../Store/stores.js';
</script>

{#each $flowerSets as flowerSet}
    <div class="flowerSet">
        <div class="flowerSet__photo">
            <a href="https://russia.rozarioflowers.ru/uploads/email/2020/06/{flowerSet.image}" class="progressive replace">
                <img src="https://sun9-57.userapi.com/c5089/u86674108/a_25f6f385.jpg?ava=1" class="preview" alt="photo of the flower set">
            </a>
        </div>
        <div class="flowerSet__footer">
            <h2 class="flowerSet__name">{flowerSet.title}</h2>
            <p class="flowerSet__naw">{flowerSet.tags.join(' • ')}</p>
        </div>
    </div>
{/each}



<style lang="scss">
    .progressive {
        width: 254px;
        height: 152px;
        border-radius: 20px 20px 0px 0px;
    }
    .flowerSet {
        width: 254px;
        height: 223px;
        background: #F6F6F6;
        box-shadow: 0px 4px 15px rgba(51, 0, 51, 0.1);
        border-radius: 20px;
        padding-bottom: 18px;
        margin-bottom: 24px;
        &__name {
            font-weight: 600;
            font-size: 14px;
            line-height: 120%;
            color: #330033;
            margin-top: 18px;
            margin-bottom: 4px;
        }
        &__naw {
            font-style: normal;
            font-weight: normal;
            font-size: 12px;
            line-height: 16px;
            color: #999999;
        }
        &__footer {
            margin-left: 15px;
        }
    }


</style>