<script lang="ts">
    interface ActionData {
      invalid?: boolean;
      user?: boolean;
      message?: string;
    }
    import fondo from '$lib/imagenes/general.jpg'
    export let form: ActionData = {};
</script>
  
<div class="grid" style={`background-image:url(${fondo})`}>
  <br>
  <br>
  <br>
  <main>
    <center> 
    <form action="?/register" method="POST">
      <h1 class="title">INGRESA TUS DATOS</h1>
      <br>
      <br>
      <br>
      <br>
      <div class="brutalist-container">
        <label class="brutalist-label" for="username">Ingresa tu Usuario</label>
        <input class="brutalist-input smooth-type" id="username" placeholder="Usuario" name="username" type="text" required />
      </div>
      <br>
      <br>
      <br>
      <br>
      <div class="brutalist-container">
        <label class="brutalist-label" for="email">Ingresa tu Correo Electrónico</label>
        <input class="brutalist-input smooth-type" id="email" placeholder="Correo elctrónico" name="email" type="email" required />
      </div>
      <br>
      <br>
      <br>
      <br>
      <div class="brutalist-container">
        <label class="brutalist-label" for="password">Crea una Contraseña</label>
        <input class="brutalist-input smooth-type" id="password" placeholder="Mínimo 10 Carácteres" name="password" type="password" required />
      </div>
      <br>
      <br>
      <br>
      <br>
      {#if form?.invalid}
        <p class="error">Por favor, completa todos los campos.</p>
      {/if}
  
      {#if form?.user}
        <p class="error">El correo electrónico ya está en uso.</p>
      {/if}
  
      {#if form?.message}
        <p class="error">Error en el servidor: {form.message}</p>
      {/if}
  
      <button class="b" type="submit">Registrarse</button>
      <br>
      <br>
      <br>
      <p class="m">Ya Tienes Cuenta??</p>
      <a class="b" href="/iniciar">Iniciar Sesión</a>
    </form>
    </center>
  </main>
  <br>
  <br>
  <br>
</div>
<style>
.m {
 color: rgb(134, 134, 134);
}
.title {
  color: #264143;
  font-weight: 900;
  font-size: 1.5em;
  margin-top: 20px;
}
  /* From Uiverse.io by 0xnihilism */ 
.brutalist-container {
  position: relative;
  width: 250px;
  font-family: monospace;
}

.brutalist-input {
  width: 100%;
  padding: 15px;
  font-size: 18px;
  font-weight: bold;
  color: #000;
  background-color: #fff;
  border: 4px solid #000;
  position: relative;
  overflow: hidden;
  border-radius: 0;
  outline: none;
  transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
  box-shadow: 5px 5px 0 #000, 10px 10px 0 #4a90e2;
}

@keyframes glitch {
  0% {
    transform: translate(0);
  }
  20% {
    transform: translate(-2px, 2px);
  }
  40% {
    transform: translate(-2px, -2px);
  }
  60% {
    transform: translate(2px, 2px);
  }
  80% {
    transform: translate(2px, -2px);
  }
  100% {
    transform: translate(0);
  }
}

.brutalist-input:focus {
  animation: focus-pulse 4s cubic-bezier(0.25, 0.8, 0.25, 1) infinite,
    glitch 0.3s cubic-bezier(0.25, 0.8, 0.25, 1) infinite;
}

.brutalist-input:focus::after {
  content: "";
  position: absolute;
  top: -2px;
  left: -2px;
  right: -2px;
  bottom: -2px;
  background: white;
  z-index: -1;
}

.brutalist-input:focus::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: black;
  z-index: -2;
  clip-path: inset(0 100% 0 0);
  animation: glitch-slice 4s steps(2, end) infinite;
}

@keyframes glitch-slice {
  0% {
    clip-path: inset(0 100% 0 0);
  }
  10% {
    clip-path: inset(0 5% 0 0);
  }
  20% {
    clip-path: inset(0 80% 0 0);
  }
  30% {
    clip-path: inset(0 10% 0 0);
  }
  40% {
    clip-path: inset(0 50% 0 0);
  }
  50% {
    clip-path: inset(0 30% 0 0);
  }
  60% {
    clip-path: inset(0 70% 0 0);
  }
  70% {
    clip-path: inset(0 15% 0 0);
  }
  80% {
    clip-path: inset(0 90% 0 0);
  }
  90% {
    clip-path: inset(0 5% 0 0);
  }
  100% {
    clip-path: inset(0 100% 0 0);
  }
}

main {
		background-color: #ffffff;
		border: 1px solid #ccc;
		border-radius: 15px;
		padding: 20px;
		width: 35%;
		margin: 2rem auto;
		text-align: left;
    font-weight: bold;
	}

.brutalist-label {
  position: absolute;
  left: -3px;
  top: -35px;
  font-size: 14px;
  font-weight: bold;
  color: #fff;
  background-color: #000;
  padding: 5px 10px;
  transform: rotate(-1deg);
  z-index: 1;
  transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
}

.smooth-type {
  position: relative;
  overflow: hidden;
}

.smooth-type::before {
  content: "";
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  background: linear-gradient(90deg, #fff 0%, rgba(255, 255, 255, 0) 100%);
  z-index: 1;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.smooth-type:focus::before {
  opacity: 1;
  animation: type-gradient 2s linear infinite;
}

@keyframes type-gradient {
  0% {
    background-position: 300px 0;
  }
  100% {
    background-position: 0 0;
  }
}

.brutalist-input::placeholder {
  color: #888;
  transition: color 0.3s ease;
}

.brutalist-input:focus::placeholder {
  color: transparent;
}

.brutalist-input:focus {
  animation: focus-pulse 4s cubic-bezier(0.25, 0.8, 0.25, 1) infinite;
}

@keyframes focus-pulse {
  0%,
  100% {
    border-color: #000;
  }
  50% {
    border-color: #4a90e2;
  }
}

.b {
  color: #000;
  background: #4a90e2;
  font-family: inherit;
  padding: 0.6em 1.3em;
  font-weight: 900;
  font-size: 18px;
  border: 3px solid black;
  border-radius: 0.4em;
  box-shadow: 0.1em 0.1em;
  cursor: pointer;
}

.b:hover {
  transform: translate(-0.05em, -0.05em);
  box-shadow: 0.15em 0.15em;
}

.b:active {
  transform: translate(0.05em, 0.05em);
  box-shadow: 0.05em 0.05em;
}

</style>
  