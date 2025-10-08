# Transformation of Cartesian Products into Junction

## Com heurística aplicada:

```mermaid
graph TD
    %% Folhas (tabelas)
    C[cliente]:::folha
    CO[compra]:::folha
    M[medicamento]:::folha

    %% Joins (⨝)
    J1[⨝ Join Cliente-Compra]:::join
    J2[⨝ Join Resultado-Medicamento]:::join

    %% Projeção final (π)
    P[π nomeCliente, dsMedic, valorMedic]:::projecao

    %% Conexões
    J1 --> C
    J1 --> CO
    J2 --> J1
    J2 --> M
    P --> J2

    %% Estilos
    classDef folha fill:#f2f2f2,stroke:#333,stroke-width:1px;
    classDef join fill:#c8f7c5,stroke:#2a9d27,stroke-width:1.5px;
    classDef projecao fill:#ffd6a5,stroke:#e67e22,stroke-width:1.5px;