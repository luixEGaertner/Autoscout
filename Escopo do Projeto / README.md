🚗 Projeto AutoScout — Escopo e Cronograma

Objetivo: desenvolver um sistema automatizado para monitorar anúncios de carros usados, armazenar histórico de mercado, avaliar oportunidades segundo critérios personalizados, detectar anomalias/riscos e gerar relatórios semanais automáticos.

Dedicação prevista: ~2 h/semana
Duração: ~44 semanas
Carga total: ~88 h
Perfil: projeto pessoal/portfólio, com possibilidade de evolução para projeto acadêmico.


---

1. Escopo do projeto

1.1. Entrada

O sistema deverá coletar ou receber:

modelo;

versão;

ano;

preço;

quilometragem;

câmbio;

combustível;

localização;

vendedor;

descrição do anúncio;

URL;

fonte;

data de coleta;

eventualmente fotos/metadados.


Inicialmente, o foco será nos 14 modelos que você já selecionou.


---

1.2. Banco de dados

Armazenar:

Anúncio
├── veículo
├── preço
├── quilometragem
├── localização
├── vendedor
├── fonte
├── data
└── histórico

O sistema deverá conseguir responder:

> "Como o preço desse modelo mudou nas últimas semanas?"




---

1.3. Motor de avaliação

Cada anúncio receberá uma avaliação baseada nos critérios definidos para o casal:

Critério	Peso inicial

Conforto	20%
Economia	18%
Segurança	15%
Manutenção	12%
Peças/mecânica	10%
Confiabilidade	10%
Tecnologia	7%
Motor	5%
Firulas	3%


Os pesos deverão ser configuráveis, não fixos no código.

Resultado:

Fluence 2014
Score: 91/100


---

2. Detecção de oportunidades

O sistema deverá comparar o anúncio com o mercado.

Exemplo:

Mediana do modelo: R$ 53.000
Anúncio:           R$ 46.000

Diferença: -13,2%

Classificação:

🟢 oportunidade
🟡 normal
🟠 caro
🔴 muito caro


---

3. Detecção de risco

O sistema também terá um Risk Score independente.

Isso é importante porque:

> preço baixo ≠ necessariamente bom negócio.



Exemplo:

Oportunidade: 94/100
Risco:        81/100 🚨

Possíveis indicadores:

preço muito abaixo do mercado;

quilometragem anormal;

informações inconsistentes;

anúncio incompleto;

comportamento atípico do vendedor;

alterações bruscas de preço;

inconsistências entre descrição e características do veículo.



---

4. Inteligência Artificial

A IA será adicionada depois do sistema quantitativo estar funcionando.

Ela deverá auxiliar em:

interpretação da descrição;

extração de informações;

identificação de equipamentos;

identificação de possíveis red flags;

classificação textual;

geração da justificativa do score.


A IA não será responsável sozinha pela decisão.


---

5. Dashboard

Interface mostrando:

AUTOSCOUT

2.341 anúncios analisados

🟢 17 oportunidades
🟡 83 normais
🔴 32 suspeitos

────────────────────

TOP OPORTUNIDADES

1. Fluence 2014     91/100
2. Fit EX 2005      89/100
3. Civic 2005       86/100

Também deverá permitir filtros por:

modelo;

preço;

ano;

quilometragem;

score;

risco;

localização.



---

6. Relatório semanal

Toda semana o sistema produzirá automaticamente algo como:

🚗 AutoScout — Relatório semanal

Melhores oportunidades

1. Fluence Dynamique 2.0 CVT 2014 — 91/100


2. Fit EX 1.5 2005 — 89/100


3. Civic LX 2005 — 86/100



🚨 Atenção

Audi A1 2012 — R$ 39.900

> Preço significativamente abaixo da distribuição observada.



📊 Mercado

Fluence: ↓ 3,2%

Fit: ↑ 1,1%

Civic: ↓ 0,7%



---

7. Alertas

Quando aparecer algo excepcional:

🚨 NOVA OPORTUNIDADE

Honda Fit EX 1.5 2005
R$ 26.500
Score: 90
Risco: 18

8,5% abaixo da mediana.

O alerta poderá ser enviado por e-mail/Telegram ou outro canal disponível.


---

📅 Cronograma completo

🟦 Fase 0 — Especificação

Semana 1

Objetivo: definir exatamente o que será construído.

Entregáveis:

requisitos;

critérios;

pesos;

modelos monitorados;

estrutura inicial do banco.


Skills: análise de requisitos, modelagem de problemas.


---

🟩 Fase 1 — Dados

Semanas 2–4

Semana	Atividade

