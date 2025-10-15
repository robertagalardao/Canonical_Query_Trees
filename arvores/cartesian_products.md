# Transformation of Cartesian Products into Junction

## Sem heurística:

```mermaid
graph TD
    %% Folhas
    C[cliente]:::folha
    CO[compra]:::folha
    M[medicamento]:::folha

    %% Produto cartesiano
    X1[× Produto cartesiano]:::operacao
    X2[× Produto cartesiano]:::operacao

    %% Seleção com condições do WHERE
    S[σ c.id_cliente = co.fk_cliente_id_cliente ∧ co.fk_medicamento_id_medicamento = m.id_medicamento]:::selecao

    %% Projeção final
    P[π nomeCliente, dsMedic, valorMedic]:::projecao

    %% Conexões
    X1 --> C
    X1 --> CO
    X2 --> X1
    X2 --> M
    S --> X2
    P --> S

    %% Estilos
    classDef folha fill:#f2f2f2,stroke:#333,stroke-width:1px;
    classDef operacao fill:#d9eaff,stroke:#0074D9,stroke-width:1.5px;
    classDef selecao fill:#fcd5ce,stroke:#d62828,stroke-width:1.5px;
    classDef projecao fill:#ffd6a5,stroke:#e67e22,stroke-width:1.5px;