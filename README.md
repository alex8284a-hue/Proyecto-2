# Proyecto-2<!DOCTYPE html>
<html lang="es" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>La Brecha Económica en México</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts: Montserrat (Headers) & Inter (Body) -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Montserrat:wght@400;600;700;800;900&display=swap" rel="stylesheet">
    <!-- Chart.js for data visualization -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        display: ['Montserrat', 'sans-serif'],
                    },
                    colors: {
                        brand: {
                            dark: '#0f172a',
                            navy: '#1e293b',
                            emerald: '#059669',
                            teal: '#0d9488',
                            gold: '#d97706',
                            coral: '#e11d48',
                            light: '#f8fafc'
                        }
                    }
                }
            }
        }
    </script>
    <style>
        .custom-gradient {
            background: linear-gradient(135deg, #0f172a 0%, #1e1b4b 50%, #311042 100%);
        }
        .emerald-gradient {
            background: linear-gradient(90deg, #059669 0%, #0d9488 100%);
        }
        .card-blur {
            background: rgba(30, 41, 59, 0.7);
            backdrop-filter: blur(12px);
        }
    </style>
</head>
<body class="bg-slate-900 text-slate-100 font-sans leading-relaxed selection:bg-emerald-500 selection:text-white">

    <!-- Navigation Header -->
    <header class="sticky top-0 z-50 bg-slate-950/80 backdrop-blur-md border-b border-slate-800 transition-all duration-300">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-20">
                <!-- Logo -->
                <div class="flex-shrink-0 flex items-center gap-3">
                    <span class="p-2 bg-emerald-600 rounded-lg text-white font-bold text-xl shadow-lg shadow-emerald-900/40">🇲🇽</span>
                    <span class="font-display font-extrabold text-lg sm:text-xl bg-gradient-to-r from-emerald-400 via-teal-300 to-indigo-400 bg-clip-text text-transparent">BrechaEconómica</span>
                </div>
                
                <!-- Desktop Nav -->
                <nav class="hidden md:flex space-x-1 lg:space-x-3 text-sm font-medium">
                    <a href="#inicio" class="text-slate-300 hover:text-emerald-400 px-3 py-2 rounded-md transition duration-200">Inicio</a>
                    <a href="#problematica" class="text-slate-300 hover:text-emerald-400 px-3 py-2 rounded-md transition duration-200">Problemática</a>
                    <a href="#simulador" class="text-slate-300 hover:text-emerald-400 px-3 py-2 rounded-md transition duration-200">Simulador</a>
                    <a href="#causas" class="text-slate-300 hover:text-emerald-400 px-3 py-2 rounded-md transition duration-200">Causas</a>
                    <a href="#consecuencias" class="text-slate-300 hover:text-emerald-400 px-3 py-2 rounded-md transition duration-200">Consecuencias</a>
                    <a href="#soluciones" class="text-slate-300 hover:text-emerald-400 px-3 py-2 rounded-md transition duration-200">Soluciones</a>
                    <a href="#galeria" class="text-slate-300 hover:text-emerald-400 px-3 py-2 rounded-md transition duration-200">Galería</a>
                    <a href="#reflexion" class="text-slate-300 hover:text-emerald-400 px-3 py-2 rounded-md transition duration-200">Reflexión</a>
                </nav>

                <!-- CTA Button -->
                <div class="hidden lg:block">
                    <a href="#simulador" class="px-5 py-2.5 bg-gradient-to-r from-emerald-500 to-teal-600 text-white font-semibold rounded-lg hover:from-emerald-600 hover:to-teal-700 shadow-md shadow-emerald-900/30 transition duration-300 transform hover:-translate-y-0.5">
                        Calcular Mi Decil
                    </a>
                </div>

                <!-- Mobile Menu Button -->
                <div class="md:hidden flex items-center">
                    <button id="mobile-menu-btn" class="inline-flex items-center justify-center p-2 rounded-md text-slate-400 hover:text-white hover:bg-slate-800 focus:outline-none transition duration-150">
                        <svg class="h-6 w-6" stroke="currentColor" fill="none" viewBox="0 0 24 24">
                            <path id="menu-icon" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
                        </svg>
                    </button>
                </div>
            </div>
        </div>

        <!-- Mobile Menu Panel -->
        <div id="mobile-menu" class="hidden md:hidden bg-slate-950 border-b border-slate-800 transition-all duration-300">
            <div class="px-2 pt-2 pb-4 space-y-1 sm:px-3 text-base font-semibold">
                <a href="#inicio" class="block text-slate-300 hover:text-emerald-400 px-3 py-2 rounded-md">Inicio</a>
                <a href="#problematica" class="block text-slate-300 hover:text-emerald-400 px-3 py-2 rounded-md">Problemática</a>
                <a href="#simulador" class="block text-slate-300 hover:text-emerald-400 px-3 py-2 rounded-md">Simulador</a>
                <a href="#causas" class="block text-slate-300 hover:text-emerald-400 px-3 py-2 rounded-md">Causas</a>
                <a href="#consecuencias" class="block text-slate-300 hover:text-emerald-400 px-3 py-2 rounded-md">Consecuencias</a>
                <a href="#soluciones" class="block text-slate-300 hover:text-emerald-400 px-3 py-2 rounded-md">Soluciones</a>
                <a href="#galeria" class="block text-slate-300 hover:text-emerald-400 px-3 py-2 rounded-md">Galería</a>
                <a href="#reflexion" class="block text-slate-300 hover:text-emerald-400 px-3 py-2 rounded-md">Reflexión</a>
            </div>
        </div>
    </header>

    <!-- Hero Section (Inicio) -->
    <section id="inicio" class="relative overflow-hidden custom-gradient min-h-[90vh] flex items-center pt-8 pb-16">
        <!-- Abstract Decorative Shapes -->
        <div class="absolute -top-40 -right-40 w-96 h-96 bg-emerald-500/10 rounded-full blur-3xl"></div>
        <div class="absolute bottom-10 left-10 w-80 h-80 bg-indigo-500/10 rounded-full blur-3xl"></div>

        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10 w-full">
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 items-center">
                <!-- Text Area -->
                <div class="lg:col-span-7 space-y-6 text-center lg:text-left">
                    <span class="inline-flex items-center gap-1.5 py-1 px-3 rounded-full text-xs font-semibold bg-emerald-500/10 text-emerald-400 border border-emerald-500/20">
                        <span class="w-2 h-2 rounded-full bg-emerald-500 animate-pulse"></span>
                        Análisis Socioeconómico de México
                    </span>
                    <h1 class="text-4xl sm:text-5xl lg:text-6xl font-display font-extrabold tracking-tight text-white leading-tight">
                        La grieta de la desigualdad: <br class="hidden sm:inline">
                        <span class="bg-gradient-to-r from-emerald-400 via-teal-400 to-indigo-400 bg-clip-text text-transparent">Brecha Económica</span> en México
                    </h1>
                    <p class="text-lg text-slate-300 max-w-2xl mx-auto lg:mx-0">
                        Un territorio de contrastes abismales. Mientras un puñado de corporativos lidera listas de riqueza mundial, millones de familias enfrentan desafíos estructurales para salir de la pobreza extrema. Explora los datos, comprende las causas y sumérgete en las soluciones urgentes.
                    </p>
                    <div class="flex flex-col sm:flex-row gap-4 justify-center lg:justify-start">
                        <a href="#problematica" class="px-8 py-4 bg-gradient-to-r from-emerald-500 to-teal-600 text-white font-bold rounded-xl hover:from-emerald-600 hover:to-teal-700 shadow-lg shadow-emerald-950/50 hover:shadow-emerald-900/40 hover:-translate-y-0.5 transition duration-300 text-center">
                            Explorar la Realidad
                        </a>
                        <a href="#simulador" class="px-8 py-4 bg-slate-800/80 hover:bg-slate-800 text-slate-200 border border-slate-700 font-bold rounded-xl hover:border-slate-500 transition duration-300 text-center">
                            Simulador de Ingresos
                        </a>
                    </div>

                    <!-- Quick Stats Badges -->
                    <div class="grid grid-cols-3 gap-4 pt-6 max-w-md mx-auto lg:mx-0 border-t border-slate-800">
                        <div>
                            <p class="text-2xl sm:text-3xl font-display font-extrabold text-emerald-400">0.45</p>
                            <p class="text-xs text-slate-400 uppercase tracking-wider">Coeficiente Gini</p>
                        </div>
                        <div>
                            <p class="text-2xl sm:text-3xl font-display font-extrabold text-teal-400">10%</p>
                            <p class="text-xs text-slate-400 uppercase tracking-wider">Concentra el 59% de riqueza</p>
                        </div>
                        <div>
                            <p class="text-2xl sm:text-3xl font-display font-extrabold text-indigo-400">46.8M</p>
                            <p class="text-xs text-slate-400 uppercase tracking-wider">Mexicanos en Pobreza</p>
                        </div>
                    </div>
                </div>

                <!-- Graphic/Visual Area -->
                <div class="lg:col-span-5 relative">
                    <div class="relative mx-auto max-w-[420px]">
                        <!-- Visual decorative glow behind main image container -->
                        <div class="absolute -inset-1.5 bg-gradient-to-r from-emerald-500 to-indigo-500 rounded-2xl blur opacity-30 animate-pulse"></div>
                        
                        <div class="relative bg-slate-800/90 rounded-2xl p-6 border border-slate-700 shadow-2xl space-y-4">
                            <!-- Visual comparison box representing inequality -->
                            <div class="flex justify-between items-center pb-4 border-b border-slate-700">
                                <span class="font-display font-bold text-slate-200">Distribución de Ingresos</span>
                                <span class="text-xs text-slate-400">Datos CONEVAL / INEGI</span>
                            </div>
                            
                            <div class="space-y-4">
                                <div class="bg-slate-900/60 p-4 rounded-xl border border-slate-800/50">
                                    <div class="flex justify-between items-center mb-1">
                                        <span class="text-xs font-bold text-emerald-400 uppercase tracking-wider">Decil X (Los más ricos)</span>
                                        <span class="text-sm font-extrabold text-slate-100">59.0% del total</span>
                                    </div>
                                    <div class="w-full bg-slate-800 rounded-full h-3 overflow-hidden">
                                        <div class="bg-gradient-to-r from-emerald-400 to-teal-500 h-full rounded-full" style="width: 59%"></div>
                                    </div>
                                    <p class="text-[10px] text-slate-400 mt-1">Ingreso promedio mensual por hogar superior a $66,000 MXN.</p>
                                </div>

                                <div class="bg-slate-900/60 p-4 rounded-xl border border-slate-800/50">
                                    <div class="flex justify-between items-center mb-1">
                                        <span class="text-xs font-bold text-indigo-400 uppercase tracking-wider">Decil I (Los más vulnerables)</span>
                                        <span class="text-sm font-extrabold text-slate-100">1.8% del total</span>
                                    </div>
                                    <div class="w-full bg-slate-800 rounded-full h-3 overflow-hidden">
                                        <div class="bg-gradient-to-r from-indigo-500 to-purple-500 h-full rounded-full" style="width: 1.8%"></div>
                                    </div>
                                    <p class="text-[10px] text-slate-400 mt-1">Ingreso promedio mensual por hogar menor a $4,500 MXN.</p>
                                </div>
                            </div>

                            <p class="text-xs text-slate-400 italic text-center pt-2">
                                "En México, el ingreso de una familia rica equivale a multiplicar por más de 30 veces el de una familia de escasos recursos."
                            </p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Problemática Section -->
    <section id="problematica" class="py-24 bg-slate-950 relative">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16 space-y-4">
                <span class="text-xs font-bold text-emerald-400 uppercase tracking-widest px-3 py-1 bg-emerald-500/10 rounded-full border border-emerald-500/20">La Cruda Realidad</span>
                <h2 class="text-3xl sm:text-4xl font-display font-black text-white">¿Cuál es la problemática de la Brecha Económica?</h2>
                <p class="text-slate-400 text-lg">
                    No se trata solo de dinero; es la falta sistemática de oportunidades básicas. La brecha económica fragmenta el desarrollo del país, consolidando dos realidades paralelas que conviven a pocos kilómetros de distancia.
                </p>
            </div>

            <!-- Dashboard Breakdown -->
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-stretch">
                <!-- Left Details cards -->
                <div class="lg:col-span-5 space-y-6 flex flex-col justify-between">
                    <div class="p-6 bg-slate-900/80 rounded-2xl border border-slate-800/80 hover:border-slate-700/80 transition-all duration-300">
                        <div class="flex items-start gap-4">
                            <div class="p-3 bg-red-500/10 text-red-400 rounded-xl font-bold text-xl">01</div>
                            <div class="space-y-1">
                                <h3 class="text-lg font-bold text-slate-200">Baja movilidad social</h3>
                                <p class="text-sm text-slate-400">Si naces pobre en México, la probabilidad de seguir en el mismo peldaño económico el resto de tu vida es de casi el 74%. El ascensor social está prácticamente descompuesto.</p>
                            </div>
                        </div>
                    </div>

                    <div class="p-6 bg-slate-900/80 rounded-2xl border border-slate-800/80 hover:border-slate-700/80 transition-all duration-300">
                        <div class="flex items-start gap-4">
                            <div class="p-3 bg-indigo-500/10 text-indigo-400 rounded-xl font-bold text-xl">02</div>
                            <div class="space-y-1">
                                <h3 class="text-lg font-bold text-slate-200">Asimetría territorial extrema</h3>
                                <p class="text-sm text-slate-400">El norte industrializado de México promedia ingresos equiparables a países de Europa del Este, mientras que estados del sur como Oaxaca, Chiapas o Guerrero registran índices de rezago comparables con naciones del África subsahariana.</p>
                            </div>
                        </div>
                    </div>

                    <div class="p-6 bg-slate-900/80 rounded-2xl border border-slate-800/80 hover:border-slate-700/80 transition-all duration-300">
                        <div class="flex items-start gap-4">
                            <div class="p-3 bg-emerald-500/10 text-emerald-400 rounded-xl font-bold text-xl">03</div>
                            <div class="space-y-1">
                                <h3 class="text-lg font-bold text-slate-200">Brecha de género y etnicidad</h3>
                                <p class="text-sm text-slate-400">Ser mujer e indígena en zonas rurales reduce exponencialmente el acceso a empleo formal, crédito, y tenencia de tierras, marginando las posibilidades de independencia económica sustentable.</p>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Right Live Chart -->
                <div class="lg:col-span-7 bg-slate-900 rounded-3xl p-6 sm:p-8 border border-slate-800 flex flex-col justify-between">
                    <div>
                        <div class="flex flex-col sm:flex-row justify-between sm:items-center gap-4 mb-6">
                            <div>
                                <h3 class="text-xl font-bold text-slate-100">Distribución de Riqueza por Deciles</h3>
                                <p class="text-xs text-slate-400">Cada decil agrupa al 10% de los hogares mexicanos, del más pobre (I) al más rico (X)</p>
                            </div>
                            <!-- Selection buttons to toggle chart visual metrics -->
                            <div class="inline-flex bg-slate-800 p-1 rounded-lg border border-slate-700 text-xs text-slate-300 self-start">
                                <button onclick="updateChartType('percent')" id="chart-percent-btn" class="px-3 py-1.5 rounded-md font-semibold bg-emerald-600 text-white shadow transition-all">Porcentaje %</button>
                                <button onclick="updateChartType('cash')" id="chart-cash-btn" class="px-3 py-1.5 rounded-md font-semibold transition-all">Ingreso Promedio ($)</button>
                            </div>
                        </div>

                        <!-- Canvas container for Chart.js -->
                        <div class="relative w-full h-80">
                            <canvas id="inequalityChart"></canvas>
                        </div>
                    </div>

                    <div class="mt-6 p-4 bg-slate-950 rounded-xl border border-slate-800/80 text-center text-xs text-slate-400">
                        📌 El gráfico demuestra que el <span class="text-emerald-400 font-bold">10% superior</span> (Decil X) capta un ingreso que supera holgadamente a la suma acumulada de los primeros 7 deciles enteros de la población mexicana.
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Interactive Decile Simulator Section -->
    <section id="simulador" class="py-24 bg-gradient-to-b from-slate-950 to-slate-900 relative">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="bg-slate-900/40 rounded-3xl border border-slate-800 p-8 sm:p-12 relative overflow-hidden">
                <!-- Decorative blurred circular highlight -->
                <div class="absolute -top-10 -left-10 w-64 h-64 bg-emerald-500/5 rounded-full blur-3xl"></div>
                <div class="absolute -bottom-10 -ri
