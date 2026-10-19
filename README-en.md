*Leia isto em outros idiomas: [Português](README.md)*

---

# Super File Renamer (Google Drive)

Automation script for Google Apps Script that cleans file names, replaces text, removes exact intervals, and adds prefixes or suffixes to files in a Google Drive folder. It also offers an optional **Brazilian Portuguese Title Case** mode that normalizes capitalization and restores acronyms, special terms, and Roman numerals.

## 🚀 How to Use

For safety, create a **test folder** in Google Drive and use copies of files before applying changes to originals.

### Step 1: Get the Google Drive Folder ID
1. Open Google Drive on your computer and enter the target folder.
2. The browser URL will look like `https://drive.google.com/drive/folders/1A2b3C4d5E6f7G8h9I0j?usp=sharing`.
3. Copy the value after `folders/` and before any `?`.

### Step 2: Open Google Apps Script
1. Go to **script.google.com** and sign in.
2. Click **New project**.
3. Remove the sample code in the editor.
4. Paste the complete contents of `Gódigo.gs`.
5. Name and save the project.

### Step 3: Configure the Rules
In the `// ================= CONFIGURAÇÕES =================` section, configure only the rules you need:

- **Folder:** set `ID_DA_PASTA` to the Drive folder ID.
- **Removal:** `REMOVER_DO_INICIO`, `REMOVER_DO_FINAL`, `REMOVER_INTERVALO`, `REMOVER_ENTRE_TEXTOS`, and `TERMOS_PARA_REMOVER` remove characters or text segments.
- **Replacement:** `TERMOS_PARA_SUBSTITUIR` defines old/new text pairs.
- **Prefix/suffix:** `PREFIXO` and `SUFIXO` add text to the base file name.
- **Extension filter:** `MODO_EXTENSOES` accepts `TODAS` (all), `SOMENTE` (only), or `EXCETO` (except); configure the relevant extension list.
- **Optional capitalization:** change `MODO_FORMATACAO_NOME` from `NENHUM` to `TITLE_CASE_BRASILEIRO` to enable the new feature. `NENHUM` is the default and preserves the previous behavior.

The `TITLE_CASE_BRASILEIRO` mode keeps common Portuguese function words such as “de”, “da”, “e”, and “para” lowercase (unless a word is first), and restores acronyms and special terms listed in `SIGLAS_TITLE_CASE`, `SIGLAS_COM_HIFEN_TITLE_CASE`, and `TERMOS_ESPECIAIS_TITLE_CASE`, as well as configured Roman numerals. You can customize these lists in the code.

Example: `fundamentos DE medicina na uerj - volume iv.pdf` becomes `Fundamentos de Medicina na UERJ - Volume IV.pdf`. The file extension is preserved. Because capitalization is optional, review the simulation before renaming original files.

### Step 4: Run a Simulation
1. Select `simularRenomeacao` in the toolbar.
2. Click **Run**.
3. On the first run, grant the permissions requested by Google.
4. Check the **Execution log** and review each proposed name. Simulation does not modify files.

### Step 5: Rename Files
Only after reviewing the simulation, select `renomearArquivosDaPasta` and click **Run**. The script reports analyzed, changed, unchanged, extension-skipped files, and errors.

## 👤 Authorship and Development

Automation script independently developed by Pablo Phillipe Cândido dos Santos for bulk renaming and file-name standardization in Google Drive.

The development involved generative AI tools as an auxiliary resource, with the author retaining responsibility for the project's conception, implementation, integration, and verification.

Lattes Curriculum: [http://lattes.cnpq.br/9500873674712528](http://lattes.cnpq.br/9500873674712528)
