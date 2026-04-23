# Análise de Performance de Vendas SuperStore Sales
Utilizando o dataset de vendas SuperStore, iniciamos uma análise profunda para entender a dinâmica comercial e a rentabilidade da operação. O objetivo central é realizar uma análise exploratória e estratégica para identificar onde estão as oportunidades de lucro, como os descontos impactam a margem líquida e como as vendas evoluem ao longo do tempo (2014-2017).
Através do tratamento de dados brutos e da aplicação de cálculos avançados, buscamos entender quem são os clientes, quais produtos dominam o faturamento e onde a eficiência logística pode ser melhorada para otimizar os resultados da empresa.<br><br>

## 🛠️ Exploração e Tratamento de Dados
<img align="right" width="500"  src="https://github.com/GabrielChavesFS/SuperStoreSalesPortfolio/blob/main/Images/ExcelBruto.png?raw=true">
Iniciamos o projeto conectando à base de dados bruta ("tabela flat") para entender cada objeto, campo e as inconsistências presentes. O primeiro passo foi identificar a necessidade de uma limpeza rigorosa e uma reestruturação do modelo para suportar análises de inteligência temporal.
<br>
Identificamos a necessidade de uma <strong>limpeza rigorosa</strong> no Power Query e de uma <strong>reestruturação completa do modelo</strong>. Sem esse tratamento prévio, seria impossível suportar análises de inteligência temporal confiáveis ou cálculos de margem precisos.

<br><br>

## Modelagem de Dados (Star Schema)
<img align="left" width="500"  src="https://github.com/GabrielChavesFS/SuperStoreSalesPortfolio/blob/main/Images/StarSchemma.png?raw=true">
Para garantir a performance das medidas e a integridade dos filtros, implementamos a arquitetura <strong>Star Schema</strong> (Esquema Estrela). O dado bruto foi desmembrado em tabelas de <strong>Dimensão</strong> e uma tabela <strong>Fato (F_Sales)</strong>.

<br><br>

Um dos pilares deste modelo foi a criação de uma <strong>D_Calendario</strong> customizada, essencial para habilitar as funções de <em>Time Intelligence</em> (Inteligência Temporal) e permitir análises comparativas de períodos (ano, mês, trimestre).

<br><br><br>

<strong>Destaques da Modelagem:</strong>
<li>Relacionamentos de 1:N (um para muitos) para otimização de performance;</li>
<li>Criação de chaves substitutas onde necessário;</li>
<li>Organização de medidas em pastas para melhor governança do projeto.</li>

<br><br>
## Inteligência de Negócio com DAX
<img align="right" width="500" height="320" src="https://github.com/GabrielChavesFS/SuperStoreSalesPortfolio/blob/main/Images/Medidas.png?raw=true">

Com o modelo estruturado, desenvolvemos uma camada de métricas utilizando a linguagem <strong>DAX (Data Analysis Expressions)</strong>. O foco foi transformar colunas numéricas em indicadores de performance (KPIs) que respondem a perguntas reais de negócio.

As medidas foram organizadas em pastas temáticas (<em>Performance</em> e <em>Inteligência Temporal</em>) para facilitar a manutenção e garantir que o modelo seja autodescritivo.

<strong>Principais Lógicas Aplicadas:</strong>
<li><strong>Análises Comparativas:</strong> Implementação de cálculos de YoY (Year-over-Year) e MoM (Month-over-Month) para medir crescimento;</li>
<li><strong>Acumulados:</strong> Uso de funções YTD (Year-To-Date) para acompanhamento de metas anuais;</li>
<li><strong>Métricas de Eficiência:</strong> Desenvolvimento de cálculos de margem de lucro e SLA de entrega (Dias para Envio).</li>

<br>

Confira a documentação detalhada de todas as fórmulas DAX <a href="https://github.com/GabrielChavesFS/SuperStoreSalesPortfolio/tree/main/DAX-Queries" target="_blank">clicando aqui</a>.

<br><br>

## Dashboard Power BI
<img align="right" width="500"  src="https://github.com/GabrielChavesFS/SuperStoreSalesPortfolio/blob/main/Images/ProjetoFinal.png?raw=true">
Complementando a análise técnica, desenvolvi um dashboard focado na experiência do usuário e na agilidade da tomada de decisão. Utilizando o Power BI, foi possível criar um ambiente onde o gestor pode navegar por diferentes camadas de dados sem a necessidade de múltiplas planilhas, permitindo uma análise exploratória completa sobre a rentabilidade e eficiência da <strong>SuperStore</strong>.

<br>

<p><strong>Com esta análise, chegamos às seguintes conclusões:</strong></p>
<ul>
<li><strong>Foco em Margem:</strong> Determinadas subcategorias, embora tenham alto volume de vendas, apresentam margens reduzidas devido à agressividade dos descontos aplicados.</li>
<li><strong>Sazonalidade Identificada:</strong> Através das métricas de Time Intelligence, observamos picos de vendas recorrentes que permitem um melhor planejamento de estoque e logística.</li>
<li><strong>Eficiência Operacional:</strong> O monitoramento do <em>SLA de envio</em> revelou oportunidades de melhoria no fluxo de despacho para reduzir o tempo de entrega final.</li>
</ul>
<p>
O Power BI se mostra fundamental aqui, pois permite que o usuário final aplique seus próprios filtros e obtenha respostas personalizadas de forma dinâmica.
</p>

<br>

🔗 <a href="https://app.powerbi.com/view?r=eyJrIjoiMGI4NDY3ZDUtMDRkZS00OWY2LWJjYzYtZWI2YTkwYWJjOTM1IiwidCI6IjY1OWNlMmI4LTA3MTQtNDE5OC04YzM4LWRjOWI2MGFhYmI1NyJ9"><strong>Clique aqui</strong></a> e acesse a solução publicada.


📂 <a href="SuperStore Sales.pbix"><strong>Clique aqui</strong></a> e baixe o arquivo .pbix no GitHub.
