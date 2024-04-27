<script>
    let email = '';
    let showMessage = false;
    let notificationMessage = '';
    import Notification from "./Notification.svelte";
    function sendEmail(){

    }

</script>

<div>
    <div>
        <label for="email">Email Address</label>
        <input type="email" bind:value={email} placeholder="email@company.com"/>
    </div>
  <button on:click={sendEmail}>Subscribe to monthly newsletter</button>
  
  {#if showMessage}
    <Notification message={notificationMessage} />
  {/if}
</div>