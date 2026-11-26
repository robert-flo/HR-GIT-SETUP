# AGENTS.md — HR-GIT-SETUP

Meta-repo **HR-GIT-SETUP** del trío PM/WK/RV en Cursor y agy para gestionar y estandarizar las herramientas públicas de Roberto empaquetadas para Arch (nombres, CI y estrategias de publicación entre todos los dúos `fuente` + `*-arch`), incluyendo el ecosistema de **git-setup** y **git-setup.nvim**. Si sos un agente: si no existe `.agents/reglas/`, corré `./pj` antes de nada.

## Qué hay acá
- `proyecto.yml`: los datos del proyecto (repos, specs en orden, notas). Lo llenás vos.
- `onboarding.yml`: lo propio del proyecto para el PM, el WK y el RV (misión, lo que no tocan, primeros pasos, cómo se prueba, qué exige el RV). Lo escribe `./pj onboard`.
- Todo lo demás (reglas, plantillas, skills, scripts) lo trae `./pj` desde `robert-flo/pj-template` al SHA de `template_ref`, en `.pj/`, y genera `.agents/` y `.cursor/`. Nada de eso se versiona ni se edita a mano.

## Arquitectura
Proyecto multi-repo compuesto por 19 repositorios:

### Dúos de herramientas públicas empaquetadas para Arch (`fuente` + `*-arch`)
1. `pj-domina-rf-git-setup` + `pj-domina-rf-git-setup-arch`: CLI `git-setup` y su empaquetado Arch.
2. `pj-domina-rf-shared_dir` + `pj-domina-rf-shared_dir-arch`: herramienta compartida `shared_dir` y su empaquetado Arch.
3. `ravn-git-bare-clone` + `ravn-git-bare-clone-arch`: launcher/runtime modular de `ravn-git-bare-clone` y su paquete Arch Linux.
4. `ravn-sessionizer` + `ravn-sessionizer-arch`: sessionizer para `herdr` y su paquete Arch.
5. `ravn-trio` + `ravn-trio-arch`: trío PM/WK/RV local en `herdr` (`pj-trio`) y su paquete Arch.
6. `ravn-home-common` + `ravn-home-common-arch`: capa común de `$HOME` para la workstation ravn y su PKGBUILD Arch Linux.
7. `ravn-home-niri` + `ravn-home-niri-arch`: capa `niri` para la workstation ravn y su PKGBUILD/empaquetado Arch Linux.
8. `ravn-webapps` + `ravn-webapps-arch`: launchers `.desktop`, íconos y runtime para webapps en RaVN y su empaquetado Arch / release automation.

### Ecosistema Neovim y referencia
- `pj-domina-rf-git-setup.nvim`: código del plugin de Neovim (ventana flotante `nvim_open_win` con buffer de terminal `termopen` que corre el `git-pull` de la CLI `git-setup` y muestra una notificación según el código de salida: verde si salió bien, roja si no, dejando la ventana abierta para leer el error).
- `rvim`: configuración de Neovim de Roberto donde se integra y prueba el plugin.
- `2KAbhishek/octohub.nvim`: referencia externa de solo lectura para patrones y estructura de plugins de Neovim (sin push a upstream ni PRs).
