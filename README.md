# HR-GIT-SETUP

Meta-repo para gestionar y estandarizar las herramientas públicas de Roberto empaquetadas para Arch (nombres, CI y estrategias de publicación entre todos los dúos `fuente` + `*-arch`), incluyendo el ecosistema de [git-setup](https://github.com/robert-flo/pj-domina-rf-git-setup) y su plugin de Neovim **git-setup.nvim**.

## Arquitectura multi-repo (19 repositorios)

### Dúos de herramientas Arch (`fuente` + `*-arch`)
1. `pj-domina-rf-git-setup` + `pj-domina-rf-git-setup-arch` — CLI `git-setup` y su empaquetado Arch.
2. `pj-domina-rf-shared_dir` + `pj-domina-rf-shared_dir-arch` — Herramienta compartida `shared_dir` y su empaquetado Arch.
3. `ravn-git-bare-clone` + `ravn-git-bare-clone-arch` — Launcher/runtime modular de `ravn-git-bare-clone` y su paquete Arch Linux.
4. `ravn-sessionizer` + `ravn-sessionizer-arch` — Sessionizer para `herdr` y su paquete Arch.
5. `ravn-trio` + `ravn-trio-arch` — Trío PM/WK/RV local en `herdr` (`pj-trio`) y su paquete Arch.
6. `ravn-home-common` + `ravn-home-common-arch` — Capa común de `$HOME` para la workstation ravn y su PKGBUILD Arch Linux.
7. `ravn-home-niri` + `ravn-home-niri-arch` — Capa `niri` para la workstation ravn y su PKGBUILD/empaquetado Arch Linux.
8. `ravn-webapps` + `ravn-webapps-arch` — Launchers `.desktop`, íconos y runtime para webapps en RaVN y su empaquetado Arch / release automation.

### Ecosistema Neovim y referencia
- `pj-domina-rf-git-setup.nvim` — Plugin de Neovim compañero de `git-setup`.
- `rvim` — Configuración de Neovim de Roberto donde se integra y prueba el plugin.
- `octohub.nvim` (`2KAbhishek/octohub.nvim`) — Referencia externa de solo lectura (sin push a upstream ni PRs).

## El repo

Hijo de `robert-flo/pj-template` (modo dependencia): trae reglas, plantillas y skills del trío PM/WK/RV al SHA de `template_ref` y genera `.agents/` y `.cursor/`.

```bash
./pj listo      # después de clonar: pull, template, genera, hooks, onboarding, check
make agy-pm     # pull + ./pj listo y abre el PM en agy (make agy-wk, make agy-rv)
./pj onboard    # la entrevista del PM para llenar el onboarding
./pj            # solo trae pj-template al template_ref y genera .agents/ y .cursor/
./pj check      # esquema de proyecto.yml, idempotencia y prueba de humo
```

Necesitás `python3` (PyYAML y jsonschema van solos a `.pj/venv`), `gh`, `git` y `make`.
