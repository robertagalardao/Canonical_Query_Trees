graph TD
    %% Subgráfico sem heurística
    subgraph Sem_Heuristica ["Sem heurística aplicada"]
        C[cliente]:::folha
        CO[compra]:::folha
        M[medicamento]:::folha

        S1[σ id_cliente <= 20000]:::selecao
        S2[σ valorMedic > 50]:::selecao

        J1[⨝ Join Cliente-Compra]:::join
        J2[⨝ Join com Medicamento]:::join

        P[π nomeCliente, dsMedic, valorMedic]:::projecao

        S1 --> C
        J1 --> S1
        J1 --> CO
        S2 --> M
        J2 --> J1
        J2 --> S2
        P --> J2
    end

    %% Subgráfico com heurística (CTEs)
    subgraph Com_Heuristica ["Com heurística aplicada (CTEs)"]
        CF[cliente_filtrado]:::folha
        CO2[compra]:::folha
        MF[med_filtrado]:::folha

        J3[⨝ Join Cliente-Compra]:::join
        J4[⨝ Join com Medicamento]:::join

        P2[π nomeCliente, dsMedic, valorMedic]:::projecao

        J3 --> CF
        J3 --> CO2
        J4 --> J3
        J4 --> MF
        P2 --> J4
    end

    %% Estilos globais
    classDef folha fill:#f2f2f2,stroke:#333,stroke-width:1px;
    classDef selecao fill:#a2d2ff,stroke:#1a73e8,stroke-width:1.5px;
    classDef join fill:#c8f7c5,stroke:#2a9d27,stroke-width:1.5px;
    classDef projecao fill:#ffd6a5,stroke:#e67e22,stroke-width:1.5px;