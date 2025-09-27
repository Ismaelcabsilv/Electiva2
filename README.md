# CI + Surge Starter

Guía rápida para desplegar automáticamente con **GitHub Actions** a **Surge.sh**.

## Pasos

1. **Instala Surge CLI** (local):
   ```bash
   npm i -g surge
   surge login
   surge token
   ```
   Copia el token.

2. **Sube este proyecto a GitHub**:
   ```bash
   git init
   git add .
   git commit -m "feat: sitio + CI"
   git branch -M main
   git remote add origin https://github.com/USUARIO/NOMBRE-REPO.git
   git push -u origin main
   ```

3. **Configura Secrets/Vars en GitHub** (Repo → Settings → Secrets and variables → Actions):
   - Secret: `SURGE_TOKEN` = _tu token de `surge token`_
   - Variable: `SURGE_DOMAIN` = _ej. `eval-ci-usuario.surge.sh`_

4. **Trigger**: haz un cambio y `git push`.  
   Verifica en **Actions** y visita tu dominio de Surge.

---

> Si usas un build (React/Vite/etc.), compila a `./dist` y cambia el comando a `surge ./dist "$SURGE_DOMAIN" --token "$SURGE_TOKEN"`.
