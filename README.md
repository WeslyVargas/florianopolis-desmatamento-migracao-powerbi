# florianopolis-desmatamento-migracao-powerbi
Análise socioambiental e do mercado imobiliário em Florianópolis utilizando Power BI, DAX e Power Query.
# 📊 Florianópolis: Análise Socioambiental e Mercado Imobiliário (2017–2026)

Este repositório contém o projeto autoral desenvolvido no **Power BI** para analisar a correlação entre a expansão do fluxo migratório, a escalada nos preços de aluguel e a taxa de desmatamento da Mata Atlântica na Ilha de Santa Catarina.

---

## 🎯 Objetivos do Projeto
* **Modelagem Socioeconômica:** Mapear a relação de causa e efeito entre a atração populacional e a pressão sobre o uso do solo.
* **Data Storytelling:** Demonstrar visualmente como a escassez de Habitação de Interesse Social (HIS) e a rigidez de preços no mercado formal impulsionam a periferização ambiental em encostas e Áreas de Preservação Permanente (APPs).
* **Aplicação Técnica:** Consolidar competências em Power Query (Linguagem M), DAX e design de dashboards interativos.

---

## 📈 Estrutura dos Dados e Fontes

A análise utiliza uma série temporal de 10 anos obtida através da triangulação e modelagem de fontes públicas e indicadores consolidados:

1. **Saldo Migratório (hab/ano):** IBGE (Censo Demográfico e Estimativas) e IPUF.
2. **Área Desmatada (ha):** MapBiomas Brasil (Alertas de Uso do Solo) e Atlas da Mata Atlântica (SOS Mata Atlântica / INPE).
3. **Valor do Aluguer (R$/m²):** Série histórica baseada no Índice FipeZAP de Locação Residencial (Florianópolis).

---

## 🛠️ Script Power Query (Linguagem M)

Para reproduzir a tabela de dados no Power BI:

```powerquery
let
    Fonte = #table(
        type table [
            Ano = Int64.Type, 
            Valor_Aluguel_m2 = number, 
            Area_Desmatada_ha = number, 
            Saldo_Migratorio = Int64.Type
        ],
        {
            {2017, 23.10, 8.0, 6200},
            {2018, 24.80, 9.0, 6800},
            {2019, 26.50, 11.0, 7500},
            {2020, 28.50, 12.0, 8100},
            {2021, 31.20, 18.0, 11400},
            {2022, 39.80, 27.0, 15800},
            {2023, 48.50, 32.0, 16200},
            {2024, 54.20, 29.0, 14900},
            {2025, 58.70, 24.0, 13500},
            {2026, 61.81, 21.0, 12800}
        }
    )
in
    Fonte
