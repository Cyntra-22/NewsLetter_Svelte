<script>
    import { createEventDispatcher } from 'svelte';
    let email = '';
    let errorMessage = '';

    const dispatch = createEventDispatcher();

    function sendEmail() {
        
        validateEmail();
        if (!errorMessage){
            dispatch('submit', { email });
        }
  }

    function validateEmail(){
        if (email.trim() === ''){
            errorMessage = 'Valid email required';
        }
        else if(!isValidEmail(email)){
            errorMessage = 'Valid email required';
            
        }
        else{
            errorMessage = '';
        }
        if (errorMessage) {
            setTimeout(() => {
                errorMessage = '';
                email = '';
            }, 1500);
        }
    }

    function isValidEmail(email) {
        
        const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
        return emailRegex.test(email);
  }

    function updateInputStyle() {
        if (errorMessage) {
            return 'border-color: red; color: red; background-color:pink;';
        } else {
            return '';
        }
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

    .error_style{
        color: red;
        float: right;
        padding-right: 50px;
        opacity: 0.7;
    }

    @media (min-width: 300px) and (max-width: 768px ){
        button{
            width: 95%;
        }
        input{
            width: 95%;
        }
        .error_style{
            padding-right: 20px;
    }

    }

</style>

<div class="email-container">
    <div>
        <label for="email">Email Address
            {#if errorMessage}
                <span class="error_style">{errorMessage}</span>
            {/if}
        </label>
    {#if errorMessage}
        <input type="email" bind:value={email} placeholder="email@company.com" size="33" style="{updateInputStyle()}"/>
    {:else}
        <input type="email" bind:value={email} placeholder="email@company.com" size="33"/>
    {/if}

    </div>
  <button on:click = {sendEmail}>Subscribe to monthly newsletter</button>
</div>