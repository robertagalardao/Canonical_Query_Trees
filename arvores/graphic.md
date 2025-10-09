#Gráfico

```mermaid
graph TD
    %% Casos
    PDS["Seleção para baixo\n(Push-Down Selection)"]
    MRS["Seleção mais Restritiva\n(Most Restrictive Selection)"]
    CPC["Transformação de Produtos Cartesianos\nem Junção"]
    PDP["Projeção para baixo\n(Push-Down Projection)"]

    %% Não otimizado
    PDS_NO["Não otimizado\nExecution Time: 655 ms"]
    MRS_NO["Não otimizado\nExecution Time: 353 ms"]
    CPC_NO["Produto cartesiano\nExecution Time: 3328 ms"]
    PDP_NO["Não otimizado\nExecution Time: ~600 ms"]

    %% Otimizado
    PDS_OPT["Otimizado\nExecution Time: 623 ms"]
    MRS_OPT["Otimizado\nExecution Time: 272 ms"]
    CPC_OPT["Join explícito\nExecution Time: 3178 ms"]
    PDP_OPT["Otimizado\nExecution Time: ~300 ms"]

    %% Ligações
    PDS --> PDS_NO --> PDS_OPT
    MRS --> MRS_NO --> MRS_OPT
    CPC --> CPC_NO --> CPC_OPT
    PDP --> PDP_NO --> PDP_OPT