# 📦 Dashboard Logístico - Transporte e Entregas

Este projeto tem como objetivo construir um **Dashboard de KPIs Logísticos** para análise de desempenho em operações de transporte e entregas. O projeto foi desenvolvido com base em dados fictícios, simulando cenários reais de uma operação logística empresarial.

## 🧠 Objetivo

Monitorar os principais indicadores de desempenho (KPIs) relacionados ao transporte de mercadorias, entregas, custos e eficiência operacional. O dashboard foi desenvolvido com foco em **análise gerencial**, **identificação de gargalos** e **tomada de decisão baseada em dados**.

---

## 📊 Indicadores e Métricas

O dashboard contempla os seguintes KPIs:

- **OTIF (On Time In Full)**: percentual de entregas realizadas dentro do prazo e completas.
- **Total de Entregas**: quantidade total de pedidos entregues no período.
- **Quantidade de Erros na Entrega**: número de entregas com ocorrências como avarias, extravios, devoluções etc.
- **Custo Médio de Entrega (R$)**: média de custo por pedido entregue.
- **Capacidade Média de Ocupação dos Veículos (%)**: indicador de eficiência da utilização dos veículos de transporte.


---

## 🔗 Link do Relatório

[📊 Acesse o dashboard publicado aqui]([https://coloque-seu-link-aqui](https://app.powerbi.com/view?r=eyJrIjoiYjhjMTdlMjYtNmViNS00ZTgwLTg4YTEtNzY4MzAzNjZlNzc5IiwidCI6IjZkMzFhNjdkLWEyNTEtNDc0Ny05ODllLWUyYzk1ODY4MmFlMCJ9))

---

## 🧮 Medidas DAX Criadas

\`\`\`DAX
-- Total de Entregas
Total Entregas = COUNTROWS(Fato_Entregas)

-- Entregas com Erro
Entregas com Erro =
CALCULATE(
    COUNTROWS(Fato_Entregas),
    Fato_Entregas[Erro na Entrega] = "Sim"
)

-- Custo Médio de Entrega
Custo Médio Entrega = AVERAGE(Fato_Entregas[Custo da Entrega (R$)])

-- Custo Médio Mês Anterior
Custo Médio Entrega Mês Anterior =
CALCULATE(
    [Custo Médio Entrega],
    DATEADD(Fato_Entregas[Data_Entrega], -1, MONTH)
)

-- OTIF
OTIF =
DIVIDE(
    CALCULATE(
        COUNTROWS(Fato_Entregas),
        Fato_Entregas[Data_Entrega] <= Fato_Entregas[Data_Pedido] + 3,
        Fato_Entregas[Erro na Entrega] = "Não"
    ),
    COUNTROWS(Fato_Entregas)
)

-- Capacidade Média de Ocupação (%)
Capacidade Média Ocupação (%) = AVERAGE(Fato_Entregas[Capacidade Ocupada (%)])
\`\`\`

---

## 🖼️ Visualizações do Dashboard

Abaixo, seguem prints das páginas e visuais criados:

![image](https://github.com/user-attachments/assets/1386d51b-6404-4ad0-b536-c733b06f4c70)



---

## 🛠️ Tecnologias Utilizadas

- Power BI Desktop
- DAX
- Excel / CSV (geração e estruturação dos dados)

---

## 📌 Autor

[João Victor]  
 
 

> Este projeto é fictício e tem fins educacionais e de portfólio. Nenhum dado real foi utilizado de forma confidencial ou proprietária.
