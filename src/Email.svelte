<script>
    let email = '';
    let showMessage = false;
    let notificationMessage = '';
    import Notification from "./Notification.svelte";
    function sendEmail(){

    }

</script>

<style>

    .email-container{
        margin-top: 20px;      
    }

    input{
        border-radius: 5px;
        margin-top: 10px;
        font-size: 14px;
        margin-bottom: 15px;
        padding: 15px 15px;
        padding: 10px 10px;
    
    }
    ::placeholder {
       
        opacity: 0.8;
}

    label{
        font-weight: bold;
        font-size: 14px;
        color: var(--bgColor);
    }

    button{
        width: 290px;
        border-radius: 5px;
        background-color: var(--button-color);
        color: white;
        font-size: 12px;
        font-weight: bold;
        padding: 15px 15px; 
        cursor: pointer;   
    }

    button:hover{
        background-image: linear-gradient(to right, deeppink ,orangered);
    }


</style>

<div class="email-container">
    <div>
        <label for="email">Email Address</label>
        <input type="email" bind:value={email} placeholder="email@company.com" size="33"/>
    </div>
  <button on:click={sendEmail} >Subscribe to monthly newsletter</button>
  
  {#if showMessage}
    <Notification message={notificationMessage} />
  {/if}
</div>