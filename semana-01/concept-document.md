# Documento de Concepto: Estación Ámbar
**Curso:** TS359 — Ingeniería de Software II (UVG Altiplano)  
**Responsable de Documentación:** Tatiana Ivonne López Escobar

---

### 1. Nombre del Juego
**Estación Ámbar**

### 2. Género
Terror y supervivencia en primera persona (*First-Person Survival Horror*) con enfoque en sigilo, exploración modular y resolución de tareas bajo presión.

### 3. Sinopsis
Clara Torres es una joven técnica de mantenimiento que acepta un trabajo nocturno de emergencia en la "Estación Ámbar", un complejo subterráneo de entretenimiento infantil que lleva años clausurado. Lo que parecía un simple turno para estabilizar los generadores antes de la demolición se convierte en una lucha por sobrevivir cuando los antiguos autómatas de la instalación se encienden misteriosamente. Sin armas, armada solo con su tableta de diagnóstico y sus herramientas, Clara debe reparar los tres sectores principales de la estación para abrir las salidas de emergencia antes de que las máquinas la encuentren.

### 4. Mecánica (Game Loop)
El núcleo de la jugabilidad se define en un ciclo constante de tensión y resolución:
1.  **Exploración:** El jugador recorre pasillos y salas cerradas buscando herramientas o piezas específicas.
2.  **Reparación (Tareas):** Interactuar con paneles eléctricos, reiniciar servidores o calibrar válvulas mediante minijuegos rápidos.
3.  **Recolección:** Encontrar fusibles, baterías y tarjetas de acceso necesarias para desbloquear nuevas áreas.
4.  **Sigilo y Evasión:** Escuchar los pasos de los autómatas. Si uno se acerca, el jugador debe apagar su linterna, ocultarse bajo mesas o dentro de armarios, y controlar el ruido de sus movimientos.
5.  **Progreso:** Al completar las tareas de un sector, se desbloquea el acceso al siguiente hasta culminar el turno de escape.

### 5. Personaje Principal
*   **Nombre:** Clara Torres
*   **Apariencia:** 23 años, viste un overol de trabajo azul oscuro con parches reflectantes desgastados, cinturón de herramientas pesado y una linterna de cabeza recargable. Lleva una tableta industrial de diagnóstico sujeta al brazo.
*   **Habilidad 1 — Escáner de Frecuencia:** Clara puede usar su tableta de mantenimiento para rastrear interferencias electromagnéticas a través de las paredes, lo que le permite detectar la posición aproximada de un autómata cercano. *Limitación:* Consume mucha batería de la tableta.
*   **Habilidad 2 — Paso Amortiguado:** Debido a su conocimiento del calzado de seguridad y del entorno, Clara puede realizar un desplazamiento rápido en cuclillas que silencia por completo sus pasos durante 5 segundos. *Limitación:* Requiere un tiempo de enfriamiento (cooldown) antes de volver a usarse.

### 6. Niveles (Zonas)
El juego se compone de un diseño de niveles modular e interconectado por pasillos para optimizar el rendimiento y el diseño:
*   **Nivel 1: Sala de Espectáculos:** Zona amplia con el escenario principal. Aquí yacen los autómatas inicialmente apagados. Es el primer contacto del jugador con la atmósfera y las mecánicas básicas de reparación de luces y audio.
*   **Nivel 2: Taller de Reparación:** Un laberinto de mesas de trabajo, estanterías industriales y piezas de repuesto. Las tareas mecánicas son complejas, hay menos espacios abiertos y las rutas de escape son más estrechas.
*   **Nivel 3: Subsuelo / Sala de Máquinas:** El corazón de la estación. Oscuro, inundado de vapor ruidoso que dificulta escuchar a los autómatas, y con pasillos claustrofóbicos. Es la zona final donde la agresividad de la IA está al máximo.

### 7. Elemento de Inteligencia Artificial (IA)
Los autómatas contarán con un sistema de IA basado en una **Máquina de Estados Finitos (FSM)**. Los comportamientos principales serán:
*   *Patrulla:* El autómata recorre puntos predefinidos del nivel.
*   *Alerta/Investigación:* Si el jugador corre, tira un objeto o usa la linterna cerca, el autómata entra en estado de alerta y camina hacia el origen del ruido/luz.
*   *Persecución:* Si detecta visualmente al jugador, inicia una persecución activa y veloz.
*   *Dificultad Escalar:* Este sistema se ajustará dinámicamente mediante variables (velocidad de traslación, rango de audición y tiempo de reacción) para estructurar los **4 niveles de dificultad** del juego.

### 8. Motor de Desarrollo
Se utilizará **Unity** o **Godot Engine** (versión gratuita), aprovechando su excelente soporte para físicas de entornos cerrados en 3D y su robusto sistema de navegación (NavMesh) para la IA de los autómatas.

### 9. Público Objetivo
Jugadores jóvenes de entre 16 y 30 años, entusiastas de los géneros de terror indie, sigilo y supervivencia en primera persona, y seguidores de títulos como *Five Nights at Freddy's: Sister Location*, *Amnesia: The Dark Descent* y *Alien: Isolation*.

### 10. Viabilidad (20 semanas, 5 personas, sin presupuesto)
El proyecto es altamente viable bajo estas condiciones gracias a las siguientes decisiones de diseño:
*   **Entornos Modulares:** Al conectar salas cerradas mediante pasillos estrechos, se reduce drásticamente el tiempo de modelado 3D y texturizado en comparación con un mundo abierto.
*   **Lógica de IA Simple:** Al usar una Máquina de Estados Finitos (FSM) no se requiere entrenamiento de modelos complejos ni algoritmos de Machine Learning costosos en procesamiento.
*   **Estrategia de Assets:** Se utilizarán modelos 3D y efectos de sonido de uso libre con licencia comercial/académica gratuita para acelerar el desarrollo del entorno.

### 11. Riesgos y Mitigación
*   **Riesgo 1: Sobrediseño (Scope Creep):** Intentar añadir demasiados enemigos o zonas mecánicas complejas que consuman el tiempo de desarrollo.
    *   *Mitigación:* Definir un Producto Mínimo Viable (MVP) compuesto por 1 solo enemigo funcional y 1 zona terminada para la semana 10 antes de expandir.
*   **Riesgo 2: Falta de cohesión en el apartado artístico:** Al usar assets gratuitos de distintas fuentes, el juego podría verse visualmente inconsistente.
    *   *Mitigación:* Aplicar un filtro de post-procesamiento visual homogéneo (como aberración cromática, grano de película y un esquema de iluminación oscura/neblina de color ámbar) para unificar la estética de todos los recursos.

### 12. Retroalimentación
*(Espacio reservado para comentarios, evaluaciones y sugerencias del docente de Ingeniería de Software II y del equipo colaborador de Programación de Videojuegos).*