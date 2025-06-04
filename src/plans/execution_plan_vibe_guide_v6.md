### Plano de Execução: VIBE GUIDE Release V6 - Agnóstico à Linguagem e Clean Code

**Objetivo:** Tornar o `VIBE_GUIDE.md` agnóstico à linguagem, extrair conteúdo específico de Python para um arquivo dedicado, criar arquivos de especificações para outras linguagens (Java, .NET, Node.js/JavaScript) e incluir diretivas de Clean Code.

**Passos:**

1.  **Backup do `VIBE_GUIDE.md`:**
    *   Salvar a versão atual do `VIBE_GUIDE.md` como `src/VIBE.005.md`.

2.  **Análise e Extração de Conteúdo Específico de Python:**
    *   Ler o `VIBE_GUIDE.md` para identificar todas as referências explícitas e implícitas à linguagem Python, exemplos de código, ferramentas e bibliotecas específicas (e.g., `uv`, `pytest`, `pytest-cov`, `@pyproject.toml`).
    *   Extrair todo esse conteúdo para uma seção temporária.

3.  **Criação do `VIBE_ESPECIFICS_PYTHON.md`:**
    *   Criar o arquivo `VIBE_ESPECIFICS_PYTHON.md` na raiz do projeto.
    *   Categorizar e elencar o conteúdo extraído de Python neste novo arquivo, referenciando os itens correspondentes no `VIBE_GUIDE.md` original.

4.  **Criação dos Arquivos de Especificação para Outras Linguagens:**
    *   Criar os seguintes arquivos na raiz do projeto, com uma estrutura inicial que indique que serão preenchidos com diretrizes específicas para cada linguagem:
        *   `VIBE_ESPECIFICS_JAVA.md`
        *   `VIBE_ESPECIFICS_DOTNET.md`
        *   `VIBE_ESPECIFICS_NODEJS_JAVASCRIPT.md`

5.  **Modificação do `VIBE_GUIDE.md` (Tornar Agnóstico à Linguagem):**
    *   Substituir todas as referências explícitas/implícitas a Python por termos agnósticos à linguagem (e.g., "ambiente virtual" por "ambiente de desenvolvimento isolado", "gerenciador de pacotes" por "ferramenta de gerenciamento de dependências").
    *   Remover exemplos de código e referências a ferramentas/bibliotecas específicas de Python, substituindo-as por diretivas gerais que se apliquem a qualquer linguagem/framework.
    *   Adicionar uma nova seção ou integrar as diretivas de Clean Code (baseadas na pesquisa realizada) junto às diretivas existentes sobre os princípios SOLID. As diretivas de Clean Code devem ser sucintas e objetivas.
    *   Atualizar a seção "Environment and Dependency Management" para ser agnóstica à linguagem, mencionando a necessidade de ferramentas de gerenciamento de dependências e ambientes isolados de forma geral.
    *   Atualizar a seção "Testing" para remover referências a `pytest` e `pytest-cov`, e generalizar as diretivas de execução de testes e cobertura de código.

6.  **Atualização do `VIBE_SUMMARY.md`:**
    *   Revisar e atualizar o `VIBE_SUMMARY.md` para refletir as mudanças no `VIBE_GUIDE.md`, garantindo que o sumário seja agnóstico à linguagem e inclua as novas diretivas de Clean Code.

7.  **Atualização do `README.md`:**
    *   Revisar e atualizar o `README.md` para refletir as mudanças no `VIBE_GUIDE.md` e mencionar a existência dos novos arquivos de especificações de linguagem.

8.  **Atualização do Banco de Memória (`memory_bank`):**
    *   Revisar todos os arquivos do `memory_bank` (`projectbrief.md`, `productContext.md`, `activeContext.md`, `systemPatterns.md`, `techContext.md`, `progress.md`) para garantir que estejam alinhados com as novas diretrizes agnósticas à linguagem e as diretivas de Clean Code.
    *   Adicionar referências aos novos arquivos de especificações de linguagem, se aplicável.

9.  **Revisão Final:**
    *   Realizar uma revisão completa de todos os arquivos modificados e criados para garantir consistência, clareza e aderência aos princípios do VIBE Guide.

**Diretivas de Clean Code a serem incluídas (baseadas na pesquisa):**

*   **Nomes Significativos:** Usar nomes descritivos para variáveis, funções, classes e outros identificadores.
*   **Funções Pequenas e Focadas:** Funções devem ser pequenas e fazer apenas uma coisa.
*   **Evitar Duplicação de Código:** Reutilizar código existente ou criar abstrações quando necessário.
*   **Tratamento de Erros:** Implementar tratamento de erros robusto e explícito.
*   **Comentários:** Usar comentários com moderação, apenas para explicar "porquê" e não "o quê". O código deve ser autoexplicativo.
*   **Formatação Consistente:** Manter um estilo de formatação consistente em todo o código.

**Diagrama de Fluxo de Trabalho:**

```mermaid
graph TD
    A[Início da Tarefa] --> B{Backup VIBE_GUIDE.md};
    B --> C[Analisar e Extrair Conteúdo Python];
    C --> D[Criar VIBE_ESPECIFICS_PYTHON.md];
    D --> E[Criar VIBE_ESPECIFICS_JAVA.md];
    E --> F[Criar VIBE_ESPECIFICS_DOTNET.md];
    F --> G[Criar VIBE_ESPECIFICS_NODEJS_JAVASCRIPT.md];
    G --> H[Modificar VIBE_GUIDE.md (Agnóstico e Clean Code)];
    H --> I[Atualizar VIBE_SUMMARY.md];
    I --> J[Atualizar README.md];
    J --> K[Atualizar Memory Bank];
    K --> L[Revisão Final];
    L --> M[Conclusão da Tarefa];
