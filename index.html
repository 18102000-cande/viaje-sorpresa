<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Lisboa: Itinerario Interactivo (4-8 Dic)</title>
  
  <!-- React & Babel -->
  <script crossorigin src="https://unpkg.com/react@18/umd/react.development.js"></script>
  <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
  <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
  
  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>
  
  <!-- Font Awesome -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  
  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            azulejo: { 50: '#f0f5fa', 100: '#e1ecf4', 500: '#1d70b8', 600: '#155ca2', 900: '#0d3b66' },
            terra: { 50: '#fdf8f6', 100: '#fbe8e1', 500: '#e07a5f', 600: '#c7664d', 900: '#8c3d2b' },
            pastel: { green: '#e6f4ea', orange: '#fff0e0', pink: '#fce4ec', default: '#ffffff' }
          }
        }
      }
    }
  </script>
  
  <style>
    body { background-color: #f8fafc; font-family: system-ui, -apple-system, sans-serif; }
    .card-enter { animation: fadeIn 0.3s ease-out; }
    @keyframes fadeIn { from { opacity: 0; transform: translateY(5px); } to { opacity: 1; transform: translateY(0); } }
  </style>
</head>
<body>
  <div id="root"></div>

  <script type="text/babel">
    const { useState, useEffect, useMemo } = React;

    // --- RAW DATA EXTRACTION (100% Fidelity) ---
    
    const initialItinerary = [
      { id: '1-1', day: 'VIERNES 4 DICIEMBRE', hora: '20:05', actividad: 'Aterrizaje T1', zona: 'Aeropuerto', transporte: '-', detalle: 'Recoger maletas y comprar tarjeta Viva Viagem', coste: '0,50€ tarjeta', comida: '-', type: 'default' },
      { id: '1-2', day: 'VIERNES 4 DICIEMBRE', hora: '20:30', actividad: 'Metro al hotel', zona: 'Aeropuerto → Marquês de Pombal', transporte: 'Metro Línea Roja: Aeropuerto → São Sebastião (18 min) · Cambio a Línea Azul: São Sebastião → Marquês de Pombal (2 min) · 5 min a pie hasta el hotel. Total ~25 min puerta a puerta', detalle: 'Llegada al hotel', coste: '1,65-1,80€/persona (o pase 24h, ver hoja Notas)', comida: '-', type: 'default' },
      { id: '1-3', day: 'VIERNES 4 DICIEMBRE', hora: '21:15', actividad: 'Check-in Turim Marquês', zona: 'Marquês de Pombal', transporte: '5 min a pie desde la estación', detalle: 'Dejar maletas y refrescarse', coste: '-', comida: '-', type: 'default' },
      { id: '1-4', day: 'VIERNES 4 DICIEMBRE', hora: '21:45', actividad: 'Cena de bienvenida', zona: 'Rato / Príncipe Real', transporte: '10-15 min a pie desde el hotel', detalle: 'Petiscos en una tasca de la zona', coste: '15-25€/persona', comida: 'O Faz Frio – tasca portuguesa, bacalhau del día – 15-23€ | Tascardoso – bitoque gigante, sin reservas – ~15€ | A Cevicheria – ceviche peruano-portugués – ~25€ (esperas largas, sin reservas)', type: 'default' },
      
      { id: '2-1', day: 'SÁBADO 5 DICIEMBRE', hora: '11:00', actividad: 'Despertar y desayuno', zona: 'Marquês de Pombal (hotel)', transporte: 'A pie, 2-5 min desde el hotel', detalle: 'Cafetería cerca del hotel', coste: '4-8€/persona', comida: 'Padaria Portuguesa – café+nata+tostada – 4-5€ | Zenith Caffè – brunch americano – 8-10€', type: 'default' },
      { id: '2-2', day: 'SÁBADO 5 DICIEMBRE', hora: '12:00', actividad: 'Baixa', zona: 'Rossio / Rua Augusta', transporte: 'Metro Azul: Marquês de Pombal → Restauradores (6 min) + 5 min a pie. Alternativa: bajar Av. da Liberdade a pie (20-25 min, cuesta abajo, muy agradable)', detalle: 'Rossio, Praça da Figueira, mercado navideño', coste: 'Gratis', comida: '-', type: 'free' },
      { id: '2-3', day: 'SÁBADO 5 DICIEMBRE', hora: '12:45', actividad: 'Elevador de Santa Justa', zona: 'Baixa', transporte: '5 min a pie desde Rossio', detalle: 'Vista gratis desde abajo, subida opcional', coste: 'Opcional ~3,50€ ida-vuelta', comida: '-', type: 'optional' },
      { id: '2-4', day: 'SÁBADO 5 DICIEMBRE', hora: '13:15', actividad: 'Praça do Comércio', zona: 'Baixa', transporte: '5 min a pie', detalle: 'Plaza junto al río, la más bonita de Lisboa', coste: 'Gratis', comida: '-', type: 'free' },
      { id: '2-5', day: 'SÁBADO 5 DICIEMBRE', hora: '14:00', actividad: 'Comida', zona: 'Alfama / Baixa', transporte: '10-15 min a pie subiendo hacia Alfama', detalle: 'Tasca típica', coste: '10-15€/persona', comida: 'O Velho Eurico – bacalhau/chanfana, sin reservas, ir antes de las 13:00 – 10-12€ | A Merendinha do Arco – petiscos tradicionales – 10-15€ | Taberna Tosca – tasca de barrio en Baixa – 10-15€', type: 'default' },
      { id: '2-6', day: 'SÁBADO 5 DICIEMBRE', hora: '15:30', actividad: 'Sé de Lisboa + paseo por Alfama', zona: 'Alfama', transporte: 'Ya en la zona, todo a pie', detalle: 'Catedral (exterior gratis) y callejeo por el barrio más antiguo', coste: 'Gratis', comida: '-', type: 'free' },
      { id: '2-7', day: 'SÁBADO 5 DICIEMBRE', hora: '16:15', actividad: 'Miradouro Portas do Sol / Santa Luzia', zona: 'Alfama', transporte: '10 min a pie cuesta arriba desde la Sé', detalle: 'Vistas gratis sobre los tejados', coste: 'Gratis', comida: '-', type: 'free' },
      { id: '2-8', day: 'SÁBADO 5 DICIEMBRE', hora: '16:45', actividad: 'Castelo de São Jorge', zona: 'Alfama / Castelo', transporte: '5-10 min a pie cuesta arriba desde el miradouro', detalle: 'Opcional', coste: 'Opcional ~15€', comida: '-', type: 'optional' },
      { id: '2-9', day: 'SÁBADO 5 DICIEMBRE', hora: '17:45', actividad: 'Descanso opcional', zona: 'Vuelta al hotel', transporte: 'Metro Verde: Baixa-Chiado (15 min a pie bajando desde el castillo) → cambio Azul → Marquês de Pombal (10 min) = ~25-30 min. O taxi/Uber directo (~8-10€, 15 min)', detalle: 'Siesta antes de la noche', coste: '-', comida: '-', type: 'optional' },
      { id: '2-10', day: 'SÁBADO 5 DICIEMBRE', hora: '19:30', actividad: 'Bairro Alto', zona: 'Bairro Alto', transporte: 'Desde el hotel: 20 min a pie cuesta abajo, o Metro Azul → Restauradores (6 min) + 10 min a pie', detalle: 'Paseo y chupito de ginjinha', coste: '1€ el chupito', comida: 'A Ginjinha do Rossio – chupito de ginjinha, de camino – 1€', type: 'default' },
      { id: '2-11', day: 'SÁBADO 5 DICIEMBRE', hora: '21:00', actividad: 'Cena', zona: 'Bairro Alto', transporte: 'Ya en la zona', detalle: 'Petiscos, fado opcional en alguna taberna', coste: '12-25€/persona', comida: 'Tasca do Chico – petiscos + fado espontáneo – 12-15€ | Tasca dos Canários – tasca de barrio – 12-15€ | Sinal Vermelho – petiscos más elaborados, conviene reservar – 20-25€', type: 'default' },
      { id: '2-12', day: 'SÁBADO 5 DICIEMBRE', hora: '23:00', actividad: 'Copa nocturna opcional', zona: 'Bairro Alto', transporte: 'Ya en la zona', detalle: 'Bairro Alto sigue animado toda la noche', coste: 'Opcional', comida: '-', type: 'optional' },
      { id: '2-13', day: 'SÁBADO 5 DICIEMBRE', hora: '00:30', actividad: 'Vuelta al hotel', zona: 'Bairro Alto → Marquês de Pombal', transporte: 'Taxi/Uber recomendado de noche (~8-10€, 10 min) — cuesta arriba y algo largo a pie a esas horas', detalle: '-', coste: '-', comida: '-', type: 'default' },

      { id: '3-1', day: 'DOMINGO 6 DICIEMBRE', hora: '11:30', actividad: 'Desayuno', zona: 'Marquês de Pombal (hotel)', transporte: 'A pie, cerca del hotel', detalle: 'Antes de salir hacia Belém', coste: '4-5€/persona', comida: 'Padaria Portuguesa – 4-5€', type: 'default' },
      { id: '3-2', day: 'DOMINGO 6 DICIEMBRE', hora: '12:00', actividad: 'Hacia Belém', zona: 'Marquês de Pombal → Belém', transporte: 'Metro Azul: Marquês de Pombal → Baixa-Chiado (8 min directo) → cambio Verde → Cais do Sodré (3 min) = 15 min. Luego Tram histórico 15E: Cais do Sodré → Belém, parada "Mosteiro Jerónimos" (~25 min)', detalle: 'Total puerta a puerta ~45 min', coste: '1,65€ metro + 1,65€ tram/persona (o incluido en pase 24h)', comida: '-', type: 'default' },
      { id: '3-3', day: 'DOMINGO 6 DICIEMBRE', hora: '12:45', actividad: 'Pastéis de Belém', zona: 'Belém', transporte: '2 min a pie desde la parada del tram', detalle: 'El pastel de nata original', coste: '~1,20€/unidad', comida: 'Antiga Confeitaria de Belém – 2 pastéis + café – ~5€ (llegar antes de las 12:00 para evitar cola larga)', type: 'default' },
      { id: '3-4', day: 'DOMINGO 6 DICIEMBRE', hora: '13:15', actividad: 'Mosteiro dos Jerónimos', zona: 'Belém', transporte: '3 min a pie', detalle: 'Exterior gratis, interior opcional', coste: 'Gratis / Opcional ~10€', comida: '-', type: 'optional' },
      { id: '3-5', day: 'DOMINGO 6 DICIEMBRE', hora: '14:00', actividad: 'Comida', zona: 'LX Factory (Alcântara)', transporte: 'Tram 15E Belém → Alcântara/LX Factory (parada Calvário, ~10 min) o 20 min a pie junto al río', detalle: 'Foodtrucks y restaurantes variados', coste: '10-20€/persona', comida: 'Mex Factory – tacos y burritos mexicanos – 10-12€ | Cantina LX – portuguesa con terraza – 15-20€ | Sushi Factory – sushi all-you-can-eat – 16,90€ (comida)', type: 'default' },
      { id: '3-6', day: 'DOMINGO 6 DICIEMBRE', hora: '15:30', actividad: 'Torre de Belém + Padrão dos Descobrimentos', zona: 'Belém', transporte: '15-20 min a pie de vuelta hacia el río desde LX Factory, o tram 15E una parada', detalle: 'Exteriores gratis, subidas opcionales', coste: 'Gratis / Opcional ~6-8€', comida: '-', type: 'optional' },
      { id: '3-7', day: 'DOMINGO 6 DICIEMBRE', hora: '17:00', actividad: 'LX Factory', zona: 'LX Factory', transporte: 'Ya en la zona', detalle: 'Tiendas y arte urbano', coste: 'Gratis (visitar)', comida: '-', type: 'free' },
      { id: '3-8', day: 'DOMINGO 6 DICIEMBRE', hora: '18:00', actividad: 'Descanso opcional', zona: 'Vuelta al hotel', transporte: 'Tram 15E Alcântara → Cais do Sodré (10 min) + Metro Verde/Azul → Marquês de Pombal (10 min) = ~20-25 min', detalle: 'Siesta', coste: '-', comida: '-', type: 'optional' },
      { id: '3-9', day: 'DOMINGO 6 DICIEMBRE', hora: '19:30', actividad: 'Time Out Market', zona: 'Cais do Sodré', transporte: 'Metro Azul → Baixa-Chiado → cambio Verde → Cais do Sodré (~15 min desde el hotel)', detalle: 'Mercado gastronómico', coste: '-', comida: '-', type: 'default' },
      { id: '3-10', day: 'DOMINGO 6 DICIEMBRE', hora: '21:00', actividad: 'Cena', zona: 'Cais do Sodré', transporte: 'Ya en el mercado', detalle: 'Elige entre muchos puestos económicos', coste: '10-15€/persona', comida: 'Time Out Market – decenas de puestos de todo tipo – 10-15€/persona', type: 'default' },

      { id: '4-1', day: 'LUNES 7 DICIEMBRE', hora: '11:30', actividad: 'Desayuno', zona: 'Chiado', transporte: 'Metro Azul: Marquês de Pombal → Baixa-Chiado (8 min)', detalle: 'Desayunar ya en Chiado', coste: '4-12€/persona', comida: 'Dear Breakfast – brunch – 8-12€ | Manteigaria – café + pastéis de nata – 4€', type: 'default' },
      { id: '4-2', day: 'LUNES 7 DICIEMBRE', hora: '12:00', actividad: 'Chiado', zona: 'Chiado', transporte: 'Ya en la zona', detalle: 'Calles comerciales, Convento do Carmo opcional', coste: 'Gratis / Opcional ~5€', comida: '-', type: 'optional' },
      { id: '4-3', day: 'LUNES 7 DICIEMBRE', hora: '13:00', actividad: 'Príncipe Real', zona: 'Príncipe Real', transporte: '10-15 min a pie cuesta arriba desde Chiado', detalle: 'Jardín y tiendas vintage', coste: 'Gratis', comida: '-', type: 'free' },
      { id: '4-4', day: 'LUNES 7 DICIEMBRE', hora: '14:00', actividad: 'Comida', zona: 'Príncipe Real / Estrela', transporte: 'Ya cerca, la zona se recorre a pie', detalle: 'Tasca de la zona', coste: '15-25€/persona', comida: 'Tascardoso – bitoque gigante – ~15€ | O Faz Frio – bacalhau del día – 15-23€ | A Cevicheria – ceviche – ~25€', type: 'default' },
      { id: '4-5', day: 'LUNES 7 DICIEMBRE', hora: '15:30', actividad: 'Basílica da Estrela + jardín', zona: 'Estrela', transporte: '15 min a pie desde Príncipe Real, o Tram 28E', detalle: 'Entrada gratis, jardín precioso al lado', coste: 'Gratis', comida: '-', type: 'free' },
      { id: '4-6', day: 'LUNES 7 DICIEMBRE', hora: '16:15', actividad: 'Ferry a Cacilhas', zona: 'Cais do Sodré', transporte: 'Desde Estrela: Taxi/Uber recomendado hasta Cais do Sodré (~10 min, 6-8€). Alternativa: Metro Amarela Rato (15 min a pie) → cambio Baixa-Chiado a Verde → Cais do Sodré', detalle: 'Cruce del Tajo, vistas del skyline de Lisboa', coste: '1,30-1,70€/trayecto (ferry)', comida: '-', type: 'default' },
      { id: '4-7', day: 'LUNES 7 DICIEMBRE', hora: '17:15', actividad: 'Miradouro da Graça / Senhora do Monte', zona: 'Graça', transporte: 'Ferry de vuelta a Cais do Sodré (10 min) + Tram 28E hasta Graça (~20 min), o taxi (~10€, 15 min)', detalle: 'Atardecer (en diciembre cae ~17:20-17:30h, único horario fijo del día)', coste: 'Gratis', comida: '-', type: 'free' },
      { id: '4-8', day: 'LUNES 7 DICIEMBRE', hora: '18:15', actividad: 'Descanso opcional', zona: 'Graça', transporte: 'Ya en la zona', detalle: 'Antes de la cena especial', coste: '-', comida: '-', type: 'optional' },
      { id: '4-9', day: 'LUNES 7 DICIEMBRE', hora: '21:00', actividad: 'CENA ESPECIAL', zona: 'Costa do Castelo / Alfama alta', transporte: '10 min a pie desde el miradouro', detalle: 'La noche especial del viaje', coste: '30-45€/persona', comida: 'Chapitô à Mesa – vistas al Tajo y al castillo, ambiente bohemio – 30-40€ | Zunzum Gastrobar – terraza con vistas al río – 35-45€ | Taberna Tuga – cocina portuguesa moderna, ambiente íntimo – 30-35€ | Eleven (Amoreiras) – 1 estrella Michelin, capricho grande – 90-120€', type: 'special' },
      { id: '4-10', day: 'LUNES 7 DICIEMBRE', hora: '23:00', actividad: 'Vuelta al hotel', zona: 'Alfama → Marquês de Pombal', transporte: 'Taxi/Uber recomendado de noche (~10€, 15 min) — zona empinada y mal conectada a esas horas', detalle: '-', coste: '-', comida: '-', type: 'default' },

      { id: '5-1', day: 'MARTES 8 DICIEMBRE', hora: '11:00', actividad: 'Desayuno tranquilo', zona: 'Marquês de Pombal (hotel)', transporte: 'A pie, cerca del hotel', detalle: 'Última pastelaria antes de hacer el equipaje', coste: '4-6€/persona', comida: 'Padaria Portuguesa – 4-5€', type: 'default' },
      { id: '5-2', day: 'MARTES 8 DICIEMBRE', hora: '12:00', actividad: 'Check-out', zona: 'Hotel', transporte: '-', detalle: 'Dejar maletas en consigna del hotel si es posible', coste: '-', comida: '-', type: 'default' },
      { id: '5-3', day: 'MARTES 8 DICIEMBRE', hora: '12:15', actividad: 'Parque Eduardo VII', zona: 'Marquês de Pombal', transporte: '5 min a pie desde el hotel', detalle: 'Vistas panorámicas, gratis', coste: 'Gratis', comida: '-', type: 'free' },
      { id: '5-4', day: 'MARTES 8 DICIEMBRE', hora: '13:00', actividad: 'Fundação Gulbenkian', zona: 'São Sebastião', transporte: '10 min a pie, o 1 parada Metro Azul (Marquês de Pombal → São Sebastião, 2 min) + 5 min a pie', detalle: 'Jardines gratis, museo opcional', coste: 'Gratis / Opcional ~14€', comida: '-', type: 'optional' },
      { id: '5-5', day: 'MARTES 8 DICIEMBRE', hora: '14:00', actividad: 'Última comida', zona: 'Marquês de Pombal', transporte: '10 min a pie de vuelta hacia el hotel', detalle: 'Algo típico que aún no probasteis', coste: '10-15€/persona', comida: 'Volved a la tasca que más os gustó del viaje, o probad una nueva cerca del hotel', type: 'default' },
      { id: '5-6', day: 'MARTES 8 DICIEMBRE', hora: '16:00', actividad: 'Recoger maletas', zona: 'Hotel', transporte: '-', detalle: 'Preparar la salida hacia el aeropuerto', coste: '-', comida: '-', type: 'default' },
      { id: '5-7', day: 'MARTES 8 DICIEMBRE', hora: '17:30', actividad: 'Salida al aeropuerto', zona: 'Marquês de Pombal → Aeroporto', transporte: 'Metro Azul: Marquês de Pombal → São Sebastião (2 min) → cambio Línea Roja → Aeroporto (18 min). Total ~25-30 min con margen', detalle: '-', coste: '1,65-1,80€/persona', comida: '-', type: 'default' },
      { id: '5-8', day: 'MARTES 8 DICIEMBRE', hora: '18:15', actividad: 'Llegada al aeropuerto', zona: 'Aeropuerto', transporte: '-', detalle: 'Margen de sobra para un aeropuerto que no conocéis', coste: '-', comida: '-', type: 'default' },
      { id: '5-9', day: 'MARTES 8 DICIEMBRE', hora: '20:45', actividad: 'Vuelo de vuelta', zona: '-', transporte: '-', detalle: '-', coste: '-', comida: '-', type: 'default' }
    ];

    const restaurantList = [
      { zona: 'MARQUÊS DE POMBAL (zona del hotel)', momento: 'Desayuno', nombre: 'Padaria Portuguesa', tipo: 'Panadería / cadena', quePedir: 'Café + pastel de nata + tostada, rápido y fiable', precio: '4-5€/persona' },
      { zona: 'MARQUÊS DE POMBAL (zona del hotel)', momento: 'Desayuno', nombre: 'Zenith Caffè', tipo: 'Café / brunch', quePedir: 'Brunch americano si os apetece algo más completo', precio: '8-10€/persona' },
      { zona: 'MARQUÊS DE POMBAL (zona del hotel)', momento: 'Comida/Cena', nombre: 'Cualquier tasca de la zona', tipo: 'Tasca portuguesa', quePedir: 'Última comida: repetid la que más os gustó del viaje', precio: '10-15€/persona' },
      { zona: 'RATO / PRÍNCIPE REAL', momento: 'Comida/Cena', nombre: 'O Faz Frio', tipo: 'Tasca portuguesa', quePedir: 'Bacalhau del día (distinto cada día de la semana), sin reservas, llegar pronto', precio: '15-23€/persona' },
      { zona: 'RATO / PRÍNCIPE REAL', momento: 'Comida/Cena', nombre: 'Tascardoso', tipo: 'Tasca de barrio', quePedir: 'El famoso bitoque gigante, sin reservas, ir a la hora de apertura', precio: '~15€/persona' },
      { zona: 'RATO / PRÍNCIPE REAL', momento: 'Comida/Cena', nombre: 'A Cevicheria', tipo: 'Peruano-portugués', quePedir: 'Ceviche (incl. versión con bacalhau), sin reservas, esperas de hasta 1h30', precio: '~25€/persona' },
      { zona: 'BAIXA / ROSSIO', momento: 'Desayuno', nombre: 'Fábrica da Nata', tipo: 'Pastelería', quePedir: 'Café + 2 pastéis de nata recién hechos', precio: '4€/persona' },
      { zona: 'BAIXA / ROSSIO', momento: 'Desayuno', nombre: 'Confeitaria Nacional', tipo: 'Pastelería histórica', quePedir: 'Desde 1829, ambiente clásico, buena repostería', precio: '5€/persona' },
      { zona: 'BAIXA / ROSSIO', momento: 'Cualquier momento', nombre: 'A Ginjinha do Rossio', tipo: 'Licorería típica', quePedir: 'El chupito de ginjinha más famoso de Lisboa, parada de 2 min', precio: '1€/chupito' },
      { zona: 'ALFAMA / MOURARIA', momento: 'Comida', nombre: 'O Velho Eurico', tipo: 'Casa de pasto tradicional', quePedir: 'Bacalhau, chanfana. Sin reservas, ir antes de las 13:00', precio: '10-12€/persona' },
      { zona: 'ALFAMA / MOURARIA', momento: 'Comida', nombre: 'A Merendinha do Arco', tipo: 'Tasca tradicional', quePedir: 'Petiscos en ambiente sencillo y auténtico', precio: '10-15€/persona' },
      { zona: 'ALFAMA / MOURARIA', momento: 'Comida', nombre: 'Taberna Tosca', tipo: 'Tasca de barrio', quePedir: 'Alternativa sencilla y económica en Baixa/Alfama', precio: '10-15€/persona' },
      { zona: 'ALFAMA / MOURARIA', momento: 'Desayuno (alt.)', nombre: 'Pastelaria Alfama Doce', tipo: 'Pastelería de barrio', quePedir: 'Muy bien valorada, ambiente local', precio: '4€/persona' },
      { zona: 'BAIRRO ALTO', momento: 'Cena', nombre: 'Tasca do Chico', tipo: 'Tasca + fado espontáneo', quePedir: 'Petiscos, ambiente único, fado improvisado por la noche', precio: '12-15€/persona' },
      { zona: 'BAIRRO ALTO', momento: 'Cena', nombre: 'Tasca dos Canários', tipo: 'Tasca de barrio', quePedir: 'Petiscos tradicionales, buen ambiente local', precio: '12-15€/persona' },
      { zona: 'BAIRRO ALTO', momento: 'Cena', nombre: 'Sinal Vermelho', tipo: 'Portuguesa elaborada', quePedir: 'Un escalón más elaborado, conviene reservar', precio: '20-25€/persona' },
      { zona: 'BELÉM', momento: 'Desayuno/parada', nombre: 'Antiga Confeitaria de Belém', tipo: 'El pastel de nata ORIGINAL', quePedir: 'Llegar antes de las 12:00 o esperar cola larga', precio: '~5€/persona (2 pastéis + café)' },
      { zona: 'BELÉM', momento: 'Comida (alt.)', nombre: 'Tasca do Gordo', tipo: 'Casa de comidas', quePedir: 'Menú del día casero, cerca del Mosteiro', precio: '10-12€/persona' },
      { zona: 'LX FACTORY / ALCÂNTARA', momento: 'Comida', nombre: 'Mex Factory', tipo: 'Mexicano', quePedir: 'Tacos, burritos, nachos — raciones pequeñas para compartir', precio: '10-12€/persona' },
      { zona: 'LX FACTORY / ALCÂNTARA', momento: 'Comida', nombre: 'Cantina LX', tipo: 'Portuguesa con terraza', quePedir: 'Pulpo y platos a la brasa, ambiente con estilo', precio: '15-20€/persona' },
      { zona: 'LX FACTORY / ALCÂNTARA', momento: 'Comida', nombre: 'Sushi Factory', tipo: 'Japonés all-you-can-eat', quePedir: 'Sushi ilimitado, ideal si os gusta mucho el sushi', precio: '16,90€ comida / 20,90€ cena' },
      { zona: 'CAIS DO SODRÉ', momento: 'Cena', nombre: 'Time Out Market', tipo: 'Mercado gastronómico', quePedir: 'Decenas de puestos de todo tipo, elige lo que os apetezca', precio: '10-15€/persona' },
      { zona: 'CHIADO', momento: 'Desayuno', nombre: 'Dear Breakfast', tipo: 'Brunch', quePedir: 'Desayuno más elaborado, buen sitio para ir sin prisa', precio: '8-12€/persona' },
      { zona: 'CHIADO', momento: 'Desayuno', nombre: 'Manteigaria', tipo: 'Pastelería', quePedir: 'Los pastéis de nata mejor valorados de la ciudad', precio: '4€/persona' },
      { zona: 'CHIADO', momento: 'Comida/Cena (alt.)', nombre: 'Taberna da Rua das Flores', tipo: 'Petiscos contemporáneos', quePedir: 'Muy valorada, conviene reservar', precio: '15-20€/persona' },
      { zona: 'COSTA DO CASTELO / ALFAMA ALTA', momento: 'Cena especial', nombre: 'Chapitô à Mesa', tipo: 'Portuguesa con vistas', quePedir: 'Vistas espectaculares al Tajo y a Lisboa, ambiente bohemio único', precio: '30-40€/persona' },
      { zona: 'COSTA DO CASTELO / ALFAMA ALTA', momento: 'Cena especial', nombre: 'Zunzum Gastrobar', tipo: 'Terraza / creativa', quePedir: 'Vistas al río, platos creativos, especial sin ser carísimo', precio: '35-45€/persona' },
      { zona: 'COSTA DO CASTELO / ALFAMA ALTA', momento: 'Cena especial', nombre: 'Taberna Tuga', tipo: 'Portuguesa moderna', quePedir: 'Ambiente íntimo y romántico', precio: '30-35€/persona' },
      { zona: 'COSTA DO CASTELO / ALFAMA ALTA', momento: 'Cena especial (splurge)', nombre: 'Eleven', tipo: 'Alta cocina (1 estrella Michelin)', quePedir: 'Vistas panorámicas de la ciudad, para un capricho grande', precio: '90-120€/persona' },
    ];

    const notasData = {
      maquina: [
        "En cualquier estación de metro, buscad las máquinas verdes de venta de billetes ('Máquinas de Venda').",
        "Tocad la pantalla y elegid idioma (hay inglés y español disponibles).",
        "Si es la primera vez, comprad primero la tarjeta reutilizable 'Viva Viagem' (0,50€, una por persona) — opción 'Comprar cartão'.",
        "Elegid 'Carregar título' (recargar) → 'Navegante Ocasional' → '24 horas' (~6,60€/persona, viajes ilimitados en metro, bus, tram y elevadores/funiculares durante 24h).",
        "Pagad con tarjeta bancaria o efectivo en la propia máquina.",
        "Validad la tarjeta pasándola por el lector del torno al entrar. El contador de 24h empieza a correr desde esa primera validación, NO desde el momento de la compra — comprad con calma, validad solo cuando vayáis a empezar a usarlo de verdad.",
        "Guardad la tarjeta todos los días: es reutilizable y se puede recargar tantas veces como queráis.",
        "Cada persona necesita su propia tarjeta — no se puede compartir pasándola dos veces por el mismo torno."
      ],
      alternativa: "Si algún día vais a hacer pocos trayectos, el billete sencillo (1,65-1,80€, válido 1h con transbordos) puede salir más barato que el pase de 24h — haced números según cuántos trayectos tengáis ese día.",
      lineas: [
        { nombre: 'Línea Roja (Vermelha)', desc: 'Aeropuerto ↔ São Sebastião. La usaréis para ir y volver del aeropuerto (día 1 y día 5).', color: 'bg-red-500' },
        { nombre: 'Línea Azul (Azul)', desc: 'São Sebastião ↔ Marquês de Pombal (vuestro hotel) ↔ Restauradores ↔ Baixa-Chiado. La línea que más usaréis, conecta el hotel con casi todo.', color: 'bg-blue-500' },
        { nombre: 'Línea Verde (Verde)', desc: 'Baixa-Chiado ↔ Cais do Sodré (y hacia el norte). La necesitáis para ir a Belém (combinando con el tram) y al Time Out Market.', color: 'bg-green-500' },
        { nombre: 'Línea Amarilla (Amarela)', desc: 'Rato ↔ Marquês de Pombal. Alternativa si vais desde Príncipe Real/Rato.', color: 'bg-yellow-400' }
      ],
      transbordo: "São Sebastião: aquí cambiáis entre la Línea Roja (aeropuerto) y la Línea Azul (hotel). Es un cambio de andén sencillo, 1-2 min.",
      general: [
        { k: 'Aeropuerto → hotel', v: 'Línea Roja hasta São Sebastião, cambio a Línea Azul hasta Marquês de Pombal. ~25 min + 5 min a pie' },
        { k: 'Hotel → aeropuerto (vuelta)', v: 'Mismo trayecto a la inversa. Salir del hotel a las 17:30 para un vuelo a las 20:45 deja margen de sobra' },
        { k: 'Trayectos sin metro cercano', v: 'Campo de Ourique → Cais do Sodré y Estrela → Cais do Sodré no tienen conexión directa cómoda: mejor taxi/Uber (6-8€, ~10 min) que hacer transbordos largos' },
        { k: 'De noche', v: 'El metro cierra a la 01:00. Si salís de Bairro Alto o de la cena especial (Alfama alta) después de esa hora o la zona es empinada, mejor taxi/Uber (8-10€) que caminar cuesta arriba' },
        { k: 'Reservas', v: 'Muchas tascas tradicionales (O Velho Eurico, Tasca do Chico, Tascardoso, A Cevicheria) NO aceptan reserva, van por orden de llegada. Para la cena especial (día 4) sí conviene reservar con antelación' },
        { k: 'Efectivo', v: 'Llevar algo de efectivo: muchas tascas clásicas de Alfama/Mouraria no aceptan tarjeta' },
        { k: 'Entradas opcionales', v: 'Castelo São Jorge ~15€ · Interior Jerónimos ~10€ · Torre de Belém ~6€ · Convento do Carmo ~5€ · Gulbenkian ~14€ — todas marcadas como opcionales en el itinerario, decidid sobre la marcha' },
        { k: 'Siestas', v: 'Marcadas en naranja en la hoja Itinerario: si vais cansados, aprovechad ese hueco; si no, seguid directos al siguiente punto' }
      ]
    };

    const DAYS = ['VIERNES 4 DICIEMBRE', 'SÁBADO 5 DICIEMBRE', 'DOMINGO 6 DICIEMBRE', 'LUNES 7 DICIEMBRE', 'MARTES 8 DICIEMBRE'];

    // --- HELPER FUNCTIONS ---
    const getMapsUrl = (query) => `https://www.google.com/maps/search/?api=1&query=${encodeURIComponent(query + ' Lisbon')}`;
    
    const parsePrice = (costStr) => {
      if (!costStr || costStr === '-' || costStr.toLowerCase().includes('gratis')) return 0;
      const match = costStr.match(/(\d+(?:[,.]\d+)?)/);
      if (match) return parseFloat(match[1].replace(',', '.'));
      return 0;
    };

    // --- COMPONENTS ---

    const TimelineCard = ({ item, index, isFirst, isLast, onMoveUp, onMoveDown, onEdit }) => {
      const [expanded, setExpanded] = useState(false);
      
      const getBgColor = (type) => {
        if(type === 'free') return 'bg-pastel-green border-green-300';
        if(type === 'optional') return 'bg-pastel-orange border-orange-300';
        if(type === 'special') return 'bg-pastel-pink border-pink-300';
        return 'bg-white border-gray-200';
      };

      const renderRestaurants = (comidaStr) => {
        if (!comidaStr || comidaStr === '-') return null;
        const options = comidaStr.split('|').map(o => o.trim());
        return (
          <div className="mt-3 p-3 bg-gray-50 rounded-md border border-gray-100">
            <h5 className="text-sm font-semibold text-gray-700 mb-2"><i className="fa-solid fa-utensils mr-2"></i>Dónde comer aquí:</h5>
            <ul className="space-y-2">
              {options.map((opt, i) => {
                const parts = opt.split('–').map(p => p.trim());
                const name = parts[0];
                return (
                  <li key={i} className="text-sm">
                    <a href={getMapsUrl(name)} target="_blank" className="font-medium text-azulejo-600 hover:underline mr-1">{name}</a>
                    {parts.slice(1).join(' – ')}
                  </li>
                );
              })}
            </ul>
          </div>
        );
      };

      return (
        <div className={`card-enter relative flex flex-col md:flex-row gap-4 p-4 mb-4 rounded-xl shadow-sm border ${getBgColor(item.type)} transition-all duration-200`}>
          <div className="flex flex-col items-center justify-between md:w-24 shrink-0 border-b md:border-b-0 md:border-r border-gray-300 pb-3 md:pb-0 md:pr-4">
            <div className="text-lg font-bold text-gray-800">{item.hora}</div>
            <div className="flex gap-2 mt-2">
              <button onClick={() => onMoveUp(index)} disabled={isFirst} className="text-gray-400 hover:text-gray-700 disabled:opacity-30"><i className="fa-solid fa-chevron-up"></i></button>
              <button onClick={() => onMoveDown(index)} disabled={isLast} className="text-gray-400 hover:text-gray-700 disabled:opacity-30"><i className="fa-solid fa-chevron-down"></i></button>
            </div>
          </div>
          
          <div className="flex-grow cursor-pointer" onClick={() => setExpanded(!expanded)}>
            <div className="flex justify-between items-start">
              <div>
                <h3 className="text-xl font-bold text-gray-900 flex items-center gap-2">
                  {item.actividad}
                  <a href={getMapsUrl(item.actividad)} target="_blank" onClick={e => e.stopPropagation()} className="text-azulejo-500 hover:text-azulejo-900 text-sm" title="Abrir en Google Maps">
                    <i className="fa-solid fa-map-location-dot"></i>
                  </a>
                </h3>
                <p className="text-sm font-medium text-gray-600 mt-1"><i className="fa-solid fa-location-dot mr-1"></i> {item.zona}</p>
                <p className="text-gray-700 mt-2">{item.detalle}</p>
              </div>
              <div className="flex flex-col items-end gap-2">
                <span className="inline-flex items-center px-2.5 py-0.5 rounded-full text-xs font-medium bg-gray-100 text-gray-800 border border-gray-200">
                  {item.coste}
                </span>
                <button onClick={(e) => { e.stopPropagation(); onEdit(item); }} className="text-gray-400 hover:text-terra-600 transition-colors">
                  <i className="fa-solid fa-pen-to-square"></i> Editar
                </button>
              </div>
            </div>

            {expanded && (
              <div className="mt-4 pt-4 border-t border-gray-200/50">
                <p className="text-sm text-gray-800 mb-2"><strong><i className="fa-solid fa-train-subway mr-1"></i> Cómo llegar:</strong> {item.transporte}</p>
                {renderRestaurants(item.comida)}
              </div>
            )}
            
            {!expanded && (
              <div className="mt-2 text-xs text-gray-400 text-center">
                Click para {item.comida !== '-' ? 'ver restaurantes y ' : ''}detalles de transporte <i className="fa-solid fa-chevron-down"></i>
              </div>
            )}
          </div>
        </div>
      );
    };

    const App = () => {
      const [itinerary, setItinerary] = useState(initialItinerary);
      const [activeTab, setActiveTab] = useState('itinerary');
      const [activeDay, setActiveDay] = useState(DAYS[0]);
      
      // Editor Modal State
      const [editingItem, setEditingItem] = useState(null);
      const [editForm, setEditForm] = useState({});

      // Filters State for Restaurants
      const [resFilters, setResFilters] = useState({ zona: '', momento: '', tipo: '' });

      // Budget Calculation
      const liveBudget = useMemo(() => {
        return itinerary.reduce((acc, curr) => acc + parsePrice(curr.coste), 0).toFixed(2);
      }, [itinerary]);

      // Actions
      const handleMove = (index, direction) => {
        const dayItems = itinerary.filter(i => i.day === activeDay);
        const allOther = itinerary.filter(i => i.day !== activeDay);
        
        if (direction === 'up' && index > 0) {
          const temp = dayItems[index];
          dayItems[index] = dayItems[index - 1];
          dayItems[index - 1] = temp;
        } else if (direction === 'down' && index < dayItems.length - 1) {
          const temp = dayItems[index];
          dayItems[index] = dayItems[index + 1];
          dayItems[index + 1] = temp;
        }
        
        setItinerary([...allOther, ...dayItems].sort((a,b) => {
           let da = DAYS.indexOf(a.day), db = DAYS.indexOf(b.day);
           if(da !== db) return da - db;
           return a.hora.localeCompare(b.hora);
        }));
      };

      const handleSaveEdit = () => {
        if(editForm.id) {
          setItinerary(itinerary.map(i => i.id === editForm.id ? editForm : i));
        } else {
          // New Stop
          setItinerary([...itinerary, { ...editForm, id: Date.now().toString(), day: activeDay }]);
        }
        setEditingItem(null);
      };

      // Filtered Restaurants
      const zonas = [...new Set(restaurantList.map(r => r.zona))].filter(Boolean);
      const momentos = [...new Set(restaurantList.map(r => r.momento))].filter(Boolean);
      const tipos = [...new Set(restaurantList.map(r => r.tipo))].filter(Boolean);

      const filteredRestaurants = restaurantList.filter(r => {
        return (resFilters.zona === '' || r.zona === resFilters.zona) &&
               (resFilters.momento === '' || r.momento === resFilters.momento) &&
               (resFilters.tipo === '' || r.tipo === resFilters.tipo);
      });

      return (
        <div className="min-h-screen pb-20">
          {/* Header */}
          <header className="bg-azulejo-900 text-white p-5 sticky top-0 z-40 shadow-md">
            <div className="max-w-4xl mx-auto flex flex-col md:flex-row justify-between items-center gap-4">
              <div>
                <h1 className="text-2xl font-bold tracking-wide"><i className="fa-solid fa-tram"></i> Lisboa: 4 al 8 Dic</h1>
                <p className="text-azulejo-100 text-sm">Tu itinerario interactivo y 100% editable</p>
              </div>
              <div className="bg-white/10 px-4 py-2 rounded-lg flex items-center gap-3 backdrop-blur-sm">
                <i className="fa-solid fa-wallet text-terra-500 text-xl"></i>
                <div>
                  <div className="text-xs text-azulejo-100 uppercase font-semibold">Presupuesto Aprox.</div>
                  <div className="text-xl font-bold font-mono">~{liveBudget} €</div>
                </div>
              </div>
            </div>
            
            {/* Main Tabs */}
            <div className="max-w-4xl mx-auto mt-6 flex gap-1 overflow-x-auto pb-1">
              {[
                { id: 'itinerary', icon: 'fa-map', label: 'Itinerario' },
                { id: 'restaurants', icon: 'fa-utensils', label: 'Dónde Comer' },
                { id: 'notes', icon: 'fa-book', label: 'Guía & Transporte' }
              ].map(t => (
                <button 
                  key={t.id} 
                  onClick={() => setActiveTab(t.id)}
                  className={`px-5 py-2 rounded-t-lg font-medium whitespace-nowrap transition-colors ${activeTab === t.id ? 'bg-white text-azulejo-900' : 'bg-azulejo-600/50 hover:bg-azulejo-600 text-white'}`}
                >
                  <i className={`fa-solid ${t.icon} mr-2`}></i> {t.label}
                </button>
              ))}
            </div>
          </header>

          <main className="max-w-4xl mx-auto p-4 mt-4">
            
            {/* ITINERARY TAB */}
            {activeTab === 'itinerary' && (
              <div>
                {/* Day Tabs */}
                <div className="flex gap-2 overflow-x-auto pb-4 mb-4 border-b border-gray-200 hide-scrollbar">
                  {DAYS.map((day, i) => (
                    <button 
                      key={day} 
                      onClick={() => setActiveDay(day)}
                      className={`px-4 py-2 rounded-full text-sm font-bold whitespace-nowrap transition-shadow ${activeDay === day ? 'bg-terra-500 text-white shadow-md' : 'bg-gray-200 text-gray-600 hover:bg-gray-300'}`}
                    >
                      {['Viernes 4', 'Sábado 5', 'Domingo 6', 'Lunes 7', 'Martes 8'][i]}
                    </button>
                  ))}
                </div>

                {/* Timeline */}
                <div className="space-y-4">
                  <div className="text-sm font-semibold text-gray-500 mb-4 px-2 uppercase tracking-widest">{activeDay}</div>
                  
                  {itinerary.filter(i => i.day === activeDay).map((item, index, arr) => (
                    <TimelineCard 
                      key={item.id} 
                      item={item} 
                      index={index} 
                      isFirst={index === 0} 
                      isLast={index === arr.length - 1} 
                      onMoveUp={(idx) => handleMove(idx, 'up')}
                      onMoveDown={(idx) => handleMove(idx, 'down')}
                      onEdit={(itm) => { setEditingItem('edit'); setEditForm(itm); }}
                    />
                  ))}

                  <button 
                    onClick={() => { setEditingItem('add'); setEditForm({ hora: '12:00', actividad: '', zona: '', transporte: '-', detalle: '', coste: '0€', comida: '-', type: 'default' }); }}
                    className="w-full py-4 border-2 border-dashed border-gray-300 rounded-xl text-gray-500 hover:border-terra-500 hover:text-terra-600 transition-colors font-medium"
                  >
                    <i className="fa-solid fa-plus mr-2"></i> Añadir Parada
                  </button>
                </div>
              </div>
            )}

            {/* RESTAURANTS TAB */}
            {activeTab === 'restaurants' && (
              <div className="space-y-6 card-enter">
                <div className="bg-white p-5 rounded-xl shadow-sm border border-gray-200">
                  <h2 className="text-lg font-bold text-gray-800 mb-4"><i className="fa-solid fa-filter text-terra-500 mr-2"></i> Filtra opciones gastronómicas</h2>
                  <div className="grid grid-cols-1 md:grid-cols-3 gap-4">
                    <select className="p-2 border rounded-md w-full bg-gray-50" value={resFilters.zona} onChange={e => setResFilters({...resFilters, zona: e.target.value})}>
                      <option value="">Todas las zonas</option>
                      {zonas.map(z => <option key={z} value={z}>{z}</option>)}
                    </select>
                    <select className="p-2 border rounded-md w-full bg-gray-50" value={resFilters.momento} onChange={e => setResFilters({...resFilters, momento: e.target.value})}>
                      <option value="">Cualquier momento</option>
                      {momentos.map(m => <option key={m} value={m}>{m}</option>)}
                    </select>
                    <select className="p-2 border rounded-md w-full bg-gray-50" value={resFilters.tipo} onChange={e => setResFilters({...resFilters, tipo: e.target.value})}>
                      <option value="">Cualquier tipo de comida</option>
                      {tipos.map(t => <option key={t} value={t}>{t}</option>)}
                    </select>
                  </div>
                </div>

                <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
                  {filteredRestaurants.map((r, i) => (
                    <div key={i} className="bg-white p-4 rounded-xl shadow-sm border border-gray-100 hover:shadow-md transition-shadow">
                      <div className="flex justify-between items-start mb-2">
                        <h3 className="font-bold text-lg text-azulejo-900">
                          {r.nombre} 
                          <a href={getMapsUrl(r.nombre)} target="_blank" className="ml-2 text-azulejo-500 hover:text-azulejo-900"><i className="fa-solid fa-map-location-dot"></i></a>
                        </h3>
                        <span className="text-xs font-semibold bg-gray-100 px-2 py-1 rounded text-gray-600 whitespace-nowrap">{r.precio}</span>
                      </div>
                      <p className="text-sm font-medium text-gray-500 mb-2">{r.tipo} • {r.zona}</p>
                      <p className="text-sm text-gray-700 bg-orange-50 p-2 rounded"><i className="fa-solid fa-star text-orange-400 mr-1 text-xs"></i> {r.quePedir}</p>
                    </div>
                  ))}
                  {filteredRestaurants.length === 0 && (
                    <p className="text-gray-500 col-span-2 text-center py-8">No hay opciones para estos filtros.</p>
                  )}
                </div>
              </div>
            )}

            {/* NOTES & TRANSPORT TAB */}
            {activeTab === 'notes' && (
              <div className="space-y-6 card-enter">
                
                {/* Metros */}
                <section className="bg-white p-6 rounded-xl shadow-sm border border-gray-200">
                  <h2 className="text-xl font-bold text-gray-800 mb-4"><i className="fa-solid fa-train-subway text-azulejo-600 mr-2"></i> Líneas de Metro que vais a usar</h2>
                  <div className="space-y-3 mb-4">
                    {notasData.lineas.map((l, i) => (
                      <div key={i} className="flex items-start gap-3">
                        <div className={`w-4 h-4 rounded-full mt-1 shrink-0 ${l.color}`}></div>
                        <div>
                          <strong className="text-gray-900 block">{l.nombre}</strong>
                          <span className="text-gray-600 text-sm">{l.desc}</span>
                        </div>
                      </div>
                    ))}
                  </div>
                  <div className="bg-yellow-50 border-l-4 border-yellow-400 p-3 text-sm text-yellow-800">
                    <strong>Transbordo clave:</strong> {notasData.transbordo}
                  </div>
                </section>

                {/* Viva Viagem */}
                <section className="bg-white p-6 rounded-xl shadow-sm border border-gray-200">
                  <h2 className="text-xl font-bold text-gray-800 mb-4"><i className="fa-solid fa-ticket text-terra-500 mr-2"></i> Cómo comprar el pase Navegante 24h</h2>
                  <ol className="list-decimal list-outside ml-5 space-y-2 text-gray-700 text-sm">
                    {notasData.maquina.map((paso, i) => (
                      <li key={i} className="pl-1">{paso}</li>
                    ))}
                  </ol>
                  <div className="mt-4 bg-gray-100 p-3 rounded text-sm text-gray-600">
                    <strong>Alternativa:</strong> {notasData.alternativa}
                  </div>
                </section>

                {/* General Notes */}
                <section className="bg-white p-6 rounded-xl shadow-sm border border-gray-200">
                  <h2 className="text-xl font-bold text-gray-800 mb-4"><i className="fa-solid fa-circle-info text-azulejo-600 mr-2"></i> Notas Prácticas Generales</h2>
                  <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
                    {notasData.general.map((n, i) => (
                      <div key={i} className="bg-gray-50 p-3 rounded-lg border border-gray-100">
                        <h4 className="font-bold text-gray-800 text-sm mb-1">{n.k}</h4>
                        <p className="text-sm text-gray-600">{n.v}</p>
                      </div>
                    ))}
                  </div>
                </section>
              </div>
            )}
          </main>

          {/* EDIT MODAL */}
          {editingItem && (
            <div className="fixed inset-0 bg-black/60 z-50 flex items-center justify-center p-4">
              <div className="bg-white rounded-xl shadow-xl w-full max-w-lg overflow-hidden flex flex-col max-h-[90vh]">
                <div className="bg-azulejo-900 text-white p-4 font-bold flex justify-between items-center">
                  {editingItem === 'edit' ? 'Editar Parada' : 'Nueva Parada'}
                  <button onClick={() => setEditingItem(null)} className="text-white hover:text-gray-300"><i className="fa-solid fa-xmark"></i></button>
                </div>
                <div className="p-5 overflow-y-auto space-y-4">
                  <div className="grid grid-cols-2 gap-4">
                    <div>
                      <label className="block text-xs font-bold text-gray-700 mb-1">Hora</label>
                      <input type="text" className="w-full border rounded p-2 text-sm" value={editForm.hora} onChange={e => setEditForm({...editForm, hora: e.target.value})} />
                    </div>
                    <div>
                      <label className="block text-xs font-bold text-gray-700 mb-1">Color / Tipo</label>
                      <select className="w-full border rounded p-2 text-sm" value={editForm.type} onChange={e => setEditForm({...editForm, type: e.target.value})}>
                        <option value="default">Normal (Blanco)</option>
                        <option value="free">Gratis (Verde)</option>
                        <option value="optional">Opcional (Naranja)</option>
                        <option value="special">Especial (Rosa)</option>
                      </select>
                    </div>
                  </div>
                  <div>
                    <label className="block text-xs font-bold text-gray-700 mb-1">Actividad / Lugar</label>
                    <input type="text" className="w-full border rounded p-2 text-sm" value={editForm.actividad} onChange={e => setEditForm({...editForm, actividad: e.target.value})} />
                  </div>
                  <div>
                    <label className="block text-xs font-bold text-gray-700 mb-1">Zona</label>
                    <input type="text" className="w-full border rounded p-2 text-sm" value={editForm.zona} onChange={e => setEditForm({...editForm, zona: e.target.value})} />
                  </div>
                  <div>
                    <label className="block text-xs font-bold text-gray-700 mb-1">Detalle</label>
                    <textarea className="w-full border rounded p-2 text-sm" rows="2" value={editForm.detalle} onChange={e => setEditForm({...editForm, detalle: e.target.value})}></textarea>
                  </div>
                  <div>
                    <label className="block text-xs font-bold text-gray-700 mb-1">Cómo llegar (Transporte)</label>
                    <textarea className="w-full border rounded p-2 text-sm" rows="2" value={editForm.transporte} onChange={e => setEditForm({...editForm, transporte: e.target.value})}></textarea>
                  </div>
                  <div className="grid grid-cols-2 gap-4">
                    <div>
                      <label className="block text-xs font-bold text-gray-700 mb-1">Coste</label>
                      <input type="text" className="w-full border rounded p-2 text-sm" value={editForm.coste} onChange={e => setEditForm({...editForm, coste: e.target.value})} />
                    </div>
                    <div>
                      <label className="block text-xs font-bold text-gray-700 mb-1">Dónde comer (separar con "|")</label>
                      <input type="text" className="w-full border rounded p-2 text-sm" value={editForm.comida} onChange={e => setEditForm({...editForm, comida: e.target.value})} />
                    </div>
                  </div>
                </div>
                <div className="p-4 bg-gray-50 border-t flex justify-end gap-3">
                  <button onClick={() => setEditingItem(null)} className="px-4 py-2 text-gray-600 hover:text-gray-900 font-medium">Cancelar</button>
                  <button onClick={handleSaveEdit} className="px-4 py-2 bg-terra-500 hover:bg-terra-600 text-white font-bold rounded-lg shadow-sm">Guardar</button>
                </div>
              </div>
            </div>
          )}
        </div>
      );
    }

    const root = ReactDOM.createRoot(document.getElementById('root'));
    root.render(<App />);
  </script>
</body>
</html>
