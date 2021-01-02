<script>
	let name = 'world';
	let resume = {
		'info': {
			'name': 'INFO',
			'pos': 'SENIOR FRONT-END ENGINEER',
			'loc': 'Bengaluru, India',
			'email': 'srikantgudi@gmail.com',
			'phone': '+91-829-655-6336'
		},
		'profile': {
			name: 'PROFILE',
			contents: [
				'Senior Software Professional with over 20+ years of experience in various technologies',
				'Into Front-end development since 2014',
				'Proficient in Svelte, Angular, React, VueJs, StencilJS, NodeJS, MySQL',
				'Having working knowledge of Python-Django, MongoDB'
			]
		},
		'skills': {
			name: 'TECHNICAL SKILLS',
			groups: [
				{name: 'Frameworks', values: ['Svelte','Angular','React','Vue','Stencil','NodeJS']},
				{name: 'Web Skills', values: ['HTML5', 'CSS3', 'JavaScript', 'SVG']},
				{name: 'Databases', values: ['MongoDB', 'MySQL']},
				{name: 'Version Control', values: ['Git', 'BitBucket']},
				{name: 'Others', values: ['Visual Studio Code', 'IntelliJ', 'Atom', 'MACOS', 'Linux', 'Windows']}
			]
		}
	}
	let currentGroup = resume['skills'].groups[0].name
</script>

<style>
	main {
		box-shadow: 0 0 2px #999999;
		padding: 10px 2em;
	}
	summary.main {
		font-size: 20px;
		box-shadow: 0 2px 4px #999999;
		margin-bottom: 10px;
	}
	.section {
		font-size: 18px;
		box-shadow: 0 1px 2px #999999;
	}
	.subtitle {
		font-size: 16px;
	}
</style>
<main>
		<h1>SRIKANT GUDI <span class="subtitle">(Short Resume)</span></h1>
	<h3>
		{resume['info'].pos}
	</h3>
	<p>
		{resume['info'].loc} | {resume['info'].email} | {resume['info'].phone}	
	</p>

	<details>
		<summary class="main">{resume['info'].name}</summary>
		<ul>
			<p>
				{resume['info'].pos.toUpperCase()}
			</p>
			<p>
				Location: 
			</p>
			<p>
				eMail: <b>{resume['info'].email}</b>
			</p>
			<p>
				Phone: <b>{resume['info'].phone}</b>
			</p>

		</ul>
	</details>
	<details>
		<summary class="main">{resume['profile'].name}</summary>
		<ul>
			{#each resume['profile'].contents as content}
				<li>{content}</li>
			{/each}
		</ul>
	</details>
	<details>
		<summary class="main">{resume['skills'].name}</summary>
		<ul>
			{#each resume['skills'].groups as group}
				<details class="section">
					<summary on:click={() => currentGroup = group.name} class:active={currentGroup === group.name}>{group.name}</summary>
					<ul>
						{#each group.values as groupVal}
						<li>{groupVal}</li>
						{/each}
					</ul>
				</details>
			{/each}
		</ul>
	</details>
</main>
