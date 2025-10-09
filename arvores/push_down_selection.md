# Push-Down Selection

## Sem heurística:

```mermaid
graph TD
    %% Folhas (tabelas)
    C[cliente]:::folha
    CO[compra]:::folha
    M[medicamento]:::folha

    %% Seleção (σ)
    S[σ valorMedic > 80]:::selecao

    %% Joins (⨝)
    J1[⨝ fk_medicamento_id_medicamento = id_medicamento]:::join
    J2[⨝ id_cliente = fk_cliente_id_cliente]:::join

    %% Projeção final (π)
    P[π nomeCliente, dsMedic, valorMedic]:::projecao

    %% Ligações
    S --> M
    J1 --> CO
    J1 --> S
    J2 --> C
    J2 --> J1
    P --> J2

    %% Estilos
    classDef folha fill:#f2f2f2,stroke:#333,stroke-width:1px;
    classDef selecao fill:#a2d2ff,stroke:#1a73e8,stroke-width:1.5px;
    classDef join fill:#c8f7c5,stroke:#2a9d27,stroke-width:1.5px;
    classDef projecao fill:#ffd6a5,stroke:#e67e22,stroke-width:1.5px;