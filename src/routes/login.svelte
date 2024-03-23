<script>
    import { push, location } from "svelte-spa-router";
    import { onDestroy } from "svelte";
  
    let usereamil = "";
    let password = "";
  
    async function handleLogin() {}

    let currentpath = "";
  
    const unsubscribe = location.subscribe(($location) => {
      currentpath = $location;
    });
    onDestroy(unsubscribe);
  </script>
  
  <div class="flex items-center h-screen">
    <div class="w-1/2 bg-base-300 p-10">
      <h1 class="mb-5">Login</h1>
      {#if currentpath == "/login"}
        <form on:submit|preventDefault={handleLogin}>
          <div class="flex flex-col space-y-4 items-center">
            <div>
              <input
                class="input input-bordered w-full max-w-xs"
                type="email"
                bind:value={usereamil}
                placeholder="Email"
              />
            </div>
            <div>
              <input
                class="input input-bordered w-full max-w-xs"
                type="password"
                bind:value={password}
                placeholder="Password"
              />
            </div>
            <div class="flex flex-row space-x-10">
              <button class="btn btn-wide btn-primary" type="submit">登录</button>
            </div>
          </div>
        </form>
        <div>New to us?<a href="/#/register">Create a account</a></div>
      {/if}
    </div>
  </div>
  