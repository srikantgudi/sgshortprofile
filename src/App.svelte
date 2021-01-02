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
			title: 'PROFILE',
			contents: [
				'Senior Software Professional with over 20+ years of experience in various technologies',
				'Into Front-end development since 2014',
				'Proficient in Svelte, Angular, React, VueJs, StencilJS, NodeJS, MySQL',
				'Having working knowledge of Python-Django, MongoDB'
			]
		},
		'skills': {
			title: 'TECHNICAL SKILLS',
			groups: [
				{name: 'Frameworks', values: ['Svelte','Angular','React','Vue','Stencil','NodeJS']},
				{name: 'Web Skills', values: ['HTML5', 'CSS3', 'JavaScript', 'SVG']},
				{name: 'Databases', values: ['MongoDB', 'MySQL']},
				{name: 'Version Control', values: ['Git', 'BitBucket']},
				{name: 'Others', values: ['Visual Studio Code', 'IntelliJ', 'Atom', 'MACOS', 'Linux', 'Windows']}
			]
		},
		'exp': {
			title: 'WORK EXPERIENCE',
			expList: [
				{
					header: {
						dates: '16-Jun-2016 to present',
						jobTitle: 'Project Lead - System',
						org: 'Mphasis, Bengaluru',
					},
					content: [
		        'Currently working as Lead frontend developer with Schneider Electric',
						'Worked offshore in Bengaluru with a banking conglomerate on  projects in Angular and React',
						'Worked onsite in Glasgow, UK with a banking conglomerate on Angular based projects',
						'Developed UI for a POC for Digital Readiness Analysis Tool to create a survey questionnaire for various categories using Angular, Material Design, HTML5, CSS3, JavaScript, API integration',
						'Developed UI for client in Insurance domain using React, Material-UI, HTML5, CSS3, JavaScript, IndexedDB',
						'Worked offshore at client-side with Schneider Electric on Management Dashboard using Angular 1.x',
					]
				},
				{
					header: {
						dates: '15-Aug-2015 to 14-Jan-2016',
						jobTitle: 'Senior AngularJS Developer',
						org: 'Pandera Solutions India Pvt Ltd, Bengaluru',
					},
					content: [
						'Worked in Angular on various projects',
						'Created sub-components for re-use',
						'Interacted with client-side developers to understand the requirements',
						'Integrated APIs in the frontend code'
					]
				},
				{
					header: {
						dates: '20-Aug-2014 to 22-Jan-2015',
						jobTitle: 'Senior Software Developer',
						org: 'Basil Communications Pvt Ltd, Bengaluru',
					},
					content: [
						'Created HTML mockups for various applications',
						'Interacted with designers to understand the designs',
						'Used Photoshop to slice images'
					]
				},
				{
					header: {
						dates: 'Apr-2014 to Jun-2014',
						jobTitle: 'Senior AngularJS Developer',
						org: 'Satsyil, VA, USA (Remote work)',
					},
					content: [
						'Worked remotely as senior UI developer using AngularJS technology',
						'Modified admin-side modules and screen layouts and created new ones as required'
					]
				},
				{
					header: {
						dates: '23-Nov-2011 – 07-Mar-2014',
						jobTitle: 'Senior Software Developer (Consultant)',
						org: 'Tejas Systems / SUNSYSTEMS, Bengaluru :: Client: MModal Global Services Pvt Ltd',
					},
					content: [
						'Environment: PHP, MySQL, Jquery, Fancybox, Fusioncharts, HTML, CSS (Bootstrap), AngularJS',
						'modified client-side and admin-side scripts',
						'created animated presentation of iPad application using Jquery and Jquery-cycle',
						'created presentation of mobile application in Powerpoint',
						'created UI for password management using AngularJS'
					]
				},
				{
					header: {
						dates: '12-Feb-2010 –22-Sep-2011',
						jobTitle: 'Senior Software Engineer',
						org: 'TechJini Solutions, Bengaluru',
					},
					content: [
						'Environment: MySQL, PHP, HTML, CSS, Jquery, amChart',
						'Projects worked on:',
						'Coupons System (MySql, PHP, HTML, CSS, Jquery, HighCharts)',
						'eLearning System (PHP [Symfony], MySql, HTML, CSS, Jquery, amCharts): Developed Quiz module. Developed reports including one using amCharts',
						'Contest based application (PHP [Symfony], MySql, HTML, CSS, Jquery)'
					]
				},
				{
					header: {
						dates: '25-Jul-2007 – 14-Mar-2009',
						jobTitle: 'Senior Software Engineer',
						org: 'TLI Software, Bengaluru',
					},
					content: [
						'Environment:​ PHP, MySQL, HTML, CSS, Javascript, Jquery',
						'Worked​ as Full-time resource (3 months on-site and 3 months offsite), with Computer Methods I​nternational Corp, Toronto, Canada (www.cmic.ca), on JasperReports',
						'Developed web applications independently as per client requirements using PHP, MySql'
					]
				},
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
	.info {
		display: block;
	}
</style>
<main>
	<div class="info">
		<div>
			<h1>SRIKANT GUDI <span class="subtitle">(Short Resume)</span></h1>
			<h3>
				{resume['info'].pos}
			</h3>
		</div>
		<div>
			<p>{resume['info'].loc} | {resume['info'].email} | {resume['info'].phone}</p>
		</div>
	</div>

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
		<summary class="main">{resume['profile'].title}</summary>
		<ul>
			{#each resume['profile'].contents as content}
				<li>{content}</li>
			{/each}
		</ul>
	</details>
	<details>
		<summary class="main">{resume['skills'].title}</summary>
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
	<details>
		<summary class="main">{resume['exp'].title}</summary>
		<ul>
			{#each resume['exp'].expList as xp}
				<details>
					<summary>{xp.header.dates} | {xp.header.jobTitle} | {xp.header.org}</summary>
					<ul>
						{#each xp.content as xpitem}
						<li>{xpitem}</li>
						{/each}
					</ul>
				</details>
			{/each}
		</ul>
	</details>
</main>
