# QA Workflow - Este Proyecto

## Daily Workflow

1. **Revisar PRs abiertos**
```bash
git fetch origin
git log origin/main..origin/develop --oneline  # Ver qué hay por mergear
```

2. **Testear PR específico**
```bash
# Bajar la rama a un entorno local de revisión
git checkout -b review/feature-name origin/feature-name
npm install
npm start
```

3. **Dejar feedback en GitHub**
   1. Ir a la pestaña "Files changed".
   2. Comentar en líneas específicas si hay errores.
   3. Escribir descripción general del testing ejecutado.
   4. Marcar como **Approve** (Aprobar) o **Request changes** (Solicitar cambios).

4. **Después del merge**
```bash
git checkout main
git pull origin main  # Testear versión final en producción
```

5. **Si encuentras un bug**
   - **Opción A:** Crear issue en GitHub con pasos para reproducir.
   - **Opción B:** Usar git bisect para encontrar cuándo fue introducido.

#### Herramientas Usadas
- Chrome DevTools (F12)
- WAVE Chrome Extension
- Color Contrast Analyzer
- W3C Validator
- Git & GitHub
