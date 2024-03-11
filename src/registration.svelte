   <!-- registration.svelte -->
   <script>
       let name = '';
       let email = '';

       async function registerUser() {
           const response = await fetch('https://api.example.com/register', {
               method: 'POST',
               headers: {
                   'Content-Type': 'application/json'
               },
               body: JSON.stringify({ name, email })
           });

           if (response.ok) {
               alert('Пользователь успешно зарегистрирован!');
           } else {
               alert('Ошибка при регистрации пользователя');
           }
       }
   </script>

   <h1>Регистрация нового пользователя</h1>

   <form on:submit|preventDefault="{registerUser}">
       <label for="name">Имя:</label>
       <input type="text" id="name" bind:value="{name}">
       
       <label for="email">Email:</label>
       <input type="email" id="email" bind:value="{email}">
       
       <button type="submit">Зарегистрировать</button>
   </form>
   