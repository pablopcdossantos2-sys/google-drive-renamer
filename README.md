*Read this in other languages: [English](README-en.md)*

---

# Super Renomeador de Arquivos (Google Drive)

Script de automação para Google Apps Script que permite limpar, substituir textos, remover intervalos exatos e adicionar prefixos ou sufixos aos nomes de arquivos contidos em uma pasta do Google Drive. Também oferece um modo opcional de **Title Case brasileiro**, que normaliza a capitalização e restaura siglas, termos especiais e algarismos romanos.

## 🚀 Como utilizar (Tutorial)

Para utilizar o script com segurança, recomenda-se criar uma **pasta de teste** no seu Google Drive com cópias de alguns arquivos para praticar antes de rodar o código nos originais.

### Passo 1: Pegar o ID da Pasta no Google Drive
1. Abra o Google Drive pelo computador e entre na pasta onde estão os arquivos.
2. Na barra de endereços, o link será semelhante a `https://drive.google.com/drive/folders/1A2b3C4d5E6f7G8h9I0j?usp=sharing`.
3. Copie apenas o código que vem depois de `folders/` e antes de qualquer `?`.

### Passo 2: Acessar o Google Apps Script
1. Acesse **script.google.com** e faça login.
2. Clique em **Novo projeto**.
3. Apague o código padrão do editor.
4. Cole todo o conteúdo do arquivo `Gódigo.gs`.
5. Dê um nome ao projeto e salve.

### Passo 3: Configurar as Regras
Na seção `// ================= CONFIGURAÇÕES =================`, configure apenas as opções necessárias:

- **Pasta:** `ID_DA_PASTA` deve receber o ID da pasta do Drive.
- **Remoção:** `REMOVER_DO_INICIO`, `REMOVER_DO_FINAL`, `REMOVER_INTERVALO`, `REMOVER_ENTRE_TEXTOS` e `TERMOS_PARA_REMOVER` permitem retirar caracteres ou trechos.
- **Substituição:** `TERMOS_PARA_SUBSTITUIR` define pares de texto antigo e novo.
- **Prefixo/sufixo:** `PREFIXO` e `SUFIXO` adicionam textos ao nome-base.
- **Filtro por extensão:** `MODO_EXTENSOES` aceita `TODAS`, `SOMENTE` ou `EXCETO`; configure as listas de extensões correspondentes.
- **Capitalização opcional:** altere `MODO_FORMATACAO_NOME` de `NENHUM` para `TITLE_CASE_BRASILEIRO` para ativar a nova função. O padrão `NENHUM` preserva o comportamento anterior.

O modo `TITLE_CASE_BRASILEIRO` mantém palavras funcionais como “de”, “da”, “e” e “para” em minúsculas (exceto quando são a primeira palavra) e restaura as siglas e os termos especiais listados nas constantes `SIGLAS_TITLE_CASE`, `SIGLAS_COM_HIFEN_TITLE_CASE` e `TERMOS_ESPECIAIS_TITLE_CASE`, além dos algarismos romanos configurados. Essas listas podem ser personalizadas no código.

Exemplo: `fundamentos DE medicina na uerj - volume iv.pdf` passa a `Fundamentos de Medicina na UERJ - Volume IV.pdf`. A extensão é preservada. Como a capitalização é opcional, revise a simulação antes de renomear os arquivos originais.

### Passo 4: Fazer uma Simulação
1. Selecione `simularRenomeacao` na barra de ferramentas.
2. Clique em **Executar**.
3. Na primeira execução, conceda as permissões solicitadas pelo Google.
4. Confira o **Log de execução** e revise cada nome proposto. A simulação não modifica arquivos.

### Passo 5: Renomear de Verdade
Somente depois de conferir a simulação, selecione `renomearArquivosDaPasta` e clique em **Executar**. O script contabiliza arquivos analisados, alterados, sem mudança, ignorados por extensão e erros.

## 👤 Autoria e desenvolvimento

Script de automação desenvolvido de forma independente por Pablo Phillipe Cândido dos Santos, destinado à renomeação em massa e padronização de nomenclatura de arquivos no Google Drive.

O desenvolvimento contou com a utilização de ferramentas de inteligência artificial generativa como recurso auxiliar, mantendo-se sob responsabilidade do autor a concepção, implementação, integração e verificação do projeto.

Currículo Lattes: [http://lattes.cnpq.br/9500873674712528](http://lattes.cnpq.br/9500873674712528)
