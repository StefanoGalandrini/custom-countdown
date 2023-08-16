<script>
import AppCounter from "./components/AppCounter.vue";

export default {
	components: {
		AppCounter,
	},
};
</script>

<template>
	<div class="container">
		<img src="./assets/images/tree.png" alt="" />
		<img class="gift gift_1" src="./assets/images/gift_1.png" alt="" />
		<img class="gift gift_2" src="./assets/images/gift_2.png" alt="" />
		<img class="gift gift_3" src="./assets/images/gift_3.png" alt="" />
		<AppCounter />
	</div>
</template>

<style lang="scss">
@import "./style.scss";

img {
	max-width: 100%;
}

.container {
	width: 350px;
	height: 600px;
	margin-inline: auto;
	position: relative;

	.gift {
		position: absolute;
		width: 120px;
	}
	.gift_1 {
		bottom: 50px;
		right: 30px;
	}
	.gift_2 {
		bottom: 50px;
		left: 36px;
		width: 120px;
	}

	.gift_3 {
		bottom: 110px;
		left: 68px;
		width: 60px;
	}
}
</style>
