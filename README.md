# MVP_Eng_Dados
# 📊 MVP – Engenharia de Dados

## Introdução
Este projeto consiste em um **MVP de Engenharia de Dados** desenvolvido no Databricks, com foco na construção de um pipeline analítico utilizando **Apache Spark**, **Delta Lake** e a **arquitetura Medallion (Bronze, Silver e Gold)**. O pipeline foi aplicado a um dataset global do Spotify com o objetivo de estruturar, tratar e analisar dados musicais de forma escalável e governada.

---

## 🎯 1. Objetivo do Projeto
O objetivo do projeto é construir um pipeline de dados que permita:
- Organizar dados brutos de streaming musical em camadas analíticas bem definidas;
- Garantir qualidade, padronização e governança dos dados;
- Disponibilizar uma base final pronta para análises exploratórias;
- Investigar fatores que influenciam a popularidade das faixas no Spotify, como atributos do artista, tipo de álbum e características das músicas.

---

## 🌐 2. Fonte dos Dados
Os dados utilizados neste projeto são provenientes do Kaggle:

**Spotify Global Music Dataset (2009–2025)**  
https://www.kaggle.com/datasets/wardabilal/spotify-global-music-dataset-20092025

O dataset contém informações sobre faixas, artistas e álbuns, incluindo métricas de popularidade, seguidores, duração das músicas e tipos de lançamento.

---

## 🧱 3. Arquitetura do Pipeline (Medallion)

O pipeline foi implementado seguindo a arquitetura **Medallion**, organizada nas seguintes camadas:

### 🔹 Staging
- Upload manual do arquivo CSV em um **Volume do Databricks**.
- Camada temporária utilizada apenas como ponto de entrada dos dados brutos.

### 🔹 Bronze
- Armazenamento dos dados brutos em formato **Delta Table**.
- Leitura direta do CSV com inferência de schema.
- Preserva os dados sem transformações de negócio, servindo como camada de auditoria e rastreabilidade.

### 🔹 Silver
- Camada de **limpeza, padronização e tratamento de dados**.
- Principais transformações:
  - Preenchimento de valores nulos:
    - Campos categóricos com `"Unknown"`;
    - Métricas numéricas de artistas com `0`.
  - Conversão e padronização de tipos de dados.
  - Validação de domínios para campos como `album_type` e `explicit`.
- Escrita em Delta Table com schema controlado.

### 🔹 Gold
- Camada analítica final, pronta para consumo.
- Remoção de colunas não relevantes para análise exploratória.
- Estrutura otimizada para consultas, visualizações e geração de insights.

---

## 📐 4. Modelagem Dimensional – Tabela Flat
Na camada Gold, foi adotada uma **modelagem em tabela flat**, consolidando informações de faixas, artistas e álbuns em uma única tabela analítica.  

---

## 📚 5. Catálogo de Dados (Resumo)

**Faixa (Track)**
- `track_id`
- `track_name`
- `track_popularity`
- `track_duration_ms`

**Artista**
- `artist_name`
- `artist_popularity`
- `artist_followers`

**Álbum**
- `album_type` (album, single, compilation, Unknown)

**Classificações Derivadas**
- Segmentação de popularidade da faixa (Baixa, Média, Alta, Muito Alta)

---

## 🧪 6. Qualidade e Governança dos Dados
Foram aplicadas diversas práticas de qualidade e governança, incluindo:
- Tratamento explícito de valores nulos;
- Padronização de valores categóricos fora do domínio esperado;
- Conversão segura de tipos numéricos com fallback para valores padrão;
- Uso de Delta Lake para versionamento, consistência e confiabilidade dos dados;
- Separação clara de responsabilidades entre camadas do pipeline.

---

## 📊 7. Análises e Principais Resultados
As análises exploratórias realizadas na camada Gold responderam às seguintes questões:

1. A popularidade do artista influencia a popularidade da faixa?
2. Artistas com mais seguidores lançam faixas mais populares?
3. Singles são, em média, mais populares do que faixas de álbuns?
4. O conteúdo explícito afeta a popularidade da faixa?
5. Existe uma faixa de duração mais comum entre músicas populares?
6. Faixas muito populares (“hits”) possuem características diferentes do restante do catálogo?

- A popularidade do artista influencia fortemente a popularidade da faixa, especialmente para músicas muito populares;
- O número de seguidores, isoladamente, não se mostrou determinante para o sucesso de uma música;
- Faixas lançadas em álbuns apresentam, em média, maior popularidade do que singles;
- Músicas com conteúdo explícito tendem a ter maior popularidade média;
- Há uma preferência clara por músicas com duração entre **2 e 4 minutos**;
- Observa-se uma concentração significativa de faixas com popularidade alta, indicando padrões recorrentes entre os “hits”.

**Os resultados apresentados fornecem apenas indícios iniciais e não devem ser interpretados como conclusões definitivas. Uma aplicação prática em ambiente corporativo exigiria análises mais detalhadas e aprofundadas, que estão fora do escopo deste projeto.**

---

## 🏁 8. Atingimento dos Objetivos
Os objetivos do projeto foram plenamente atingidos. O pipeline Medallion foi implementado com sucesso, garantindo dados organizados, limpos e governados, além de viabilizar análises consistentes sobre os fatores que influenciam a popularidade musical no Spotify.

---

## 🚀 9. Conclusão
Este MVP demonstra a aplicação prática de conceitos fundamentais de Engenharia de Dados, como arquitetura Medallion, uso de Delta Lake e pipelines analíticos em Spark. Os resultados evidenciam que o sucesso musical é multifatorial, combinando atributos do artista, formato de lançamento e características da faixa.  

Como evolução futura, o projeto pode ser expandido com:
- Orquestração do pipeline;
- Incremental loading;
- Métricas de qualidade automatizadas;
- Modelagem dimensional em star schema para BI.
