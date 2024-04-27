<script>
	import Email from "./Email.svelte";
</script>

<style>

	:root{
		--font:'Work Sans', sans-serif;
		--bgColor: rgb(132, 68, 210);

	}

	:global(body){
		padding: 0;
		margin: 0;
		background-color: var(--bgColor);
		font-family: var(--font);   	 
	}

	.main-container{
		display: flex;
		width: 40%;
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%,-50%);
		background-color: white;
		padding: 20px;
		border-radius: 15px;
		justify-content: space-between;
	}

	.left-container{
		padding-right: 20px;
		padding-left: 10px;
	}

	.right-container img{
		width: 270px;
	}
	
	ul{
		padding: 0;
	}
	li{
		list-style-type: none;
		padding-top: 7px;
		padding-bottom: 7px;
	}

	.list-item{
		padding-left: 7px;
		font-size: 14px;
	}
</style>

<div class="main-container">
	<div class="left-container">
		<div class="">
			<h1>Stay updated!</h1>
			<p>Join 60,000+ product managers receiving monthly updates on: </p>
			<ul>
				<li><img src="/icon-list.svg" alt="" width="15px"/><span class="list-item">Product discovery and building what matters</span></li>
				<li><img src="/icon-list.svg" alt="" width="15px"/><span class="list-item">Measuring to ensure updates are a success </span></li>
				<li><img src="/icon-list.svg" alt="" width="15px"/><span class="list-item">And much more!</span></li>
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