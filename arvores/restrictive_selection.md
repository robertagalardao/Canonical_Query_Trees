# Most Restrictive Selection

Sem heurística aplicada:

```mermaid
graph TD
    %% Folhas (tabelas)
    C[cliente]:::folha
    CO[compra]:::folha
    M[medicamento]:::folha

    %% Seleções (σ)
    S1[σ id_cliente <= 20000]:::selecao
    S2[σ valorMedic > 50]:::selecao

    %% Joins (⨝)
    J1[⨝ Join Cliente-Compra]:::join
    J2[⨝ Join com Medicamento]:::join

    %% Projeção final (π)
    P[π nomeCliente, dsMedic, valorMedic]:::projecao

    %% Conexões
    S1 --> C
    J1 --> S1
    J1 --> CO
    S2 --> M
    J2 --> J1
    J2 --> S2
    P --> J2

    %% Estilos
    classDef folha fill:#f2f2f2,stroke:#333,stroke-width:1px;
    classDef selecao fill:#a2d2ff,stroke:#1a73e8,stroke-width:1.5px;
    classDef join fill:#c8f7c5,stroke:#2a9d27,stroke-width:1.5px;
    classDef projecao fill:#ffd6a5,stroke:#e67e22,stroke-width:1.5px;

graph TD
    %% Com a heurística aplicada
    %% Folhas (tabelas filtradas via CTE)
    CF[cliente_filtrado]:::folha
    CO[compra]:::folha
    MF[med_filtrado]:::folha

    %% Joins (⨝)
    J1[⨝ Join Cliente-Compra]:::join
    J2[⨝ Join com Medicamento]:::join

    %% Projeção final (π)
    P[π nomeCliente, dsMedic, valorMedic]:::projecao

    %% Conexões
    J1 --> CF
    J1 --> CO
    J2 --> J1
    J2 --> MF
    P --> J2

    %% Estilos
    classDef folha fill:#f2f2f2,stroke:#333,stroke-width:1px;
    classDef join fill:#c8f7c5,stroke:#2a9d27,stroke-width:1.5px;
    classDef projecao fill:#ffd6a5,stroke:#e67e22,stroke-width:1.5px;
