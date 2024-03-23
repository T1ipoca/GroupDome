<script>
    import { push, location } from "svelte-spa-router";
    import { onDestroy } from "svelte";
  
    function handleLogin() {
      push("/login");
    }
    let currentpath = "";
  
    const unsubscribe = location.subscribe(($location) => {
      currentpath = $location;
    });
    onDestroy(unsubscribe);
  </script>
  
  <div class="h-lvh w-screen flex flex-col space-y-20 items-center justify-center">
    <div class='text-neutral '>
      <h1 class="font-bold font-sans">
         游学系统
      </h1>
    </div>
    <div>
      {#if currentpath == "/"}
        <button class="btn btn-wide" on:click={handleLogin}> 登录 </button>
      {/if}
    </div>
  </div>
