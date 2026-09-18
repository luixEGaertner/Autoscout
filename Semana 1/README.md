# AutoScout — Sistema de Monitoramento de Carros Usados

Sistema automatizado de engenharia de dados para acompanhamento de anúncios, análise quantitativa de oportunidades de mercado e detecção de riscos em veículos seminovos.

## 📌 Entradas de Dados
- **Identificação:** Modelo, Versão, Ano Fabricação/Modelo.
- **Comerciais:** Preço (R$), Quilometragem (km), Cidade/Estado, Vendedor (Particular/Lojista), Fonte, URL do Anúncio.
- **Técnicos:** Câmbio, Combustível, Descrição Completa.

## 📊 Métricas Calculadas (Saídas)
- **Score Oportunidade (0-100):** Pontuação multicritério ponderada.
- **Preço Relativo (%):** Desconto/Acréscimo frente à mediana do mercado regional.
- **Risk Score (0-100):** Alerta estatístico para anomalias de preço e potenciais problemas mecânicos/golpes.
- **Ranking Semanal:** Classificação ordinal das melhores oportunidades.

## ⚖️ Critérios de Avaliação e Pesos
| Critério | Peso | Descrição |
|---|---|---|
| Conforto | 20% | Ar-condicionado, direção, espaço interno e acabamento |
| Economia | 18% | Consumo urbano/rodoviário (km/l) e combustível |
| Segurança | 15% | Airbags, freios ABS, controle de tração/estabilidade |
| Manutenção | 12% | Custo médio de revisão e facilidade mecânica |
| Peças | 10% | Disponibilidade e preço no mercado nacional |
| Confiabilidade | 10% | Histórico de durabilidade do conjunto motor/câmbio |
| Tecnologia | 7% | Multimídia, conectividade e assistentes de condução |
| Motor/Desempenho | 5% | Potência (cv) e torque (kgfm) |
| Estética/Acessórios | 3% | Rodas de liga, teto solar e estado visual aparente |
