# Gráfico de execução

```mermaid
%% Comparação de execução não otimizado vs otimizado
%% Valores em ms
%% Não otimizado = vermelho, Otimizado = verde

%% Configuração
%% width é a largura relativa da barra

graph LR
    PDS["Push-Down Selection"]
    MRS["Most Restrictive Selection"]
    CPC["Produto Cartesiano → Join"]
    PDP["Push-Down Projection"]

    PDS_NO["627 ms"]:::no
    PDS_OPT["608 ms"]:::opt
    MRS_NO["353 ms"]:::no
    MRS_OPT["272 ms"]:::opt
    CPC_NO["3328 ms"]:::no
    CPC_OPT["3178 ms"]:::opt
    PDP_NO["4213 ms"]:::no
    PDP_OPT["3201 ms"]:::opt

    PDS --> PDS_NO --> PDS_OPT
    MRS --> MRS_NO --> MRS_OPT
    CPC --> CPC_NO --> CPC_OPT
    PDP --> PDP_NO --> PDP_OPT

    classDef no fill:#f88,stroke:#000,stroke-width:1px;
    classDef opt fill:#8f8,stroke:#000,stroke-width:1px;
