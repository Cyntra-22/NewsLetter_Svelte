<script>
    export let email;
    import { createEventDispatcher } from 'svelte';

  const dispatch = createEventDispatcher();

  function dismissNotification() {
    dispatch('dismiss');
  }

   
</script>
    
<style>

     button{
        width: 290px;
        border-radius: 5px;
        background-color: var(--button-color);
        color: white;
        font-size: 12px;
        font-weight: bold;
        padding: 15px 15px; 
        cursor: pointer;  
        width: 300px;
        margin-top: 10px;
        margin-bottom: 10px; 
    }

    button:hover{
        background-image: linear-gradient(to right, deeppink ,orangered);
    }
    .success-container{
        background-color: white;
        border-radius: 20px;
        width: 300px;
        position: absolute;
        top: 50%;
        left: 50%;
        transform:translate(-50%,-50%);
        padding: 25px;
        
    }
    img{
        width: 35px;
        height: 35px;
    }

    @media (max-width: 768px){
        .success-container{
            width: 240px;
        }
        button{
            margin-top: 150px;
            width: 240px;
        }
        img {
            width: 50px;
            height: 50px;
        }
    }
</style>

<div class="success-container">
    <img src="/icon-list.svg" alt = "list-item-icon" />
    <h1>Thanks for subscribing!</h1>
    <p>A confirmation email has been sent to <strong>{email}</strong>. Please open it and click the button inside to confirm your subscription.</p>
    <button on:click = {dismissNotification}>Dismiss Message</button>
</div>