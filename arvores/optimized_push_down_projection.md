# Push-Down Projection

## Com heurística aplicada:

```mermaid
graph TD
    %% Folhas (tabelas projetadas)
    CP[clientes_proj]:::folha
    CO[compra]:::folha
    MP[medicamentos_proj]:::folha

    %% Joins (⨝)
    J1[⨝ id_cliente = fk_cliente_id_cliente]:::join
    J2[⨝ fk_medicamento_id_medicamento = id_medicamento]:::join

    %% Projeção final (π)
    P[π nomeCliente, dsMedic]:::projecao

    %% Ligações
    J1 --> CP
    J1 --> CO
    J2 --> J1
    J2 --> MP
    P --> J2

    %% Estilos
    classDef folha fill:#f2f2f2,stroke:#333,stroke-width:1px;
    classDef join fill:#c8f7c5,stroke:#2a9d27,stroke-width:1.5px;
    classDef projecao fill:#ffd6a5,stroke:#e67e22,stroke-width:1.5px;