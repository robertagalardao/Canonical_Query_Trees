# Most Restrictive Selection

## Com a heurística aplicada:

```mermaid
graph TD
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