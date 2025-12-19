# 📘 Autoavaliação – MVP de Engenharia de Dados

## 1. Contexto Acadêmico
Este projeto foi desenvolvido com o objetivo de demonstrar a compreensão dos principais conceitos, arquiteturas e boas práticas associadas à construção de pipelines de dados analíticos e atingiu 100% dos objetivos propostos.

---

## 2. Avaliação do Escopo e Complexidade
O escopo definido para o projeto mostrou-se coerente com os objetivos da disciplina. A utilização de um dataset real e público, aliado à implementação da arquitetura Medallion (Bronze, Silver e Gold), permitiu trabalhar simultaneamente aspectos de:

- Ingestão e armazenamento de dados;
- Tratamento, padronização e governança;
- Modelagem analítica;
- Análise exploratória orientada a perguntas de negócio.

---

## 3. Arquitetura e Engenharia de Dados
Do ponto de vista de engenharia de dados, o projeto atende de forma satisfatória aos principais requisitos esperados para um MVP acadêmico:

- Implementação clara da **arquitetura Medallion**, com separação explícita de responsabilidades entre camadas;
- Uso consistente de **Delta Lake**, explorando versionamento, confiabilidade e organização dos dados;
- Tratamento estruturado de valores nulos, domínios inválidos e tipos de dados;
- Pipeline reprodutível e organizado, alinhado a boas práticas de engenharia de dados.

Embora não tenha sido implementado carregamento incremental ou orquestração avançada, tais itens foram conscientemente deixados como evolução futura.

---

## 4. Qualidade dos Dados e Governança
As práticas de qualidade e governança adotadas são compatíveis com o nível esperado:

- Padronização de valores categóricos;
- Estratégias explícitas de preenchimento de nulos;
- Controle de schema na escrita das tabelas;
- Uso de camadas para rastreabilidade e auditoria.

---

## 5. Análise e Geração de Insights
As análises exploratórias realizadas demonstram capacidade de:

- Traduzir dados em perguntas analíticas relevantes;
- Relacionar métricas técnicas e comportamentais;
- Interpretar resultados de forma crítica, evitando conclusões determinísticas.

Um ponto positivo do projeto é o cuidado em não extrapolar os resultados, deixando explícito que as análises fornecem apenas indícios iniciais, o que demonstra maturidade analítica e alinhamento com boas práticas acadêmicas.

---

## 6. Limitações Reconhecidas
Como parte da autoavaliação, destacam-se as seguintes limitações:

- Dependência de métricas proprietárias do Spotify (ex.: popularidade);
- Ausência de dados de consumo absoluto (streams, receita);
- Análises estatísticas predominantemente descritivas.

---

## 7. Aderência aos Objetivos da Disciplina
O projeto atende de forma consistente aos objetivos da disciplina de Engenharia de Dados, demonstrando:

- Compreensão dos conceitos fundamentais;
- Capacidade de implementação prática;
- Organização, documentação e clareza técnica;
- Integração entre engenharia de dados e análise analítica.

---

## 8. Considerações Finais
De forma geral, o MVP pode ser considerado bem-sucedido dentro de sua proposta. Ele demonstra domínio conceitual, aplicação prática e pensamento crítico, servindo como uma base sólida para projetos mais complexos em contextos corporativos ou em disciplinas futuras do curso.

Como próximos passos naturais, o projeto poderia evoluir para incorporar:

- Análises estatísticas e preditivas mais aprofundadas;
- Conectar um Power BI diretamente às tabelas Delta para visualização interativa.

---
