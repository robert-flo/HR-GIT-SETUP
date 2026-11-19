# AGENTS.md — HR-GIT-SETUP

Meta-repo **HR-GIT-SETUP** del trío PM/WK/RV para el plugin **git-setup.nvim** en Cursor y agy (el código del plugin vive en `pj-domina-rf-git-setup.nvim`). Si sos un agente: si no existe `.agents/reglas/`, corré `./pj` antes de nada.

## Qué hay acá
- `proyecto.yml`: los datos del proyecto (repos, specs en orden, notas). Lo llenás vos.
- `onboarding.yml`: lo propio del proyecto para el PM, el WK y el RV (misión, lo que no tocan, primeros pasos, cómo se prueba, qué exige el RV). Lo escribe `./pj onboard`.
- Todo lo demás (reglas, plantillas, skills, scripts) lo trae `./pj` desde `robert-flo/pj-template` al SHA de `template_ref`, en `.pj/`, y genera `.agents/` y `.cursor/`. Nada de eso se versiona ni se edita a mano.

## Arquitectura
Proyecto multi-repo compuesto por 5 repositorios:
- `pj-domina-rf-git-setup.nvim`: código del plugin de Neovim (ventana flotante `nvim_open_win` con buffer de terminal `termopen` que corre el `git-pull` de la CLI `git-setup` y muestra una notificación según el código de salida: verde si salió bien, roja si no, dejando la ventana abierta para leer el error).
- `pj-domina-rf-git-setup`: CLI `git-setup`.
- `pj-domina-rf-git-setup-arch`: empaquetado Arch de la CLI `git-setup`.
- `rvim`: configuración de Neovim de Roberto donde se integra y prueba el plugin.
- `2KAbhishek/octohub.nvim`: referencia externa de solo lectura para patrones y estructura de plugins de Neovim (sin push a upstream ni PRs).
