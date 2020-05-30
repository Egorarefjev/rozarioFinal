<script>
	import Bouquet from './components/bouquet.svelte'
	import FlowerSet from './components/flowerSet.svelte'
	import { bouquets } from  './Store/stores.js';
	import { flowerSets } from  './Store/stores.js';

	function getData(url){
		return  fetch(url).then(response => {
			return response.json()
		})
	}
	getData('https://raw.githubusercontent.com/Egorarefjev/online-store-api/master/responses/rozarioProducts.JSON')
			.then((value) => {
				bouquets.update(n => value)
			})
			.catch(err => console.log(err))
	getData('https://raw.githubusercontent.com/Egorarefjev/online-store-api/master/responses/rozarioSets.JSON')
			.then((value) => {
				flowerSets.update(n => value)
			})
			.catch(err => console.log(err))

	/** По данному url возникает ошибка с CORS, решил через прокси, но это долго (решение в комментариях),
	 *  перезалил JSON на гит для удобства и быстротыо. **/

	/* function getData(proxyUrl , url){
		return  fetch(proxyUrl + url).then(response => {
			return response.json()
		})
	}


	 getData( 'https://cors-anywhere.herokuapp.com/', 'https://desolate-everglades-62768.herokuapp.com/productlist')
			.then((value) => {
				bouquets.update(n => value)
			})
			.catch(err => console.log(err))
	getData( 'https://cors-anywhere.herokuapp.com/', 'https://desolate-everglades-62768.herokuapp.com/collectionlist')
			.then((value) => {
				flowerSets.update(n => value)
			})
			.catch(err => console.log(err))
*/
</script>

<main>
	<div class="bouquets">
		<h2 class="categoryName">Букеты</h2>
		<div class="bouquets__item">
			<Bouquet/>
		</div>

	</div>
	<div class="flowerSets">
		<h2 class="categoryName">Коллекции</h2>
		<div class="flowerSets__item">
			<FlowerSet/>
		</div>

	</div>

</main>

<style lang="scss">

main {
	max-width: 600px;
	margin: 0 auto;

}

.categoryName {
	font-weight: bold;
	font-size: 24px;
	line-height: 115%;
	margin-left: 5%;
	margin-bottom: 18px;
	margin-top: 48px;
}
	.bouquets {

		&__item {
			display: flex;
			flex-wrap: wrap;
			justify-content: space-around;

		}
	}
.flowerSets {

	&__item {
		display: flex;
		flex-wrap: wrap;
		justify-content: space-around;

	}
}
@media (max-width: 550px) {
	main {
		min-width: 320px;
		width: 320px;
	}
	.categoryName {
		margin-top: 34px;
	}
}
</style>