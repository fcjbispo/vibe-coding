### Plano de Execução para VIBE_GUIDE v6.1

**Objetivo:** Atualizar o `VIBE_GUIDE` e seus arquivos relacionados para a versão 6.1, corrigindo a grafia de "ESPECIFICS" para "SPECIFICS", adicionando seções de instruções específicas por linguagem (exceto Python) e atualizando a documentação.

**Etapas:**

1.  **Renomear Arquivos `VIBE_ESPECIFICS_<LANGUAGE>.md`:**
    *   Renomear os seguintes arquivos para a grafia correta:
        *   `VIBE_ESPECIFICS_DOTNET.md` para `VIBE_SPECIFICS_DOTNET.md`
        *   `VIBE_ESPECIFICS_JAVA.md` para `VIBE_SPECIFICS_JAVA.md`
        *   `VIBE_ESPECIFICS_NODEJS_JAVASCRIPT.md` para `VIBE_SPECIFICS_NODEJS_JAVASCRIPT.md`
        *   `VIBE_ESPECIFICS_PYTHON.md` para `VIBE_SPECIFICS_PYTHON.md`

2.  **Atualizar Referências de Arquivos:**
    *   Atualizar todas as referências a `VIBE_ESPECIFICS_<LANGUAGE>.md` para `VIBE_SPECIFICS_<LANGUAGE>.md` nos seguintes arquivos:
        *   `VIBE_GUIDE.md`
        *   `README.md`
        *   `memory_bank/activeContext.md`
        *   `memory_bank/techContext.md`
        *   `memory_bank/progress.md`
        *   `src/plans/execution_plan_vibe_guide_v6.md`
        *   `.prompts.md` (se aplicável, para garantir consistência interna)

3.  **Adicionar Seções de Instruções Específicas por Linguagem:**
    *   Para cada um dos arquivos `VIBE_SPECIFICS_<LANGUAGE>.md` (exceto Python), adicionar as seguintes seções, numerando-as sequencialmente:
        1.  `Environment and Dependency Management`
        2.  `Testing`
        3.  `Prompts Specifics`
            1.  `REFACTOR`
            2.  `REVIEW_README`
            3.  `REVIEW_TEST`
    *   Utilizar o conteúdo existente em `VIBE_SPECIFICS_PYTHON.md` como exemplo para a estrutura e o tipo de informação a ser incluída.

4.  **Atualizar Documentação Principal:**
    *   Revisar e atualizar o `README.md` para refletir todas as mudanças de nomes de arquivos e a nova estrutura de documentação.

5.  **Atualizar Memory Bank:**
    *   Revisar e atualizar os arquivos do `memory_bank` (`activeContext.md`, `techContext.md`, `progress.md`) para refletir as mudanças de nomes de arquivos e a adição das novas seções. Garantir que o `activeContext.md` e `progress.md` reflitam o estado atual da tarefa.

**Fluxo de Execução (Mermaid Diagram):**

:::mermaid
graph TD
    A[Início: Leitura do Memory Bank e Identificação de "ESPECIFICS"] --> B{Renomear Arquivos VIBE_ESPECIFICS_<LANG>.md};
    B --> C{Atualizar Referências em Todos os Arquivos .md};
    C --> D{Adicionar Seções em VIBE_SPECIFICS_<LANG>.md (exceto Python)};
    D --> E{Atualizar README.md};
    E --> F{Atualizar Memory Bank};
    F --> G[Fim: Plano Concluído];
:::
