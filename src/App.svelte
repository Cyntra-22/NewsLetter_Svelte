<script>
  import { onMount } from "svelte";
	import Email from "./Email.svelte";
	import Notification from "./Notification.svelte";

	let submittedEmail = '';
	let showMessage = false;

	let right_image = "/illustration-sign-up-desktop.svg";

	onMount(() =>{
		if(window.innerWidth < 1080) {
			right_image = "/illustration-sign-up-mobile.svg";
		}
	});


	function handleEmailSubmission(event){
		submittedEmail = event.detail.email;
		showMessage = true;
	}

	function dismissMessage(){
		showMessage = false;
	}



</script>

<style>

	:root{
		--font:'Work Sans', sans-serif;
		--bgColor: hsl(234, 29%, 20%);
		--button-color: hsl(235, 18%, 26%);

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
		border-radius: 20px;
		justify-content: space-between;
		
	}

	.left-container{
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
		padding: 4px 4px;
	}

	.list-item{
		padding-left: 7px;
		font-size: 14px;
	}

	h1{
		color: var(--bgColor);
		font-size: 40px;
	}

	@media (max-width: 750px){
		.main-container{
			flex-direction: column-reverse;
			width: 80%;
			margin: 20px;
		}
		.right-container img{
		width: 100%;
		
	}
	

	}
</style>


{#if showMessage}
  <Notification email={submittedEmail} on:dismiss={dismissMessage} />
{:else}
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

			<div>
				{#if !showMessage}
					<Email on:submit ={handleEmailSubmission}/>
				{:else}
					<Notification email={submittedEmail} on:dismiss={dismissMessage}/>
				{/if}
			</div>
		</div>
		<div class="right-container" >
			<img src={right_image} alt = "side-image"/>
		</div>

	</div>

{/if}