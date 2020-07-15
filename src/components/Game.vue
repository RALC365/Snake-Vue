<template>
	<div class="container">
		<div class="status-bar">SNAKE - Score {{ score }}</div>
		<div class="game">
			<table v-if="!dead">
				<tr v-for="(row, index) in grid" :key="index">
					<td v-for="(cell, index) in row" :key="index" class="grid-cell"
						:class="{ snake: cell.snake > 0, food: cell.food }">
					</td>
				</tr>
			</table>
			<div v-else>
				<button @click="reset()">Play Again?</button>
			</div>
		</div>
	</div>
</template>

