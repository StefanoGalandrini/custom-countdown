<script>
export default {
	data() {
		return {
			endGame: 0,
			now: 0,
			timeDifference: 0,
			remainingDays: 0,
			remainingHours: 0,
			remainingMinutes: 0,
			remainingSeconds: 0,
		};
	},

	methods: {
		startTimer() {
			this.now = new Date().getTime();
			this.timeDifference = this.endGame - this.now;
			const msInOneSecond = 1000;
			const msInOneMinute = msInOneSecond * 60;
			const msInOneHour = msInOneMinute * 60;
			const msInOneDay = msInOneHour * 24;
			const differenceInDays = this.timeDifference / msInOneDay;
			const remainderDifferenceInHours =
				(this.timeDifference % msInOneDay) / msInOneHour;
			const remainderDifferenceInMinutes =
				(this.timeDifference % msInOneHour) / msInOneMinute;
			const remainderDifferenceInSeconds =
				(this.timeDifference % msInOneMinute) / msInOneSecond;
			this.remainingDays = Math.floor(differenceInDays);
			this.remainingHours = Math.floor(remainderDifferenceInHours);
			this.remainingMinutes = Math.floor(remainderDifferenceInMinutes);
			this.remainingSeconds = Math.floor(remainderDifferenceInSeconds);
		},
	},

	mounted() {
		this.endGame = new Date("2023-08-21T09:30:00").getTime();
		setInterval(() => {
			this.startTimer();
		}, 1000);
	},
};
</script>

<template>
	<div class="counter-wrapper">
		<h1>Final Exercise Countdown</h1>
		<div class="timer">
			<div class="days">
				<p class="count">{{ remainingDays }}</p>
				<p class="text">Giorni</p>
			</div>
			<div class="hours">
				<p class="count">{{ remainingHours }}</p>
				<p class="text">Ore</p>
			</div>
			<div class="minutes">
				<p class="count">{{ remainingMinutes }}</p>
				<p class="text">Minuti</p>
			</div>
			<div class="seconds">
				<p class="count">{{ remainingSeconds }}</p>
				<p class="text">Secondi</p>
			</div>
		</div>
	</div>
</template>

<style lang="scss" scoped>
@import "../style.scss";

h1 {
	font-size: 1.5rem;
	color: $color-pink;
	margin-bottom: 1rem;
}

.counter-wrapper {
	width: 100%;
	margin-inline: auto;
	background-color: $color-darkblue;
	border-radius: 10px;
	padding: 1rem;
	position: absolute;
	top: 5.5rem;
	left: 0;

	.timer {
		display: flex;
		justify-content: center;
		align-items: center;
		gap: 1.5rem;

		.count {
			font-size: 2.75rem;
			font-weight: bold;
		}

		.text {
			font-size: 1.3rem;
		}
	}

	.seconds {
		color: $color-yellow;
	}
}
</style>
