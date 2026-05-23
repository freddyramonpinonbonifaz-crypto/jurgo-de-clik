<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Clicker System Pro 💰 | El Camino a los 100 Billones</title>
    <style>
        /* --- ESTILOS GENERALES Y TEMA --- */
        :root {
            --bg-main: #11111b;
            --bg-card: #1e1e2e;
            --bg-input: #313244;
            --text-main: #cdd6f4;
            --text-muted: #a6adc8;
            --accent-blue: #89b4fa;
            --accent-green: #a6e3a1;
            --accent-red: #f38ba8;
            --accent-orange: #fab387;
            --accent-yellow: #f9e2af;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
        }

        body {
            background-color: var(--bg-main);
            color: var(--text-main);
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 20px;
        }

        /* --- CONTENEDORES PRINCIPALES --- */
        .box {
            background: var(--bg-card);
            width: 100%;
            max-width: 440px;
            padding: 30px;
            border-radius: 16px;
            box-shadow: 0 12px 32px rgba(0, 0, 0, 0.5);
            border: 1px solid rgba(255, 255, 255, 0.05);
            text-align: center;
        }

        .hidden {
            display: none !important;
        }

        h2 {
            font-size: 22px;
            letter-spacing: 1px;
            margin-bottom: 20px;
            color: var(--accent-green);
        }

        /* --- FORMULARIOS E INPUTS --- */
        .form-group {
            margin-bottom: 15px;
            text-align: left;
        }

        .form-group label {
            display: block;
            font-size: 13px;
            color: var(--text-muted);
            margin-bottom: 5px;
            padding-left: 5px;
        }

        input {
            width: 100%;
            padding: 12px 16px;
            border-radius: 8px;
            border: 2px solid transparent;
            background: var(--bg-input);
            color: white;
            font-size: 15px;
            transition: all 0.2s;
        }

        input:focus {
            outline: none;
            border-color: var(--accent-blue);
        }

        /* --- BOTONES ESTILIZADOS --- */
        button {
            width: 100%;
            padding: 14px;
            margin-top: 10px;
            border: none;
            border-radius: 8px;
            font-size: 15px;
            font-weight: bold;
            cursor: pointer;
            transition: transform 0.1s, filter 0.2s;
        }

        button:hover {
            filter: brightness(1.1);
        }

        button:active {
            transform: scale(0.98);
        }

        .btn-blue { background: var(--accent-blue); color: #11111b; }
        .btn-green { background: var(--accent-green); color: #11111b; }
        .btn-red { background: var(--accent-red); color: #11111b; }
        
        .btn-secondary { 
            background: transparent; 
            color: var(--text-muted); 
            border: 1px solid var(--bg-input);
            margin-top: 5px;
        }

        .btn-orange { 
            background: var(--accent-orange); 
            color: #11111b; 
            width: auto; 
            padding: 8px 14px; 
            font-size: 13px;
            border-radius: 6px;
        }

        /* --- SECCIÓN DEL JUEGO ACTIVO --- */
        .header-juego {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }

        #lbl-dinero {
            color: var(--accent-yellow);
            font-size: 38px;
            font-weight: 800;
            margin: 15px 0 5px 0;
            text-shadow: 0 4px 10px rgba(249, 226, 175, 0.2);
        }

        .meta-text {
            font-size: 12px;
            color: var(--text-muted);
            margin-bottom: 25px;
        }

        /* El Botón Gigante */
        .btn-click {
            background: radial-gradient(circle, var(--accent-blue) 0%, #74c7ec 100%);
            color: #11111b;
            font-size: 24px;
            font-weight: 900;
            letter-spacing: 1px;
            padding: 0;
            border-radius: 50%;
            width: 160px;
            height: 160px;
            margin: 0 auto 30px auto;
            display: flex;
            justify-content: center;
            align-items: center;
            box-shadow: 0 8px 24px rgba(137, 180, 250, 0.4);
            border: 4px solid var(--bg-main);
        }

        .btn-click:active {
            transform: scale(0.92);
            box-shadow: 0 4px 12px rgba(137, 180, 250, 0.2);
        }

        /* La Tienda */
        .tienda-titulo {
            text-align: left;
            font-size: 16px;
            color: var(--accent-blue);
            margin-bottom: 12px;
            border-bottom: 1px solid var(--bg-input);
            padding-bottom: 5px;
        }

        .tienda-item {
            background: rgba(255, 255, 255, 0.02);
            border: 1px solid var(--bg-input);
            padding: 12px 16px;
            margin: 10px 0;
            border-radius: 10px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            text-align: left;
        }

        .tienda-info h4 { font-size: 14px; color: white; }
        .tienda-info small { font-size: 12px; color: var(--text-muted); }

        .tienda-item button {
            width: auto;
            padding: 8px 14px;
            margin: 0;
            font-size: 13px;
        }

        .tienda-item button:disabled {
            background: #585b70;
            color: #a6adc8;
            cursor: not-allowed;
            transform: none;
            filter: none;
        }

        /* --- INTERFAZ ADMINISTRADOR --- */
        select {
            width: 100%;
            background: var(--bg-input);
            color: white;
            padding: 12px;
            border-radius: 8px;
            border: none;
            margin-bottom: 15px;
            outline: none;
        }
    </style>
</head>
<body>

    <!-- PANTALLA 1: INICIAR SESIÓN -->
    <div id="pantalla-login" class="box">
        <h2>INICIAR SESIÓN</h2>
        <div class="form-group">
            <label for="log-user">Nombre de Usuario</label>
            <input type="text" id="log-user" placeholder="Ej. JuanClicker">
        </div>
        <div class="form-group">
            <label for="log-pass">Contraseña</label>
            <input type="password" id="log-pass" placeholder="••••••••">
        </div>
        <button class="btn-blue" onclick="loginUsuario()">Ingresar / Cargar Partida</button>
        <button class="btn-secondary" onclick="cambiarPantalla('registro')">Crear Nueva Cuenta</button>
        
        <hr style="border: none; border-top: 1px solid var(--bg-input); margin: 25px 0 20px 0;">
        <button class="btn-red" onclick="loginAdmin()">Acceso Administrador 🛠️</button>
    </div>

    <!-- PANTALLA 2: REGISTRO -->
    <div id="pantalla-registro" class="box hidden">
        <h2 style="color: var(--accent-yellow);">REGISTRARSE</h2>
        <div class="form-group">
            <label for="reg-user">Elige tu Usuario</label>
            <input type="text" id="reg-user" placeholder="Tu apodo en el juego">
        </div>
        <div class="form-group">
            <label for="reg-pass">Crea tu Contraseña</label>
            <input type="password" id="reg-pass" placeholder="Mínimo 4 caracteres">
        </div>
        <button class="btn-green" onclick="registrarUsuario()">Confirmar Registro</button>
        <button class="btn-secondary" onclick="cambiarPantalla('login')">Volver Atrás</button>
    </div>

    <!-- PANTALLA 3: EN EL JUEGO -->
    <div id="pantalla-juego" class="box hidden" style="max-width: 460px;">
        <div class="header-juego">
            <span id="lbl-jugador" style="color: var(--accent-blue); font-size: 14px; font-weight: bold;"></span>
            <button class="btn-orange" onclick="volverAlMenu()">🏠 Salir y Guardar</button>
        </div>

        <h1 id="lbl-dinero">$0</h1>
        <div class="meta-text">
            <span id="lbl-info">Generando: $0/seg</span><br>
            <span id="lbl-meta-val" style="color: var(--text-muted);">Meta global: 100 Billones</span>
        </div>

        <button class="btn-click" id="btn-picar" onclick="hacerClic()">¡PICAR!</button>

        <h3 class="tienda-titulo">Tienda de Mejoras</h3>
        
        <div class="tienda-item">
            <div class="tienda-info">
                <h4>Fuerza de Clic</h4>
                <small id="info-c">+1 por cada toque</small>
            </div>
            <button class="btn-green" id="btn-c" onclick="comprarC()">Costo: $10</button>
        </div>

        <div class="tienda-item">
            <div class="tienda-info">
                <h4>Puesto de Limonadas</h4>
                <small id="info-l">+$5/segundo automáticamente</small>
            </div>
            <button class="btn-green" id="btn-l" onclick="comprarL()">Costo: $100</button>
        </div>
    </div>

    <!-- PANTALLA 4: CONSOLA DE ADMINISTRADOR -->
    <div id="pantalla-admin" class="box hidden">
        <h2 style="color: var(--accent-red);">SISTEMA CENTRAL ADMIN 🛠️</h2>
        <p style="font-size: 14px; color: var(--text-muted); margin-bottom: 15px;">Selecciona la cuenta de un usuario para inyectarle fondos desde el servidor:</p>
        
        <select id="lista-usuarios" size="5"></select>
        
        <button class="btn-blue" onclick="hackUsuario()">Inyectar +$10 Millones</button>
        <button class="btn-secondary" onclick="cambiarPantalla('login')">Cerrar Sesión de Servidor</button>
    </div>

    <!-- --- LÓGICA CORE EN JAVASCRIPT --- -->
    <script>
        // Sistema de persistencia integrado usando localStorage del navegador
        let db = JSON.parse(localStorage.getItem('clicker_web_db')) || {
            usuarios: {"player1": "1234"},
            progreso: {"player1": {dinero: 0, d_clic: 1, d_seg: 0, c_clic: 10, c_lim: 100, meta: 100000000000000}}
        };
        
        let usuarioActual = "";
        let juego = {};

        function guardarDB() { 
            localStorage.setItem('clicker_web_db', JSON.stringify(db)); 
        }

        function cambiarPantalla(pantalla) {
            document.getElementById('pantalla-login').classList.add('hidden');
            document.getElementById('pantalla-registro').classList.add('hidden');
            document.getElementById('pantalla-juego').classList.add('hidden');
            document.getElementById('pantalla-admin').classList.add('hidden');
            
            document.getElementById('pantalla-' + pantalla).classList.remove('hidden');
            if(pantalla === 'admin') cargarListaAdmin();
        }

        function registrarUsuario() {
            let u = document.getElementById('reg-user').value.trim();
            let p = document.getElementById('reg-pass').value;
            
            if(!u || !p) return alert("Por favor, llena todos los espacios.");
            if(db.usuarios[u]) return alert("Este nombre de usuario ya está ocupado.");
            
            db.usuarios[u] = p;
            db.progreso[u] = {dinero: 0, d_clic: 1, d_seg: 0, c_clic: 10, c_lim: 100, meta: 100000000000000};
            guardarDB();
            
            alert("¡Cuenta creada con éxito! Ahora puedes iniciar sesión.");
            document.getElementById('reg-user').value = "";
            document.getElementById('reg-pass').value = "";
            cambiarPantalla('login');
        }

        function loginUsuario() {
            let u = document.getElementById('log-user').value.trim();
            let p = document.getElementById('log-pass').value;
            
            if(db.usuarios[u] && db.usuarios[u] === p) {
                usuarioActual = u;
                juego = db.progreso[u];
                document.getElementById('lbl-jugador').innerText = "👤 " + u;
                document.getElementById('btn-picar').disabled = false;
                actualizarUI();
                cambiarPantalla('juego');
            } else { 
                alert("Usuario o contraseña incorrectos."); 
            }
        }

        function loginAdmin() {
            let clave = document.getElementById('log-pass').value;
            if(clave === "admin123") {
                document.getElementById('log-pass').value = "";
                cambiarPantalla('admin');
            } else { 
                alert("Clave de Administrador incorrecta. Colócala en el campo de contraseña."); 
            }
        }

        function volverAlMenu() {
            if(usuarioActual) db.progreso[usuarioActual] = juego;
            guardarDB();
            alert("¡Progreso de partida guardado de forma segura en tu navegador!");
            cambiarPantalla('login');
        }

        // Formateador dinámico para evitar colapsar la UI con números de 14 dígitos
        function formatear(n) {
            if (n >= 1000000000000) return (n / 1000000000000).toFixed(2) + " Billones";
            if (n >= 1000000000) return (n / 1000000000).toFixed(2) + " Mil Millones";
            if (n >= 1000000) return (n / 1000000).toFixed(2) + " Millones";
            if (n >= 1000) return (n / 1000).toFixed(2) + " K";
            return "$" + n;
        }

        function hacerClic() {
            juego.dinero += juego.d_clic;
            verificarVictoria();
            actualizarUI();
        }

        function comprarC() {
            if(juego.dinero >= juego.c_clic) {
                juego.dinero -= juego.c_clic;
                juego.d_clic += 1;
                juego.c_clic = Math.round(juego.c_clic * 1.15);
                actualizarUI();
            }
        }

        function comprarL() {
            if(juego.dinero >= juego.c_lim) {
                juego.dinero -= juego.c_lim;
                juego.d_seg += 5;
                juego.c_lim = Math.round(juego.c_lim * 1.15);
                actualizarUI();
            }
        }

        function verificarVictoria() {
            if(juego.dinero >= juego.meta) {
                document.getElementById('lbl-dinero').innerText = "¡GANASTE! 🎉";
                document.getElementById('btn-picar').disabled = true;
            }
        }

        function actualizarUI() {
            if(juego.dinero < juego.meta) document.getElementById('lbl-dinero').innerText = formatear(juego.dinero);
            document.getElementById('lbl-info').innerHTML = `Generando automáticamente: <strong>${formatear(juego.d_seg)}/seg</strong>`;
            document.getElementById('lbl-meta-val').innerText = `Meta global: ${formatear(juego.meta)}`;
            
            document.getElementById('info-c').innerText = `Suma +1 por clic (Tienes +${juego.d_clic})`;
            document.getElementById('btn-c').innerText = `Comprar: ${formatear(juego.c_clic)}`;
            document.getElementById('btn-c').disabled = juego.dinero < juego.c_clic;
            
            document.getElementById('info-l').innerText = `Suma +$5/seg (Generando +${juego.d_seg}/s)`;
            document.getElementById('btn-l').innerText = `Comprar: ${formatear(juego.c_lim)}`;
            document.getElementById('btn-l').disabled = juego.dinero < juego.c_lim;
        }

        function cargarListaAdmin() {
            let s = document.getElementById('lista-usuarios');
            s.innerHTML = "";
            for(let u in db.usuarios) {
                let o = document.createElement('option');
                o.value = u; 
                o.innerText = "👤 " + u; 
                s.appendChild(o);
            }
        }

        function hackUsuario() {
            let u = document.getElementById('lista-usuarios').value;
            if(!u) return alert("Por favor, selecciona un usuario válido de la lista.");
            db.progreso[u].dinero += 10000000;
            guardarDB();
            if(u === usuarioActual) { juego.dinero = db.progreso[u].dinero; actualizarUI(); }
            alert("Se han inyectado $10,000,000 exitosamente a la cuenta de " + u);
        }

        // Bucle temporal para simular la producción pasiva por segundo
        setInterval(() => {
            if(usuarioActual && juego.dinero < juego.meta) {
                juego.dinero += juego.d_seg;
                verificarVictoria();
                actualizarUI();
            }
        }, 1000);
    </script>
</body>
</html>
