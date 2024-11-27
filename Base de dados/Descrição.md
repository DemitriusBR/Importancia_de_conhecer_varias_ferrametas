# Base de Dados de Compras

Este documento descreve as especificações da base de dados utilizada para o gerenciamento de compras, fornecedores e matérias-primas. A base de dados está organizada em 4 abas no arquivo Excel, cada uma com informações específicas, conforme detalhado abaixo.

## Estrutura da Base de Dados

### 1. Aba: `dCompras`

- **Descrição**: Contém informações sobre os compradores.
- **Colunas**:
  - **Código do Comprador**: Identificador único do comprador.
  - **Nome do Comprador**: Nome completo do comprador.

---

### 2. Aba: `dFornecedor`

- **Descrição**: Contém informações sobre os fornecedores.
- **Colunas**:
  - **Código do Fornecedor**: Identificador único do fornecedor.
  - **Nome do Fornecedor**: Nome completo do fornecedor.

---

### 3. Aba: `fCompra`

- **Descrição**: Contém os registros de compras, incluindo dados sobre pedidos, compradores, fornecedores e matérias-primas.
- **Colunas**:
  - **Pedido**: Número único do pedido de compra.
  - **Data Pedido**: Data em que o pedido foi realizado.
  - **Data Saída**: Data em que o pedido saiu do armazém ou foi processado.
  - **Previsão de Entrega**: Data estimada para a entrega do pedido.
  - **Data de Entrega**: Data real de entrega do pedido.
  - **Comprador**: ID do comprador (referência à aba `dCompras`).
  - **Matéria Prima**: ID da matéria-prima (referência à aba `dMateriaPrima`).
  - **Quantidade**: Quantidade solicitada da matéria-prima.
  - **% Desconto**: Percentual de desconto concedido ao comprador no pedido.
  - **Fornecedor**: ID do fornecedor (referência à aba `dFornecedor`).

---

### 4. Aba: `dMateriaPrima`

- **Descrição**: Contém informações sobre as matérias-primas utilizadas nas compras.
- **Colunas**:
  - **Código da Matéria Prima**: Identificador único da matéria-prima.
  - **Nome da Matéria Prima**: Nome da matéria-prima.
  - **Custo Unitário**: Custo de uma unidade da matéria-prima.

---

## Relacionamentos entre as Abas

- A coluna **Comprador** da aba `fCompra` refere-se ao **Código do Comprador** na aba `dCompras`.
- A coluna **Fornecedor** da aba `fCompra` refere-se ao **Código do Fornecedor** na aba `dFornecedor`.
- A coluna **Matéria Prima** da aba `fCompra` refere-se ao **Código da Matéria Prima** na aba `dMateriaPrima`.

---

## Observações

- Os **IDs de Comprador**, **Fornecedor** e **Matéria Prima** são utilizados como referências na aba `fCompra` para evitar a duplicação de informações nessas colunas.
- A aba `fCompra` é a principal fonte de dados para análise de compras, integrando informações de compradores, fornecedores e matérias-primas adquiridas.

---

Se houver dúvidas ou necessidade de ajustes na estrutura, entre em contato com o responsável pelo gerenciamento da base de dados.

