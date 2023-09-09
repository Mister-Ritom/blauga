<script lang="ts">
	import Dashboard from '$lib/images/Dashboard_Dark_Edited .png';


	let mouseX = -10,
		mouseY = -10;

	function handleMousemove(event: MouseEvent) {
		mouseX = event.clientX;
		mouseY = event.clientY;
	}

	function handleMouseLeave() {
		mouseX = -10;
		mouseY = -10;
	}
	
</script>

<svlte:head>
	<title>Blauga Home</title>
	<meta name="description" content="Balauga, Create,Share,Earn" />
	<meta name="keywords" content="Balauga,Blogs,Earn,Moeney" />
	<meta name="author" content="Ritom" />
</svlte:head>

<header>
	<h1 class="name">
		<h1 class="b">B</h1>
		<h1 class="l">L</h1>
		<h1 class="a">A</h1>
		U
		<h1 class="g">G</h1>
		A
	</h1>
	<h2>Read blogs to get more knowledge. Write blogs to give knowledge</h2>
</header>

<div on:mousemove={handleMousemove} on:mouseleave={handleMouseLeave} class="intro" role="banner">
	<div style="left: {mouseX}px; top: {mouseY}px;" class="cursor" />
	<div class="intro-grid">
		<div class="intro-card">
			<h2>Write Blogs</h2>
			<p>
				Compose well-researched and informative blogs with the aim of sharing your knowledge,
				expanding your audience, and potentially earning money, all while enhancing your online
				presence and popularity.
			</p>
		</div>
		<div class="intro-card">
			<h2>Read Blogs</h2>
			<p>
				Read blogs authored by brilliant individuals to acquire knowledge, and contribute to the
				community by sharing your insights and ideas.
			</p>
		</div>
		<div class="intro-card">
			<h2>Create presence</h2>
			<p>
				Establish a strong online presence with us and craft content that has the power to influence
				and inspire people.
			</p>
		</div>
		<div class="intro-card">
			<h2>Podcasts</h2>
			<p>
				Join our podcasts and supercharge your productivity. Gain knowledge hands-free while you
				work on your projects, turning every moment into an opportunity for learning and personal
				growth. Elevate your multitasking game with our informative and engaging content.
			</p>
		</div>
		<div class="intro-card">
			<h2>Elevate your skills</h2>
			<p>
				Join us on a transformative educational voyage where videos, images, and a treasure trove of
				knowledge await. Elevate your skills and understanding as you delve into intricate tasks and
				enrich your learning experience.
			</p>
		</div>
		<div class="intro-card">
			<h2>Daily knowledge</h2>
			<p>
				Embark on a journey with us as we invite you to dive into the richness of our daily blogs.
				Discover a wealth of insights, stay informed about the latest trends, and engage with
				thought-provoking content that keeps you at the forefront of knowledge and exploration.
			</p>
		</div>
	</div>
</div>

<div class="dashboard-wrapper">
	<div class="dash-bg" />
	<div class="dashboard">
		<a href="/dashboard">Dashboard for creators</a>
		<img class="dashboard-img" src={Dashboard} alt="Dashboard of Blauga" />
	</div>
</div>

<h2 class="final-footer">
	Discover, Create, and Connect with Blauga - Your Destination for Inspiring Blogs. Join our
	community of passionate bloggers, share your voice, and explore a world of ideas. Start your
	blogging journey today and let Blauga be your platform for inspiration and insight.
</h2>

<div class="space" />

