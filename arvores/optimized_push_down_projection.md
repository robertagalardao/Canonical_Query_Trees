# Push-Down Projection

## Com heurística aplicada:

```mermaid
graph TD
    %% Folhas (tabelas filtradas)
    C[cliente]:::folha
    CO[compra]:::folha
    MF[med_filtrado]:::folha

    %% Joins (⨝)
    J1[⨝ Join Compra-Med_Filtrado]:::join
    J2[⨝ Join Cliente-Compra]:::join

    %% Projeção final (π)
    P[π nomeCliente, dsMedic, valorMedic]:::projecao

    %% Conexões
    J1 --> CO
    J1 --> MF
    J2 --> C
    J2 --> J1
    P --> J2

    %% Estilos
    classDef folha fill:#f2f2f2,stroke:#333,stroke-width:1px;
    classDef join fill:#c8f7c5,stroke:#2a9d27,stroke-width:1.5px;
    classDef projecao fill:#ffd6a5,stroke:#e67e22,stroke-width:1.5px;