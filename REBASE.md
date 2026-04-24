# Documentación de Rebase

## Estado inicial
El historial de la rama principal contaba con 3 commits consecutivos cuyos mensajes ("Arreglos", "Cambios", "Actualización de cosas") no aportan valor ni contexto sobre los cambios que se han hecho.

## Proceso de limpieza
1. **Comando:** Ejecuto `git rebase -i HEAD~3` para evaluar los últimos 3 commits.
2. **Acción (Squash):** En el editor, mantengo el primer commit con `pick` (o `reword`) y se marca a los dos siguientes con `squash`. Esto le dice a Git que unirá los cambios de los tres commits en uno solo.
3. **Acción (Reword):** En el siguiente paso del editor, se borran los mensajes antiguos y se escribe un nuevo mensaje unificado y descriptivo.

## Sincronización remota
Sabiendo que el rebase reescribe el historial (cambiando los hashes de los commits), la rama local se queda desincronizada de la remota. Para solucionar esto y aplicar la limpieza en GitHub, utilizo `git push origin main --force`.