<style>
	header {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		margin: 2rem;
		text-wrap: balance;
		font-weight: 700;
	}
	header h2 {
		text-align: center;
		margin: 0;
		font-weight: 400;
	}
	.name {
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
	}
	.name .b {
		background: linear-gradient(45deg, var(--primary), rgb(131, 174, 230));
		background-clip: text;
		-webkit-background-clip: text;
		color: transparent;
	}
	.name .l {
		background: linear-gradient(10deg, var(--primary), var(--accent));
		background-clip: text;
		-webkit-background-clip: text;
		color: transparent;
	}
	.name .a {
		background: linear-gradient(45deg, var(--accent), rgb(11, 182, 212));
		background-clip: text;
		-webkit-background-clip: text;
		color: transparent;
	}
	.name .g {
		background: linear-gradient(45deg, rgb(214, 10, 214), rgb(44, 123, 226));
		background-clip: text;
		-webkit-background-clip: text;
		color: transparent;
	}
	h1 {
		font-family: 'Phudu', sans-serif;
		font-size: 72px;
		letter-spacing: 0.5rem;
		margin: 0.5rem;
	}
	h2 {
		margin: 0;
	}

	.intro {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		margin: 2rem 0;
		cursor: none;
		background: rgba(106, 49, 160, 0.2);
		width: 80dvw;
		height: 35.5rem;
		margin-left: auto;
		margin-right: auto;
		border-radius: 16px;
	}

	.intro-grid {
		padding: 1rem;
		display: grid;
		grid-template-columns: 1fr 1fr 1fr;
		grid-gap: 2rem;
		margin: 2rem 0;
		/* From https://css.glass */
		/* Primary Color in rgb */
		background: transparent;
		border-radius: 16px;
		box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
		backdrop-filter: blur(10.5px);
		-webkit-backdrop-filter: blur(10.5px);
		/* Primary color in rgb */
		border: 1px solid rgba(106, 49, 160, 0.54);
	}

	.intro-card {
		padding: 0.5rem;
		/* From https://css.glass */
		background: rgba(15, 5, 24, 0.22);
		border-radius: 16px;
		box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
		backdrop-filter: blur(2.5px);
		-webkit-backdrop-filter: blur(2.5px);
	}

	.intro-card h2 {
		text-align: center;
		user-select: none;
	}

	.intro-card p {
		text-align: justify;
		user-select: none;
	}

	.intro-card:hover {
		border-color: white;
		border-width: 1px;
		border-style: solid;
	}

	.dashboard {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		margin-left: auto;
		margin-right: auto;
		background: rgba(15, 5, 24, 0.22);
		border-radius: 16px;
		box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
		backdrop-filter: blur(90.5px);
		-webkit-backdrop-filter: blur(90.5px);
	}

	.dashboard a {
		font-size: 2rem;
		font-weight: 700;
		margin: 2rem 0;
		text-decoration: none;
		color: var(--primary);
		letter-spacing: 1.2px;
		word-spacing: 1.5px;
	}

	.dashboard-img {
		width: 60%;
		height: 40%;
		border-radius: 16px;
	}

	.dash-bg {
		border-radius: 48px;
		display: inline-block;
		position: absolute;
		width: 75%;
		height: 75%;
		background: linear-gradient(45deg, var(--secondary), var(--accent));
		border-radius: 50%;
		margin-top: 25px;
		z-index: -1;
	}

	.final-footer {
		text-align: center;
		margin-left: 5rem;
		margin-right: 5rem;
		margin-top: 2rem;
		font-weight: 700;
		font-size: large;
		font-family: 'Phudu', sans-serif;
		word-spacing: 1.5px;
		letter-spacing: 2px;
	}

	.cursor {
		position: fixed;
		width: 20px;
		height: 20px;
		background: white;
		border-radius: 50%;
		pointer-events: none; /* To prevent cursor from interfering with elements */
		transform: translate(-50%, -50%); /* Center the cursor on the mouse pointer */
		transition: transform 0.15s ease; /* Add a smooth transition effect */
	}

	.space {
		height: 5rem;
	}

	@media (max-width: 1000px) {
		p {
			font-size: small;
		}
	}

	@media (max-width: 720px) {
		.intro {
			width: 90vw;
			height: 100%;
			border-radius: 8px;
			padding-left: 8px;
			padding-right: 8px;
		}
		.intro-grid {
			grid-template-columns: 1fr 1fr;
		}
		.intro-card {
			height: 11.9rem;
			overflow: hidden;
			text-overflow: ellipsis;
		}
	}
</style>
