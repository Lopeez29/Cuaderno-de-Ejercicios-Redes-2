# Cuaderno-de-Ejercicios-Redes-2


# EJERCICIOS - TEMAS 4, 5 y 6

1. **Explicar sobre el siguiente grafo de red los conceptos de circuito virtual entre el nodo 10 y el 6, y datagrama entre el nodo 3 y el 6.**  
   Asumir arcos bidireccionales.


### a) Circuito virtual 10 → 6  
| Nodo | VCI in | VCI out | Próximo salto |
|------|-------|--------|---------------|
| 10   | —     | **33** | 5 |
| 5    | 33    | **45** | 2 |
| 2    | 45    | **52** | 4 |
| 4    | 52    | **07** | 6 |
| 6    | 07    | —      | destino |

1. **SETUP:** 10 envía un `SETUP` hasta 6; cada nodo reserva recursos y asigna su VCI.  
2. **Datos:** los paquetes llevan solo la etiqueta local (33 → 45 → 52 → 07).  
3. **TEARDOWN:** un mensaje de cierre libera las tablas en orden inverso.  


---

### b) Datagrama 3 → 6  
Ruta inicial (mínimos saltos): **3 → 10 → 5 → 2 → 4 → 6**

| Salto | Nodo | Próximo salto |
|-------|------|---------------|
| 1 | 3  | 10 |
| 2 | 10 | 5  |
| 3 | 5  | 2  |
| 4 | 2  | 4  |
| 5 | 4  | 6 |

Cada datagrama consulta la tabla en cada salto; si la red cambia, la siguiente trama puede tomar otra ruta.


---


2. **Partiendo de la anterior red, generar las tablas de cada uno de los nodos de un circuito virtual entre los nodos 3 y 4.**  
   Tener en cuenta que los CV creados del anterior ejercicio siguen presentes.  
   Asumir arcos bidireccionales.

3. **Partiendo de la anterior red, generar las tablas de cada uno de los nodos de un circuito virtual entre los nodos 3 y 4.**  
   Tener en cuenta que los CV creados del anterior ejercicio siguen presentes.  
   Asumir arcos bidireccionales.

4. **Aplicar los algoritmos indicados en los siguientes grafos, tomando como partida el nodo 5.**  
   Indicar iteración a iteración lo que ocurre. Asumir arcos bidireccionales.  
   a) Algoritmo de Dijkstra.  
   b) Algoritmo de inundación hasta el nodo 6. Contar el total de paquetes generados.

5. **Diseñar las tablas de rutado jerárquico de la siguiente red.**

6. **En un sistema con las siguientes características, indicar las máscaras utilizadas, la primera y última dirección de los equipos, y los elementos/dispositivos necesarios:**
   - 7900 profesionales con datos sensibles.
   - 54 subredes para sensorización (100 sensores por subred).
   - 1290 tomas Ethernet.
   - 75000 clientes externos que deberán tener acceso a Internet por wifi.
   - Switches de máximo 24 bocas.

7. **Calcular la eficiencia de un sistema basado en UDP/IP desde un mensaje de la capa de aplicación de 1000000 bytes, sabiendo que la longitud máxima del campo de datos es:**
   - UDP: 65527 bytes. Cabecera de 8 bytes.
   - IP: 65535 bytes. Cabecera de 4 bytes.
   - Ethernet: 1500 bytes. Cabecera de 8 bytes.

8. **Con los datos del ejercicio anterior, calcular la eficiencia de un sistema RTP/UDP, con cabecera RTP de 12 bytes y 65535 bytes de datos.**

9. **Realizar el pseudocódigo de un cliente y servidor UDP/TCP que devuelva la hora de una región determinada.**

10. **Indicar el procedimiento a seguir mediante el protocolo DNS para obtener la dirección IP de la siguiente URL:** `iuj.ac.jp`

11. **Indicar el intercambio de mensajes completo que se produce desde que se introduce la URL www.twitch.tv hasta que empieza a visualizarse una transmisión en directo.**
