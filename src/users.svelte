<!-- users.svelte -->
   <script>
       let users = [];

       async function fetchUsers() {
           const response = await fetch('https://api.example.com/users');
           const data = await response.json();
           users = data;
       }

       fetchUsers();
   </script>

   <h1>Список пользователей</h1>

   <ul>
       {#each users as user}
           <li>{user.name}</li>
       {/each}
   </ul>