⚡ ENERGYWISE - Eficiência Energética, Custos Industriais & Sustentabilidade (ESG)

Projeto de análise avançada de dados e visualização executiva, focado em eficiência energética industrial, redução de custos operacionais e avaliação de impacto ambiental, utilizando dados simulados realistas e dashboard estratégico em Power BI.

📌 Visão Geral

Empresas industriais enfrentam pressão crescente para:

reduzir custos energéticos,

aumentar eficiência operacional,

cumprir metas de sustentabilidade (ESG).

O ENERGYWISE foi desenvolvido como um case executivo de portfólio, simulando um cenário real de grandes operações industriais, com foco em decisão estratégica orientada por dados.

🎯 Objetivos do Projeto

Identificar onde o consumo energético é mais elevado

Comparar eficiência entre plantas industriais

Avaliar impacto financeiro por fonte de energia

Detectar desperdícios operacionais (equipamentos e turnos)

Medir impacto ambiental (emissões de CO₂)

Apoiar decisões estratégicas de eficiência e sustentabilidade

🧠 Abordagem Analítica (Método DEASA)

O projeto segue o método DEASA:

Definição do Problema

Redução de custos energéticos e melhoria de eficiência industrial com metas ESG.

Estruturação do Problema

Análise por:

Planta

Fonte de energia

Equipamento

Turno

Período

Análise de Dados

Dataset simulado não homogêneo

Distribuições distintas

Outliers naturais e defensáveis

Desenvolvimento de Soluções

KPIs executivos

Comparações claras

Identificação de ineficiências

Apresentação dos Resultados

Dashboard executivo

Storytelling estratégico

Visual premium

🧩 Modelo de Dados

Tipo

Modelo Estrela

Tabela Fato

Fato_ConsumoEnergia

Granularidade:

Planta × Equipamento × Turno × Fonte × Dia

📄 Campos da Fato

Campo |	Descrição

ID_Consumo | Identificador único
Date | Data do registro
ID_Planta	| Planta industrial
ID_Regiao	| Região geográfica
ID_Turno	| Turno operacional
ID_FonteEnergia	| Fonte de energia
ID_Equipamento	| Equipamento
Consumo_MWh	| Consumo energético
Custo_Energia_R$	| Custo total
Emissao_CO2_ton	| Emissão de CO₂
Horas_Operacao	| Horas de operação
Producao_Unidades	| Produção

📊 KPIs Principais

Consumo Total de Energia (MWh)

Custo Total de Energia (R$)

Consumo Médio por Planta

Custo por Unidade Produzida

Intensidade Energética (MWh / unidade)

Emissão Total de CO₂

Eficiência Energética (%)

Variação MoM e YoY (Consumo e Custo)

📈 Dashboard — ENERGYWISE

Tema Visual

Estratégia & Inovação — Dark Mode Premium

Público-alvo

Diretoria

Executivos C-level

Comitês estratégicos

Avaliação de portfólio sênior

📄 Páginas do Dashboard

1️⃣ Resumo Executivo Energético

KPIs estratégicos

Consumo por planta

Custo por fonte

Produção × Consumo

2️⃣ Análise por Planta

Benchmark de consumo

Evolução temporal

Eficiência comparativa

3️⃣ Equipamentos & Turnos

Consumo por equipamento

Heatmap turno × planta

Diagnóstico operacional

4️⃣ Sustentabilidade & ESG

Emissões por planta

Emissões por fonte

Evolução temporal de CO₂

Ranking de poluentes

📐 MEDIDAS DAX 

🔹 1. Consumo Total de Energia (MWh)
Consumo Total MWh =
SUM ( Fato_ConsumoEnergia[Consumo_MWh] )


Uso:
KPIs, consumo por planta, consumo por equipamento, scatter.

🔹 2. Custo Total de Energia (R$)
Custo Total Energia =
SUM ( Fato_ConsumoEnergia[Custo_Energia_R$] )


Uso:
KPIs financeiros, custo por fonte, análises CFO.

🔹 3. Emissão Total de CO₂ (ton)
Emissão Total CO2 =
SUM ( Fato_ConsumoEnergia[Emissao_CO2_ton] )


Uso:
Dashboard ESG, ranking ambiental, evolução temporal.

🔹 4. Produção Total
Produção Total =
SUM ( Fato_ConsumoEnergia[Producao_Unidades] )


Uso:
Base para indicadores de eficiência e scatter.

🔹 5. Consumo Médio por Planta
Consumo Médio por Planta =
AVERAGEX (
    VALUES ( Fato_ConsumoEnergia[ID_Planta] ),
    [Consumo Total MWh]
)


