# Modelagem de Dados - Oficina Mecânica

# 💡 Sistema de Gerenciamento de Ordens de Serviço - Oficina Mecânica

Este projeto consiste em um **modelo de dados ER)** para um sistema de controle e gerenciamento da execução de **ordens de serviço (OS)** em uma **oficina mecânica**.

O modelo foi desenvolvido para ser visualizado no [draw.io (diagrams.net)](https://app.diagrams.net)

---

## 🧩 Entidades e Atributos

### **Cliente**
- `ID_Cliente` (PK)
- Nome
- Endereço
- Telefone

### **Veículo**
- `ID_Veiculo` (PK)
- Placa
- Modelo
- Ano
- Marca
- `ID_Cliente` (FK)

### **Ordem_de_Serviço (OS)**
- `ID_OS` (PK)
- Data_Emissão
- Data_Conclusão
- Valor_Total
- Status
- `ID_Veiculo` (FK)
- `ID_Equipe` (FK)

### **Equipe**
- `ID_Equipe` (PK)
- Nome_Equipe

### **Mecânico**
- `ID_Mecanico` (PK)
- Nome
- Endereço
- Especialidade
- `ID_Equipe` (FK)

### **Serviço**
- `ID_Servico` (PK)
- Descrição
- Valor_Mão_de_Obra

### **Peça**
- `ID_Peca` (PK)
- Nome
- Valor_Unitario

### **OS_Servico**
- `ID_OS` (FK)
- `ID_Servico` (FK)
- Valor_Calculado

### **OS_Peca**
- `ID_OS` (FK)
- `ID_Peca` (FK)
- Quantidade
- Valor_Total

---

## 🔁 Relacionamentos e Cardinalidades

- **Cliente 1:N Veículo** – Um cliente pode ter vários veículos.
- **Veículo 1:N OS** – Um veículo pode ter várias ordens de serviço.
- **Equipe 1:N OS** – Uma equipe pode ser responsável por várias ordens.
- **Equipe 1:N Mecânico** – Cada mecânico pertence a uma equipe.
- **OS 1:N OS_Servico** – Cada ordem pode conter vários serviços.
- **Serviço 1:N OS_Servico** – Um mesmo serviço pode ser utilizado em várias ordens.
- **OS 1:N OS_Peca** – Cada ordem pode conter várias peças.
- **Peça 1:N OS_Peca** – Uma peça pode estar presente em várias ordens.

---

