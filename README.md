<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Boliteros App - Análisis de Loterías</title>
    <style>
        :root {
            --primary: #2c3e50;
            --secondary: #e74c3c;
            --light: #ecf0f1;
            --dark: #2c3e50;
            --success: #27ae60;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f5f5f5;
            color: #333;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        header {
            background-color: var(--primary);
            color: white;
            padding: 15px 0;
            text-align: center;
            border-radius: 5px 5px 0 0;
            margin-bottom: 20px;
        }
        
        h1, h2, h3 {
            margin-bottom: 15px;
        }
        
        .card {
            background-color: white;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            padding: 20px;
            margin-bottom: 20px;
        }
        
        .card-header {
            border-bottom: 1px solid #eee;
            padding-bottom: 10px;
            margin-bottom: 15px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 20px;
        }
        
        .menu {
            display: flex;
            gap: 10px;
            margin-bottom: 20px;
            flex-wrap: wrap;
        }
        
        .menu-item {
            padding: 10px 15px;
            background-color: var(--primary);
            color: white;
            border-radius: 5px;
            cursor: pointer;
            text-decoration: none;
            transition: background-color 0.3s;
        }
        
        .menu-item:hover {
            background-color: var(--secondary);
        }
        
        .results-table {
            width: 100%;
            border-collapse: collapse;
        }
        
        .results-table th, .results-table td {
            padding: 10px;
            text-align: center;
            border: 1px solid #ddd;
        }
        
        .results-table th {
            background-color: var(--primary);
            color: white;
        }
        
        .results-table tr:nth-child(even) {
            background-color: #f2f2f2;
        }
        
        .btn {
            padding: 8px 15px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
            transition: all 0.3s;
        }
        
        .btn-primary {
            background-color: var(--primary);
            color: white;
        }
        
        .btn-danger {
            background-color: var(--secondary);
            color: white;
        }
        
        .btn-success {
            background-color: var(--success);
            color: white;
        }
        
        .form-group {
            margin-bottom: 15px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
        }
        
        .form-control {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
        }
        
        .checkbox-group {
            display: flex;
            gap: 10px;
            margin-bottom: 10px;
        }
        
        .badge {
            display: inline-block;
            padding: 3px 8px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: bold;
        }
        
        .badge-primary {
            background-color: var(--primary);
            color: white;
        }
        
        .badge-secondary {
            background-color: var(--secondary);
            color: white;
        }
        
        .tab-content {
            display: none;
        }
        
        .tab-content.active {
            display: block;
        }
        
        .alert {
            padding: 15px;
            border-radius: 5px;
            margin-bottom: 20px;
        }
        
        .alert-info {
            background-color: #d1ecf1;
            color: #0c5460;
            border: 1px solid #bee5eb;
        }
        
        .stat-card {
            background-color: white;
            border-radius: 5px;
            padding: 15px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            margin-bottom: 15px;
        }
        
        .stat-card h4 {
            margin-bottom: 10px;
            color: var(--primary);
        }
        
        footer {
            text-align: center;
            padding: 20px;
            margin-top: 30px;
            background-color: var(--primary);
            color: white;
            border-radius: 0 0 5px 5px;
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>osmaanyp</h1>
            <p>Análisis de loterías: Florida, Georgia y New York</p>
        </header>
        
        <div class="menu">
            <a href="#" class="menu-item" onclick="showTab('results')">Resultados</a>
            <a href="#" class="menu-item" onclick="showTab('predictions')">Pronósticos</a>
            <a href="#" class="menu-item" onclick="showTab('stats')">Estadísticas</a>
            <a href="#" class="menu-item" onclick="showTab('lab')">Laboratorio</a>
        </div>
        
        <!-- Results Tab -->
        <div id="results" class="tab-content active">
            <div class="card">
                <h2>Resultados Recientes</h2>
                
                <div class="alert alert-info">
                    <strong>NUEVO JUEGO DE DADOS EN EL CASINO CUBANO ENTRA A BOLIGAMES!</strong>
                </div>
                
                <div class="grid">
                    <div class="stat-card">
                        <h3>Florida (FL)</h3>
                        <ul>
                            <li>Pick 2: 34</li>
                            <li>Pick 3: 826</li>
                            <li>Pick 4: 8261</li>
                            <li>Pick 5: 82615</li>
                        </ul>
                    </div>
                    
                    <div class="stat-card">
                        <h3>Georgia (GA)</h3>
                        <ul>
                            <li>Cash 3: 534</li>
                            <li>Cash 4: 5341</li>
                            <li>Georgia Five: 53419</li>
                        </ul>
                    </div>
                    
                    <div class="stat-card">
                        <h3>New York (NY)</h3>
                        <ul>
                            <li>Numbers 3: 678</li>
                            <li>Win 4: 6786</li>
                        </ul>
                    </div>
                </div>
                
                <h3>Florida Pick 3 - Historial</h3>
                <table class="results-table">
                    <thead>
                        <tr>
                            <th>Fecha</th>
                            <th>Día</th>
                            <th>Turno</th>
                            <th>Números</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>2025-06-10</td>
                            <td>Martes</td>
                            <td>Midday</td>
                            <td>8 2 6</td>
                        </tr>
                        <tr>
                            <td>2025-06-09</td>
                            <td>Lunes</td>
                            <td>Evening</td>
                            <td>5 3 4</td>
                        </tr>
                        <tr>
                            <td>2025-06-09</td>
                            <td>Lunes</td>
                            <td>Midday</td>
                            <td>5 7 2</td>
                        </tr>
                        <tr>
                            <td>2025-06-08</td>
                            <td>Domingo</td>
                            <td>Evening</td>
                            <td>6 7 8</td>
                        </tr>
                        <tr>
                            <td>2025-06-08</td>
                            <td>Domingo</td>
                            <td>Midday</td>
                            <td>2 8 3</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
        
        <!-- Predictions Tab -->
        <div id="predictions" class="tab-content">
            <div class="card">
                <h2>Pronósticos</h2>
                
                <div class="grid">
                    <div class="stat-card">
                        <h3>TOP Pronósticos</h3>
                        <p>Pronósticos y estadísticas</p>
                        <ul>
                            <li>826 - 35% probabilidad</li>
                            <li>534 - 28% probabilidad</li>
                            <li>678 - 22% probabilidad</li>
                        </ul>
                    </div>
                    
                    <div class="stat-card">
                        <h3>Mi Laboratorio</h3>
                        <p>Prueba tus técnicas para el TOP</p>
                        <a href="#" class="btn btn-primary" onclick="showTab('lab')">Ir al Laboratorio</a>
                    </div>
                    
                    <div class="stat-card">
                        <h3>Tus Números de la Suerte</h3>
                        <p>Exclusivos para ti!</p>
                        <ul>
                            <li>2 - 8 - 6</li>
                            <li>5 - 3 - 4</li>
                            <li>6 - 7 - 8</li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Statistics Tab -->
        <div id="stats" class="tab-content">
            <div class="card">
                <h2>Estadísticas</h2>
                
                <div class="grid">
                    <div class="stat-card">
                        <h3>Pick3 Arrastrados</h3>
                        <p>Fijos, Decenas, Centenas, Terminales</p>
                        <ul>
                            <li>Fijos: 8 (35 veces)</li>
                            <li>Decenas: 2 (28 veces)</li>
                            <li>Centenas: 6 (22 veces)</li>
                            <li>Terminales: 6 (18 veces)</li>
                        </ul>
                    </div>
                    
                    <div class="stat-card">
                        <h3>Pick 3 Atrasados</h3>
                        <p>Fijos, Centenas, Decenas, Terminales</p>
                        <ul>
                            <li>Fijos: 0 (6230 días)</li>
                            <li>Centenas: 1 (4521 días)</li>
                            <li>Decenas: 3 (3856 días)</li>
                            <li>Terminales: 7 (2987 días)</li>
                        </ul>
                    </div>
                </div>
                
                <h3>Arrastrados/Rechazados</h3>
                <p>Sección para la lotería de la Florida. Vaya al símbolo 2 arriba para información.</p>
                
                <div class="form-group">
                    <label>Días Atrás: 6230 (4/5)</label>
                    <div class="checkbox-group">
                        <label><input type="checkbox"> para</label>
                        <label><input type="checkbox"> para</label>
                        <label><input type="checkbox"> General</label>
                        <label><input type="checkbox"> para</label>
                        <label><input type="checkbox"> para</label>
                    </div>
                    <button class="btn btn-primary">Buscar Arrastrados/Rechazados</button>
                </div>
                
                <div class="alert alert-info">
                    No hay datos que mostrar
                </div>
            </div>
        </div>
        
        <!-- Laboratory Tab -->
        <div id="lab" class="tab-content">
            <div class="card">
                <h2>Laboratorio</h2>
                <p>Prueba tus técnicas y pon tu mejor pronóstico en el TOP</p>
                
                <div class="form-group">
                    <button class="btn btn-success">Adicionar Técnica</button>
                </div>
                
                <div class="alert alert-info">
                    <strong>NUEVO JUEGO DE DADOS EN EL CASINO CUBANO ENTRA A BOLIGAMES!</strong>
                </div>
                
                <h3>Técnica: II PP</h3>
                <div class="grid">
                    <div class="stat-card">
                        <h4>Resultados</h4>
                        <ul>
                            <li>1</li>
                            <li>0.0%</li>
                            <li>0.0%</li>
                            <li>0.0%</li>
                        </ul>
                    </div>
                </div>
                
                <table class="results-table">
                    <thead>
                        <tr>
                            <th>Corrido1</th>
                            <th>Corrido2</th>
                            <th>Parle</th>
                            <th>Candado</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>Estadísticas</td>
                            <td><button class="btn btn-primary">Insertar Prono</button></td>
                            <td><button class="btn btn-primary">Historial Prono</button></td>
                            <td></td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
        
        <footer>
            <p>Boliteros App &copy; 2025 - Todos los derechos reservados</p>
        </footer>
    </div>
    
    <script>
        function showTab(tabId) {
            // Hide all tabs
            document.querySelectorAll('.tab-content').forEach(tab => {
                tab.classList.remove('active');
            });
            
            // Show selected tab
            document.getElementById(tabId).classList.add('active');
        }
        
        // Simple example of adding a technique
        document.querySelector('.btn-success').addEventListener('click', function() {
            alert('Funcionalidad para añadir nueva técnica será implementada aquí');
        });
    </script>
</body>
</html>
