<script lang="ts">
	import '../../style/reset.css';
	import '../../style/globals.css';
	import Header from '../../components/header.svelte';

	const alunos = [
		['Felipe Romero', 'https://github.com/feliperasilva'],
		['Jaqueline Albertina', 'https://github.com/Jaquelinealbertina03'],
		['Marcos Vinicius', 'https://github.com/Dido3535'],
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
				This project was developed by students from the 1st period of the TSI course at IFPE Campus
				Igarassu, in the imperative programming discipline taught by Professor Allan Diego Silva.
				During the project, we developed the Lights Out game.
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
