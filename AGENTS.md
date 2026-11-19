# AGENTS.md — git-setup.nvim

Plugin de Neovim y meta-repo del trío PM/WK/RV de **git-setup.nvim** para Cursor y agy. Si sos un agente: si no existe `.agents/reglas/`, corré `./pj` antes de nada.

## Qué hay acá
- `proyecto.yml`: los datos del proyecto (repos, specs en orden, notas). Lo llenás vos.
- `onboarding.yml`: lo propio del proyecto para el PM, el WK y el RV (misión, lo que no tocan, primeros pasos, cómo se prueba, qué exige el RV). Lo escribe `./pj onboard`.
- Todo lo demás (reglas, plantillas, skills, scripts) lo trae `./pj` desde `robert-flo/pj-template` al SHA de `template_ref`, en `.pj/`, y genera `.agents/` y `.cursor/`. Nada de eso se versiona ni se edita a mano.

## Arquitectura
Proyecto de un solo repo: el código del plugin vive acá. La idea: una ventana flotante (`nvim_open_win`) con un buffer de terminal (`termopen`) que corre el comando de la CLI git-setup (el git-pull de pj-domina-rf-git-setup), y una notificación con el resultado según el código de salida (verde si salió bien, roja si no, dejando la ventana abierta para leer el error). El empaquetado Arch de la CLI vive en pj-domina-rf-git-setup-arch, fuera de este trío.
