<script lang="ts">
	import '../../style/reset.css';
	import '../../style/globals.css';

	const alunos = [
		['Felipe Romero', '..'],
		['Jaqueline Albertina', '..'],
		['Marcos Vinicius', '..'],
		['Paulo Ricardo', '..'],
		['Weydson Lino', '..']
	];
</script>

<main class="pages">
	<header>
		<nav class="buttons-bar">
			<a href="/"><button class="buttons">back</button></a>
		</nav>
	</header>

	<body>
		<h2 class="tittle">About</h2>
		<div class="container-about">
			<p class="text">
				This is a simple puzzle game. The aim is to turn off all the lights. <br /><br /><br />
				Tap a button. The neighboring buttons will light up too, or turn off – depending on what state
				they were in before.
			</p>
		</div>
		<h2 class="tittle">Students</h2>

		<section class="container-students">
			{#each alunos as [aluno, github]}
				<div class="container-students-name">
					<h3 class="students-name">{aluno}</h3>
					<a href={github}><button class="buttons">github</button></a>
				</div>
			{/each}
		</section>
	</body>
</main>
