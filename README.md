# <h1 align="center">Trabajo UML Entornos de Desarrollo</h1>

## Índice
- [1. Explicación diagrama de uso](#1-explicación-diagrama-de-uso)
- [2. Explicación diagrama de clase](#2-explicación-diagrama-de-clase)
  - [Clase Persona](#clase-persona)
  - [Clase Jugador](#clase-jugador)
  - [Clase Manager](#clase-manager)
  - [Clase Entrenador](#clase-entrenador)
  - [Clase PropietarioEquipo](#clase-propietarioequipo)
  - [Clase Contrato](#clase-contrato)
  - [Clase Equipo](#clase-equipo)
  - [Clase Administrador](#clase-administrador)
  - [Clase Competición](#clase-competición)
  - [Clase Partida](#clase-partida)
  - [Clase Juego](#clase-juego)
  - [Clase Categoría](#clase-categoría)
  - [Clase Árbitro](#clase-árbitro)
  - [Clase Espectador](#clase-espectador)
  ---

## 1. Explicación diagrama de uso
En el análisis del sistema se han identificado los siguientes actores:
  1. Jugador
  2. Mánager
  3. Entrenador
  4. Propietario de equipo
  5. Administrador
  6. Árbitro
  7. Medio de retransmisión
  8. Espectador

Todos los actores tienen acceso a la consulta de información relacionada con jugadores, equipos, resultados y clasificaciones.
- El jugador participa en entrenamientos y competiciones.
- El mánager representa al jugador, busca equipos, facilita documentación y gestiona la firma de contratos.
- El entrenador planifica y dirige los entrenamientos de los jugadores.
- El administrador gestiona los derechos de retransmisión, organiza torneos y valida, junto a su equipo, las inscripciones de jugadores y equipos, asegurando que se cumplan los requisitos de participación.
- Los árbitros registran los resultados de las partidas y colaboran en la actualización de tablas de clasificación.
- Los medios de retransmisión, una vez autorizados, emiten las competiciones al público y permiten el acceso a la información.
- El espectador consume el contenido transmitido y accede a los datos de competición.
- El propietario de equipo organiza entrenamientos, recluta nuevos jugadores en coordinación con los mánagers, y verifica que el equipo cumpla los requisitos necesarios para participar en los campeonatos.

## 2. Explicación diagrama de clase

Este diagrama de clases representa la estructura del sistema de gestión de competiciones de eSports. Muestra las entidades principales, sus atributos, métodos y las relaciones entre ellas, manteniendo coherencia con los casos de uso previamente descritos.

### Clase Persona

Clase base que abstrae atributos y comportamientos comunes de todos los actores del sistema.

**Atributos**:  
- id  
- nombre  
- correoElectronico  

**Métodos**:  
- consultarEquipos()  
- consultarJugador()  
- consultarResultados()  
- consultarClasificaciones()  

**Herencia**: De esta clase derivan Jugador, Manager, Entrenador, Administrador, PropietarioEquipo, Árbitro y Espectador.

---

### Clase Jugador

Representa a los jugadores que participan en las competiciones.

**Atributos**:  
- nacionalidad  
- tipoJuego  
- posición  
- elo  
- equipoActual  

**Métodos**:  
- jugarPartida()  
- entrenar()  

---

### Clase Manager

Representa a los representantes o agentes de jugadores.

**Atributos**:  
- jugadoresRepresentados: List<Jugador>  

**Métodos**:  
- representarJugador()  

---

### Clase Entrenador

Encargado de la preparación de los jugadores de un equipo.

**Atributos**:  
- equipoActual  

**Métodos**:  
- entrenarJugador()  

---

### Clase PropietarioEquipo

Responsable de la gestión y formación del equipo.

**Atributos**:  
- equipoActual  

**Métodos**:  
- reclutarJugador()  

---

### Clase Contrato

Registra los acuerdos entre jugadores y equipos.

**Atributos**:  
- fechaContrato  
- salario  

**Métodos**:  
- firmarContrato()  

---

### Clase Equipo

Representa un equipo participante en competiciones.

**Atributos**:  
- tipoJuego  
- división  

**Métodos**:  
- agregarMiembro()  
- eliminarMiembro()  
- listaMiembros()  

---

### Clase Administrador

Gestiona los torneos y derechos de transmisión.

**Métodos**:  
- crearTorneo()  
- gestionarDerechosTransmision()  

---

### Clase Competición

Agrupa partidas dentro de un mismo torneo o evento.

**Atributos**:  
- nombreCompeticion  
- categoría  
- equipos: List<Equipo>  

**Métodos**:  
- iniciarCompeticion()  
- finalizarCompeticion()  

---

### Clase Partida

Representa una partida dentro de una competición.

**Atributos**:  
- equipos: List<Equipo>  

**Métodos**:  
- empezarPartida()  
- finalizarPartida()  

---

### Clase Juego

Define los juegos disponibles en las competiciones.

**Atributos**:  
- idJuego  
- nombre  

---

### Clase Categoría

Clasifica las competiciones.

**Atributos**:  
- idCategoria  
- tipoCompeticion  

---

### Clase Árbitro

Encargado de validar y registrar los resultados de las partidas.

**Métodos**:  
- registrarResultados()  

---

### Clase Espectador

Usuario que consume las transmisiones del sistema.

**Métodos**:  
- verTransmision()  
