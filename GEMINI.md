# CruxPlane Extension Instructions

You have access to the **CruxPlane** cloud workspace and deployment platform (`https://cruxplane.dev`).

## Workflow Rules
1. **Call `cpx_guide` first** when starting a new multi-file build or stack architecture task.
2. **Instant Preview First:** `scaffold_workspace` returns `starter_paths` and a live `*.cruxpreview.dev` URL immediately—do not call `get_workspace_context` right after scaffolding.
3. **Zero Redundant Polling:** `batch_write_files` (keep `<= 400` lines per call) and `patch_workspace_files` already await inline `esbuild` compilation and return `build_status` + compiler errors.
4. **Deploy on Explicit Go-Ahead:** Share the live `*.cruxpreview.dev` preview URL first; deploy to Dev Sandbox or Production (`*.cruxplane.run`) via `deploy_workspace` when the user asks to deploy.
