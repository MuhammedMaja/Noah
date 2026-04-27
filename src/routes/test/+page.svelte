<script>
	let boxSize = 800;

	let playerSize = 25;
	let top = 50;
	let left = 50;

	let targetSize = 40;

	let score = 0;

	
	let targetValue = 1;
	let targets = [];
	let interval 
	
	let valueUpgradeCost = 5;
	let targetAmountUpgradeCost = 20;

	// Spawn first target
	addTarget();

	function onKeyDown(e) {

		if(!e.repeat){
			if (interval)
				clearInterval(interval)
			interval= setInterval(()=>move(e.key.toLowerCase()),20)
		}

	}
	function on_key_up(){
		clearInterval(interval)
	}

	function move(key){
		switch (key) {

			// WASD
				case "w":
					if (top > 0) top -= 10;
					break;

				case "s":
					if (top < boxSize - playerSize) top += 10;
					break;

				case "a":
					if (left > 0) left -= 10;
					break;

				case "d":
					if (left < boxSize - playerSize) left += 10;
					break;
			}
			checkCollision()
	}

	function checkCollision() {
		targets.forEach((target, index) => {
			if (
				left < target.left + targetSize &&
				left + playerSize > target.left &&
				top < target.top + targetSize &&
				top + playerSize > target.top
			) {
				score += targetValue;

				// Move that specific target
				targets[index] = randomPosition();
			}
		});
	}

	function randomPosition() {
		return {
			left: Math.random() * (boxSize - targetSize),
			top: Math.random() * (boxSize - targetSize)
		};
	}

	function addTarget() {
		targets = [...targets, randomPosition()];
	}

	function upgradeValue() {
		if (score >= valueUpgradeCost) {
			score -= valueUpgradeCost;
			targetValue += 1;
			valueUpgradeCost = Math.floor(valueUpgradeCost * 1.6);
		}
	}

	function upgradeTargetAmount() {
		if (score >= targetAmountUpgradeCost) {
			score -= targetAmountUpgradeCost;
			addTarget();
			targetAmountUpgradeCost = Math.floor(targetAmountUpgradeCost * 1.8);
		}
	}
</script>

<style>
	.wrapper {
		width: 100vw;
		height: 100vh;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.container {
		display: flex;
		gap: 20px;
	}

	.upgrades {
		width: 220px;
		display: flex;
		flex-direction: column;
		gap: 10px;
	}

	.gamebox {
		width: 800px;
		height: 800px;
		border: 3px solid black;
		position: relative;
		background-color: #eee;
	}

	.player {
		width: 25px;
		height: 25px;
		background-color: green;
		position: absolute;
	}

	.target {
		width: 40px;
		height: 40px;
		background-color: brown;
		position: absolute;
	}

	button {
		padding: 10px;
		font-size: 14px;
		cursor: pointer;
	}
</style>

<div class="wrapper">
	<div class="container">

		<!-- LEFT SIDE UI -->
		<div class="upgrades">
			<h3>Upgrades</h3>
			<div>Score: {score}</div>
			<div>Target Value: {targetValue}</div>
			<div>Targets: {targets.length}</div>

			<button on:click={upgradeValue}>
				Increase Target Value (+1)
				<br>
				Cost: {valueUpgradeCost}
			</button>

			<button on:click={upgradeTargetAmount}>
				Add Another Target
				<br>
				Cost: {targetAmountUpgradeCost}
			</button>
		</div>

		<!-- GAME AREA -->
		<div class="gamebox">
			<div
				class="player"
				style="left: {left}px; top: {top}px;"
			></div>

			{#each targets as target}
				<div
					class="target"
					style="left: {target.left}px; top: {target.top}px;"
				></div>
			{/each}
		</div>

	</div>
</div>

<svelte:window on:keydown|preventDefault={onKeyDown} on:keyup={on_key_up}/>