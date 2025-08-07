# Laboratorio de Técnicas de Ingeniería de Prompt
Técnicas para escribir los prompts de un Asistente de IA para Recursos Humanos que analiza la transcripción de una entrevista de trabajo. 

![Entrevista](interview.png)

## Técnica 1. Prompting de menos a más
<ins>***Least-To-Most Prompting***</ins>: Descompone un problema complejo en subproblemas más simples y los resuelve secuencialmente.

:hand: `Recuerda subir el archivo "interview-transcript.txt"`
```
Contexto:
El archivo "interview-transcript.txt" contiene la transcripción de una entrevista de trabajo realizada por un Analista de Selección en una compañía de desarrollo de software a un Arquitecto Java para determinar si es el candidato apropiado para ser asignado a un proyecto.

Consideraciones:
El factor crítico que se debe tener en cuenta es que el candidato se va a integrar a un equipo que pone demasiado énfasis en el uso de metodologías ágiles.

Prompt:
1. Inicialmente presenta un corto resumen de la experiencia del candidato en arquitectura de software dentro de proyectos que hagan énfasis en el uso de metodologías ágiles.
2. Con base en los resultados de este resumen presenta los pros y los contras para contratar al candidato e integrarlo en un equipo que tiene mucha adherencia a metodologías ágiles.
3. Teniendo esto en cuenta ¿Qué tan prudente es contratar al candidato en estas condiciones?
```

## Técnica 2. Prompting de auto-pregunta
<ins>***Self-Ask Prompting***</ins>: Permite al LLM razonar explícitamente y descomponer la pregunta en subpreguntas de seguimiento.

```
Contexto:
Se va a realizar una entrevista de trabajo por parte de un Analista de Selección en una compañía de desarrollo software a un Arquitecto Java para determinar si es el candidato apropiado para ser asignado a un proyecto.

Consideraciones:
Cómo dedo orientar la entrevista si el candidato se va a integrar a un equipo que pone demasiado énfasis en el uso de metodologías ágiles.

Prompt:
¿Qué preguntas podrían hacerse para determinar si el candidato es apto para integrarse a un equipo que tiene mucha adherencia a metodologías ágiles?
```

**Posibles Respuesta:**
- ¿La idea que tiene el candidato del uso de metodologías ágiles es positiva o negativa? justifica la respuesta
- ¿Qué tanta  experiencia tiene el candidato en arquitectura de software y metodologías ágiles?
- ¿Cuáles son los pros y los contras para contratar al candidato e integrarlo en un equipo que tiene mucha adherencia a metodologías ágiles?
- ¿Consideras que es prudente contratar al candidato en estas condiciones?

## Técnica 3. Meta-prompting

<ins>***Meta-Prompting***</ins>: Utiliza un prompt general para guiar al LLM a reflexionar sobre su propio rendimiento y modificar sus instrucciones en consecuencia.

```
Contexto:
Se va a realizar una entrevista de trabajo por parte de un Analista de Selección en una compañía de desarrollo de software a un Arquitecto Java para determinar si es el candidato apropiado para ser asignado a un cliente “scrum lover”.

Consideraciones:
Se tienen dudas de qué criterios de evaluación usar y qué preguntas realizarle al candidato para que el cuestionario esté alineado con los criterios de evaluación.

Prompt:
Podrías redactar un prompt que sirva para encontrar los cinco criterios de evaluación más apropiados para un cliente “scrum lover” (mucha adherencia a esta metodología ágil) y luego redacta un cuestionario de diez preguntas que esté alineado con los criterios de evaluación que formulaste.

Define una escala Likert que permita calificar el nivel de cumplimento del criterio por parte del candidato, de tal forma que pueda ser usado posteriormente para otros candidatos.
```

## Técnica 4. Prompting de cadena de pensamiento

<ins>***Chain-of-Thought Prompting***</ins>: Divide una tarea o problema más grande en subtareas, y luego encadenamos estas subtareas, usando el resultado de una subtarea como entrada para la siguiente subtarea. Desarrolla capacidades de razonamiento sofisticado.

:hand: `Recuerda subir el archivo "interview-transcript.txt"`
```
Contexto:
El archivo "interview-transcript.txt" contiene la transcripción de una entrevista de trabajo realizada por un Analista de Selección en una compañía de desarrollo de software a un Arquitecto Java para determinar si es el candidato apropiado para ser asignado a un proyecto.

Consideraciones:
El archivo es bastante voluminoso y contiene mucha información en la que se muestra el orden en el que el entrevistador y el entrevistado se comunicaron.

Prompt:
Podrías resumir la entrevista enfatizando los tópicos del tema de arquitectura Java que se abordaron y cuál es la experiencia y el conocimiento que tiene el candidato de cada uno; presenta únicamente el resumen y ten en cuenta que luego el resumen será utilizado para continuar con el proceso de análisis del candidato. Genera la respuesta como un archivo *.txt descargable.
```

## Técnica 5. ReAct (Razonar & Actuar)

<ins>***ReAct (Reasoning & Acting)***</ins>: Combina el razonamiento con la toma de acciones, permitiendo al LLM actualizar planes de acción en función de información adicional recopilada.

