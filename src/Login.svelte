<script>
  import { user } from './user';

  let username;
  let password;

  function login() {
    user.auth(username, password, ({ err }) => err && alert(err));
  }

  function signup() {
    user.create(username, password, ({ err }) => {
      if (err) {
        alert(err);
      } else {
        login();
      }
    });
  }
</script>

<label for="username">Username</label>
<input name="username" bind:value={username} minlength="3" maxlength="16" />

<label for="password">Password</label>
<input name="password" bind:value={password} type="password" />

<button class="login" on:click={login}>Login</button>
<button class="login"  on:click={signup}>Sign Up</button>
  
<a href="https://www.flaticon.com/free-icons/hermit-crab" title="hermit crab icons">Hermit crab icons created by Freepik - Flaticon</a>