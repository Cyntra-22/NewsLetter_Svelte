<script>
	import Email from "./Email.svelte";
</script>

<style>
	.main-container{
		display: flex;
		width: 40%;
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%,-50%);
		background-color: blueviolet;
		padding: 20px;
		border-radius: 15px;
		justify-content: space-between;
	}

	.right-container img{
		width: 270px;
	}
</style>

<div class="main-container">
	<div class="left-container">
		<div class="">
			<h1>Stay updated!</h1>
			<p>Join 60,000+ product managers receiving monthly updates on: </p>
			<ul>
				<li><img src="/" alt=""/>Product discovery and building what matters</li>
				<li><img src="/" alt=""/>Measuring to ensure updates are a success </li>
				<li><img src="/" alt=""/> And much more!</li>
			</ul>
		</div>

		<div class="">
			<Email/>
		</div>
	</div>
	<div class="right-container">
		<img src="/illustration-sign-up-desktop.svg" alt = "side-image"/>
	</div>

</div>