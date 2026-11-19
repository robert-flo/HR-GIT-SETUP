# git-setup.nvim

Plugin de Neovim compañero de [git-setup](https://github.com/robert-flo/pj-domina-rf-git-setup): lanza una mini terminal flotante donde corre el comando de git-setup (el pull) y muestra una notificación con el resultado.

Estado: arranque. El repo trae solo el andamiaje del trío; el código del plugin viene después.

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
