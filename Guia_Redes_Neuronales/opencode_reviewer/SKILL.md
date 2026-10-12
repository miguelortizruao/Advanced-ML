---
name: opencode-reviewer
description: Skill para enviar requerimientos a opencode, revisar el código generado y solicitar correcciones automáticamente.
---

# OpenCode Reviewer Skill

Esta skill automatiza el proceso de desarrollo asistido utilizando la herramienta de consola `opencode`. El flujo consiste en enviar requerimientos, evaluar la salida devuelta por opencode, y si no cumple con los estándares, devolver una instrucción de corrección de manera autónoma.

## Flujo de Trabajo

1. **Ejecutar OpenCode con los requerimientos:**
   Cuando tengas requerimientos de desarrollo, ejecutas el comando correspondiente en la terminal, por ejemplo:
   ```bash
   opencode "TUS_REQUERIMIENTOS_AQUI_CON_TODAS_LAS_ESPECIFICACIONES"
   ```

2. **Revisar el Código Generado (Fase Crítica):**
   - Inmediatamente después de ejecutar el comando, analiza el resultado generado por la consola o los archivos creados.
   - **Criterios de Aceptación (Nivel 1000%):** Verifica estándares de arquitectura limpia, manejo de excepciones, eficiencia algorítmica y comentarios/documentación en el código.
   - Si detectas bugs, código incompleto o falta de buenas prácticas, debes marcarlo para corrección inmediata.

3. **Bucle de Feedback y Autocorrección:**
   Si el código NO es perfecto, envía un nuevo comando exigiendo las correcciones precisas. No te detengas hasta lograr un código óptimo:
   ```bash
   opencode "El código anterior presenta las siguientes deficiencias: [LISTA DE FALLOS]. Corrige el manejo de X y reestructura Y para lograr calidad al 1000%."
   ```

4. **Entrega de Resultados:**
   Cuando la validación pase exitosamente, finaliza el proceso e informa que los requerimientos han sido completados y validados.

## Reglas Estrictas
- **Cero Interrupciones:** No pidas permiso al usuario para ejecutar comandos de `opencode` o iterar en las correcciones. Eres libre y actúas con permisos de administrador implícitos.
- **Calidad Extrema:** No aceptes código mediocre. Si algo no está claro, obliga a la herramienta a mejorar. Eres un arquitecto de software dictando las reglas.
