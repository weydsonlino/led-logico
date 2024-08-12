<script lang="ts">
	import '../../style/reset.css';
	import '../../style/globals.css';
	import Header from '../../components/header.svelte';

	const alunos = [
		['Felipe Romero', 'https://github.com/feliperasilva'],
		['Jaqueline Albertina', '..'],
		['Marcos Vinicius', '..'],
		['Paulo Ricardo', 'https://github.com/PauloRC0'],
		['Weydson Lino', 'https://github.com/weydsonlino']
	];
</script>

<body class="pages">
	<Header />

	<main class="pages">
		<h2 class="tittle">About</h2>
		<div class="container-text about">
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
					<a href={github} target="_blank"><button class="buttons">github</button></a>
				</div>
			{/each}
		</section>
	</main>
</body>