2	Python + Pandas
3	Limpeza e normalização
4	SQLite + SQL


Entregável: banco de dados contendo anúncios.

Skills: Python, Pandas, SQL, SQLite, tratamento de dados.


---

🟨 Fase 2 — Motor de Score

Semanas 5–8

Semana	Atividade

5	Score de preço/km/idade
6	Regras de avaliação
7	Pesos configuráveis
8	Ranking dos veículos


Entregável:

anúncio → score 0–100

Skills: algoritmos, funções, estatística básica, otimização multicritério.


---

🟧 Fase 3 — Coleta automática

Semanas 9–14

Semana	Atividade

9	HTTP + HTML
10	Primeiro coletor
11	Extração dos dados
12	Normalização
13	Deduplicação
14	Integração com o banco


Entregável:

site → coletor → banco

Skills: HTTP, HTML, Requests, BeautifulSoup, parsing, regex, automação.

> Começar com poucas fontes. Não tentar automatizar todos os sites simultaneamente.




---

🟪 Fase 4 — Histórico de mercado

Semanas 15–18

Semana	Atividade

15	Histórico de preços
16	Média/mediana/percentis
17	Comparação anúncio × mercado
18	Classificação de preço


Entregável:

preço observado
      ↓
distribuição do mercado
      ↓
posição do anúncio

Skills: estatística, análise exploratória, séries temporais básicas.


---

🟫 Fase 5 — Dashboard

Semanas 19–22

Semana	Atividade

19	Streamlit
20	Tabelas e filtros
21	Gráficos
22	Dashboard integrado


Entregável: interface web funcional.

Skills: Streamlit, visualização de dados, UX básica.


---

🟥 Fase 6 — Detecção de anomalias

Semanas 23–27

Semana	Atividade

23	Regras estatísticas
24	IQR/Z-score
25	Isolation Forest
26	Score de risco
27	Validação


Entregável:

OPORTUNIDADE SCORE
+
RISK SCORE

Skills: estatística, Machine Learning, scikit-learn.


---

🟦 Fase 7 — IA/NLP

Semanas 28–33

Semana	Atividade

28	LLM/API
29	Extração estruturada
30	Classificação de anúncios
31	Red flags
32	IA + score quantitativo
33	Testes


Entregável: IA capaz de interpretar anúncios.

Skills: APIs, JSON, NLP, LLM, classificação.


---

🟩 Fase 8 — Relatório automático

Semanas 34–36

Semana	Atividade

34	Gerar relatório
35	Gráficos/tabelas
36	Automatizar geração


Entregável:

dados
 ↓
análise
 ↓
relatório semanal


---

🟨 Fase 9 — Alertas

Semanas 37–39

Semana	Atividade

37	Regras de alerta
38	Integração com canal
39	Testes


Entregável:

Score alto
+
Risco baixo
       ↓
🚨 ALERTA


---

🟥 Fase 10 — Validação e versão 1.0

Semanas 40–44

Semana	Atividade

40	Avaliar falsos positivos
41	Ajustar pesos
42	Corrigir problemas
43	Documentação
44	Release AutoScout v1.0


Entregável final: sistema completo e documentado.


---

🧩 Stack final

LINGUAGEM
Python

DADOS
Pandas
NumPy
SQLite
SQL

WEB
Requests
BeautifulSoup
Playwright/Selenium quando necessário

ESTATÍSTICA
SciPy

ML
Scikit-learn

DASHBOARD
Streamlit

VISUALIZAÇÃO
Matplotlib / Plotly

IA
LLM + API + JSON estruturado

AUTOMAÇÃO
GitHub Actions / cron / serviço equivalente


---

🎯 Marco de conclusão

O projeto estará funcional antes das 44 semanas.

MVP — ~18 semanas

Já deverá:

coletar → armazenar → comparar → pontuar

Beta — ~27 semanas

Além disso:

dashboard + histórico + detecção de anomalias

v1.0 — ~44 semanas

Finalmente:

coleta + banco + histórico + score + risco + IA + dashboard + relatório + alertas


---

A regra mais importante do cronograma

2 horas por semana são suficientes, desde que o escopo permaneça controlado.

Não é necessário cumprir:

> "Semana 15 = obrigatoriamente terminar semana 15."



Se uma semana ficar impossível, você simplesmente desloca o cronograma.

A unidade de progresso será entregável, não quantidade de dias trabalhados.

Assim, o projeto não vira mais uma obrigação acadêmica: ele vai crescendo lentamente até chegar ao ponto em que o computador faz semanalmente a parte chata da busca de carros que você faria manualmente.