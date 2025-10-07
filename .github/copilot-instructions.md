# Copilot instructions for this repository

Purpose: help an AI contributor get immediately productive editing and building the AvePoint API documentation site.

- Big picture
  - This repository is a documentation site built with DocFX. The DocFX config is at `docs/docfx.json` and the generated site is written to `_site`.
  - Authoring sources live under `docs/` (note: there is a `docs/docs/` subfolder that contains most content pages such as `Overview.md`, `register-app.md`, and many `toc.yml` files that control nav).
  - API specifications and source OpenAPI/Swagger files live in `src/` (examples: `aos-swagger.json`, `aos-swagger.yaml`, `insights-swagger.json`, `googleBackup-swagger.json`). Some specs have pre-converted markdown (e.g. `insights-swagger.md`).

- What you can edit
  - Content pages: add or update markdown in `docs/docs/` (or other `docs/**` subfolders). Keep front-matter layout consistent (see `docs/index.md` which uses `---\n_layout: landing\n---`).
  - Navigation: update the nearest `toc.yml` in the same folder or a parent folder. There are many localized `toc.yml` files (e.g. `docs/docs/toc.yml`, `docs/docs/elements/toc.yml`).
  - Templates & CSS: custom templates/styles live under `docs/learntemplate/` (see `docs/learntemplate/public/main.css`). DocFX uses the templates declared in `docs/docfx.json` (`default`, `modern`, `learntemplate`).
  - API specs: update the source OpenAPI files in `src/`. There is no repository script discovered to auto-generate markdown from these specs, so follow the repo convention: update JSON/YAML in `src/` and coordinate with maintainers if md regeneration is required.

- Build / preview (Windows PowerShell)
  - Install DocFX (one option is Chocolatey):
    choco install docfx -y
  - Build the site (run from repo root):
    docfx build docs/docfx.json
    - output: `_site`
  - Serve/preview locally:
    docfx serve _site
  - If DocFX isn't acceptable, ask maintainers for the exact toolchain; `docfx` is the discovered build tool from `docs/docfx.json`.

- Project-specific conventions and patterns
  - Files and directories are organized by product area under `docs/docs/` and each area has its own `toc.yml`. Always update the relevant `toc.yml` when adding a page.
  - Page front-matter sometimes uses a custom `_layout` value (e.g. `landing`) — mirror the patterns in `docs/index.md`.
  - Global site behavior is controlled by `globalMetadata` in `docs/docfx.json` (for example `_disableContribution: true`, `_enableSearch: true`, and `output: _site`).
  - Swagger/OpenAPI files are canonical API sources (under `src/`). Some API docs are stored as pre-converted markdown — search `src/` before regenerating API docs.

- Integration points and external dependencies
  - Identity and OAuth examples in the docs reference external AvePoint identity endpoints; these are documentation examples, not runtime code in this repo.
  - No build/test scripts for code were discovered. This repo's main artifact is the generated website.

- Quick examples (concrete edits an agent can make)
  - Add a new API guide: create `docs/docs/myarea/new-guide.md` with front-matter, then add an entry to `docs/docs/myarea/toc.yml`, run `docfx build docs/docfx.json`, and `docfx serve _site` to validate.
  - Update an OpenAPI file: edit `src/aos-swagger.yaml`. If you need an updated markdown derivative, ask maintainers for their preferred conversion command; there is no conversion script in-tree.

If anything above is unclear or you want the file to include a contributor checklist (PR labels, branch naming, or automation hooks), tell me what conventions your team follows and I will iterate. 