:hand: `Recuerda subir el archivo "interview-transcript.txt"`
```
Contexto:
El archivo "interview-transcript.txt" contiene la transcripción de una entrevista de trabajo realizada por un Analista de Selección en una compañía de desarrollo de software a un Arquitecto Java para determinar si es el candidato apropiado para ser asignado a un proyecto.

Consideraciones:
Se contratará al candidato para un cliente de mucha adherencia a Scrum, con base en su entrevista ¿Cuáles pasos se deben tener en cuenta para su proceso de on-boarding?

Prompt:
Con base en la entrevista, qué frentes de la metodología Scrum debe fortalecer el candidato para ser contratado para un cliente de mucha adherencia a Scrum, ¿Cuáles pasos se deben tener en cuenta para su proceso de on-boarding? Define un plan de on-boarding para ser aplicado con el candidato de un mes de duración.
```

## Técnica 6 y 7. Razonamiento simbólico y PAL

<ins>***Symbolic Reasoning and PAL (Program-Aided LLM)***</ins>: Permite convertir el razonamiento en un programa que implica análisis de símbolos, colores, tipos de objetos, etc.

:hand: `Recuerda subir el archivo "interview-transcript.txt"`
```
Contexto:
El archivo "interview-transcript.txt" contiene la transcripción de una entrevista de trabajo realizada por un Analista de Selección en una compañía de desarrollo de software a un Arquitecto Java para determinar si es el candidato apropiado para ser asignado a un proyecto.

Consideraciones:
Se debe calificar porcentualmente la entrevista de este y otros candidatos considerando 3 dimensiones: scrum (50%), experiencia (30%) y herramientas (20%).


Prompt:
Con base en la entrevista, genera una tabla de calificación de la entrevista considerando tres dimensiones: scrum (50 puntos), experiencia (30 puntos) y herramientas (20 puntos), poniendo para cada dimensión la justificación de cada calificación.
```

## Técnica 8. Prompting iterative

<ins>***Iterative Prompting***</ins>: Asegura que las indicaciones sean contextuales, contengan ejemplos de entrenamiento (few-shot) y el historial de la conversación.

:hand: `Recuerda subir el archivo "interview-transcript.txt"`
```
Contexto:
El archivo "interview-transcript.txt" contiene la transcripción de una entrevista de trabajo realizada por un Analista de Selección en una compañía de desarrollo de software a un Arquitecto Java para determinar si es el candidato apropiado para ser asignado a un proyecto.

Consideraciones:
Se necesita una lista de la experiencia del candidato detallada, mostrando para cada caso el área de experiencia y el nivel (Alto / Medio Alto / Medio / Medio Bajo / Bajo).

Prompt:
Basándose exclusivamente en el archivo de trascripción de la entrevista, genera una tabla de experiencia detallada mostrando el nivel del candidato a un área específica; por ejemplo: 
- Pruebas : Alto.
- Microservicios : Medio Alto.
- Bases de Datos: Medio
```

## Técnica 9. Prompting secuencial

<ins>***Sequential Prompting***</ins>: Suele usar un pipeline para generar candidatos (elementos, componentes  o técnicas relevantes) y luego hacer un ranking (para determinar los mejores elementos o su orden), considerando que usar LLMs a gran escala es costoso.

:hand: `Recuerda subir el archivo "interview-transcript.txt"`
```
Contexto:
El archivo "interview-transcript.txt" contiene la transcripción de una entrevista de trabajo realizada por un Analista de Selección en una compañía de desarrollo de software a un Arquitecto Java para determinar si es el candidato apropiado para ser asignado a un proyecto.

Consideraciones:
Calcular la velocidad a la que habló el candidato en palabras por minuto.

Prompt:
Basándose exclusivamente en el archivo de trascripción de la entrevista, calcula la velocidad a la que habló el candidato en palabras por minuto con los dos siguientes métodos:

1. Totalizado: Multiplicar el tiempo total de la entrevista por el total de palabras que habló el candidato y dividir por el total de palabras que se hablaron en la entrevista (tanto el candidato como el entrevistador).

2. Por dialogo: Para cada dialogo del candidato contar las palabras y dividir por el tiempo extraído de la marca de tiempo del respectivo diálogo; finalmente promediar para todos los diálogos del candidato.

¿Cuál de los dos métodos es mejor?
```

## Técnica 10. Autoconsistencia

<ins>***Self-Consistency***</ins>: Genera múltiples caminos de razonamiento y selecciona el más consistente como respuesta final.

:hand: `Recuerda subir el archivo "interview-transcript.txt"`
```
Contexto:
El archivo "interview-transcript.txt" contiene la transcripción de una entrevista de trabajo realizada por un Analista de Selección en una compañía de desarrollo de software a un Arquitecto Java para determinar si es el candidato apropiado para ser asignado a un proyecto.

Consideraciones:
Dejar que el LLM defina cual es el mejor método para calcular la velocidad a la que habló el candidato en palabras por minuto.

Prompt:
Basándose exclusivamente en el archivo de trascripción de la entrevista, propón los métodos que se pueden usar para calcular la velocidad a la que habló el candidato en palabras por minuto.

Realiza el cálculo con cada uno de los métodos que propusiste y muestra los resultados

¿Cuál de los métodos es mejor?
```