Uso:
Benchmark entre plantas.

🔹 6. Custo por Unidade Produzida
Custo por Unidade =
DIVIDE (
    [Custo Total Energia],
    [Produção Total]
)


Uso:
Eficiência econômica, análise de competitividade.

🔹 7. Intensidade Energética

(MWh por unidade produzida)

Intensidade Energética =
DIVIDE (
    [Consumo Total MWh],
    [Produção Total]
)


Uso:
Indicador-chave de eficiência operacional.

🔹 8. Eficiência Energética (%)

Quanto menor a intensidade, maior a eficiência

Eficiência Energética (%) =
VAR Intensidade = [Intensidade Energética]
RETURN
IF (
    NOT ISBLANK ( Intensidade ),
    DIVIDE ( 1, Intensidade ) * 100
)


Uso:
KPIs executivos, comparação entre plantas.

⏱️ ANÁLISES TEMPORAIS (MoM / YoY)
🔹 9. Consumo Mês Anterior (MoM)
Consumo Mês Anterior =
CALCULATE (
    [Consumo Total MWh],
    DATEADD ( Fato_ConsumoEnergia[Date], -1, MONTH )
)

🔹 10. Variação Mensal de Consumo (%)
Consumo MoM % =
DIVIDE (
    [Consumo Total MWh] - [Consumo Mês Anterior],
    [Consumo Mês Anterior]
)

🔹 11. Consumo Ano Anterior (YoY)
Consumo Ano Anterior =
CALCULATE (
    [Consumo Total MWh],
    SAMEPERIODLASTYEAR ( Fato_ConsumoEnergia[Date] )
)

🔹 12. Variação Anual de Consumo (%)
Consumo YoY % =
DIVIDE (
    [Consumo Total MWh] - [Consumo Ano Anterior],
    [Consumo Ano Anterior]
)

🔹 13. Custo Mês Anterior (MoM)
Custo Mês Anterior =
CALCULATE (
    [Custo Total Energia],
    DATEADD ( Fato_ConsumoEnergia[Date], -1, MONTH )
)

🔹 14. Variação Mensal de Custo (%)
Custo MoM % =
DIVIDE (
    [Custo Total Energia] - [Custo Mês Anterior],
    [Custo Mês Anterior]
)

🔹 15. Custo Ano Anterior (YoY)
Custo Ano Anterior =
CALCULATE (
    [Custo Total Energia],
    SAMEPERIODLASTYEAR ( Fato_ConsumoEnergia[Date] )
)

🔹 16. Variação Anual de Custo (%)
Custo YoY % =
DIVIDE (
    [Custo Total Energia] - [Custo Ano Anterior],
    [Custo Ano Anterior]
)

🎨 Identidade Visual
Paleta (Dark Mode)

Fundo: #0E1117

Cards: #1A1F2B

Texto principal: #F9FAFB

Roxo (inovação): #7C3AED

Verde (eficiência): #22C55E

Estilo

Visual limpo

Alto contraste

Sem poluição

Foco em decisão

🛠 Tecnologias Utilizadas

Python — geração de dados simulados

Pandas / NumPy — modelagem e distribuição

Power BI — modelagem, DAX e visualização

Figma — design do dashboard

GitHub — versionamento e portfólio

📌 Principais Insights (Exemplo)

Plantas com maior consumo nem sempre são as mais produtivas

Fontes térmicas concentram maior custo e emissão

Turnos noturnos apresentam menor eficiência média

Equipamentos obsoletos geram outliers claros de desperdício

🚀 Diferenciais do Projeto

✔ Dataset grande e não homogêneo
✔ Outliers naturais e explicáveis
✔ Visual executivo premium
✔ Storytelling estratégico
✔ Abordagem de consultoria
✔ Pronto para portfólio sênior

⚠️ Observações Importantes

Dados simulados, porém realistas

Projeto com foco educacional e demonstrativo

Nenhuma informação real de empresa utilizada

👤 Autor

Projeto desenvolvido por Guilherme Alencar
Especialista em Análise de Dados, Negócios e Visualização Executiva

📫 LinkedIn: https://www.linkedin.com/in/guilherme-alencar-327413213/
📊 Portfólio: https://github.com/GuilhermeAlencarSilva

⭐ Conclusão

O ENERGYWISE demonstra como dados bem estruturados, aliados a visualização estratégica, podem apoiar decisões complexas em ambientes industriais, equilibrando custo, eficiência e sustentabilidade.
