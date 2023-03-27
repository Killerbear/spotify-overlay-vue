<script setup lang="ts">
let item
let error
let requestData
let duration: string
let durationInMs: number
let elapse: string
let elapseInMs: number
</script>

<template>
	<main>
		<img src="{item.album.images[0].url}" alt="cover" />
		<div class="info">
			<div class="title">{item?.name}</div>
			<div class="artist">{item?.artists[0]?.name}</div>
			<div class="progress">
				<div class="elapse">{elapse}</div>
				<div class="progress-bar">
					<div class="elapse-bar" />
				</div>
				<div class="duration">{duration}</div>
			</div>
		</div>

		<!--		{#if !error && !item}-->
		<!--		<div class="info">-->
		<!--			<div class="artist">Es läuft keine Musik</div>-->
		<!--		</div>-->
		<!--		{/if}-->

		<!--		{#if error}-->
		<!--		<div class="info">-->
		<!--			<div class="artist">Es ist ein Fehler aufgetreten</div>-->
		<!--		</div>-->
		<!--		{/if}-->
	</main>
</template>

<style lang="scss">
:root {
	--progress-bar-transform: 0%;
}

main {
	display: flex;
}

img {
	width: 112px;
	margin: 32px;
}

.info {
	display: flex;
	flex: auto;
	flex-direction: column;
	justify-content: center;
	margin-right: 32px;
}

.title {
	font-size: 28px;
	font-weight: 500;
	line-height: 32px;
	color: #fff;
}

.artist {
	font-size: 22px;
	font-weight: 400;
	line-height: 32px;
	color: #b3b3b3;
}

.progress {
	display: flex;
	gap: 8px;
	align-items: center;
	justify-content: space-between;
	margin-top: 20px;
}

.elapse,
.duration {
	color: #a7a7a7;
	font-size: 0.6875rem;
}

.progress-bar {
	flex: auto;
	background: hsla(0, 0%, 100%, 0.3);
	height: 4px;
	border-radius: 2px;
	position: relative;
	overflow: hidden;
}

.elapse-bar {
	background: #ececec;
	height: 4px;
	border-radius: 2px;
	width: 100%;
	transform: translateX(calc(-100% + var(--progress-bar-transform)));
}
</style>
