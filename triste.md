# Diseño de Multiplicador Binario 3x2 Bits

Este es el diagrama lógico combinatorio para el producto de dos números de 3x2 bits.

```mermaid
graph TD
    subgraph Entradas
        A0 --> AND_A0B0
        A1 --> AND_A1B0
        A2 --> AND_A2B0
        A0 --> AND_A0B1
        A1 --> AND_A1B1
        A2 --> AND_A2B1
        B0 --> AND_A0B0
        B0 --> AND_A1B0
        B0 --> AND_A2B0
        B1 --> AND_A0B1
        B1 --> AND_A1B1
        B1 --> AND_A2B1
    end

    subgraph Productos_Parciales
        AND_A0B0(A0*B0) --> P0_Salida
        AND_A1B0(A1*B0) --> HA1_Entrada1
        AND_A0B1(A0*B1) --> HA1_Entrada2
        AND_A2B0(A2*B0) --> FA1_Entrada1
        AND_A1B1(A1*B1) --> FA1_Entrada2
        AND_A2B1(A2*B1) --> HA2_Entrada1
    end

    subgraph Sumadores
        HA1_Entrada1 --> HA1
        HA1_Entrada2 --> HA1
        HA1(Medio Sumador 1) --> P1_Salida
        HA1 --> C1_Salida
        C1_Salida(C1) --> FA1_AcarreoEntrada

        FA1_Entrada1 --> FA1
        FA1_Entrada2 --> FA1
        FA1_AcarreoEntrada --> FA1
        FA1(Sumador Completo 1) --> P2_Salida
        FA1 --> C2_Salida
        C2_Salida(C2) --> HA2_AcarreoEntrada

        HA2_Entrada1 --> HA2
        HA2_AcarreoEntrada --> HA2
        HA2(Medio Sumador 2) --> P3_Salida
        HA2 --> C3_Salida
        C3_Salida(C3) --> P4_Salida
    end

    subgraph Salidas
        P0_Salida(P0)
        P1_Salida(P1)
        P2_Salida(P2)
        P3_Salida(P3)
        P4_Salida(P4)
    end

    P0_Salida --- Producto_Final
    P1_Salida --- Producto_Final
    P2_Salida --- Producto_Final
    P3_Salida --- Producto_Final
    P4_Salida --- Producto_Final

    style P0_Salida fill:#fff,stroke:#333,stroke-width:2px
    style P1_Salida fill:#fff,stroke:#333,stroke-width:2px
    style P2_Salida fill:#fff,stroke:#333,stroke-width:2px
    style P3_Salida fill:#fff,stroke:#333,stroke-width:2px
    style P4_Salida fill:#fff,stroke:#333,stroke-width:2px
