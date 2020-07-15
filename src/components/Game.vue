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

<style>
 .container {
display: flex;
flex-flow: 1;
align-items: center;
justify-content: center;
flex-direction: column;
border: 1px solid black;
}
 .status-bar {
background-color: #91C7B1;
display: flex;
justify-content: center;
align-items: center;
font-size: 3rem;
height: 5rem;
margin-top: 1rem;
margin-bottom: 1rem;
text-align: center;
width: 100%;
 }
 .game {
background-color: rgb(169, 177, 169);
display: flex;
flex-grow: 1;
justify-content: center;
margin-bottom: 1rem;
 }
 table {
border-collapse: collapse;
 }
 .grid-cell {
margin: 0;
padding: 0;
height: 10px;
width: 10px;
background-color: #f4f4f4;
border: 1px solid white;
 }
 .food {
background-color: #e3d081;
 }
 .snake {
background-color: #54494B;
 }
</style>