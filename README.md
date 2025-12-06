# Análise de Embeddings e Redução de Dimensionalidade

Este projeto foi desenvolvido como parte das atividades avaliativas da disciplina **IMD 3003 - Aprendizado de Máquina Não Supervisionado**, ministrada pelo professor **Silvan Ferreira da Silva Junior**.

O objetivo principal é explorar técnicas modernas de Processamento de Linguagem Natural (NLP) e Aprendizado Não Supervisionado para transformar textos em representações vetoriais e analisar sua estrutura semântica.

## 📋 Sobre o Projeto

O notebook implementa um pipeline completo de Ciência de Dados para análise textual, partindo de frases cruas até a visualização de clusters semânticos. O sistema é capaz de identificar automaticamente tópicos em um conjunto de dados não rotulado.

Os dados utilizados consistem em um corpus de frases mistas cobrindo quatro temas principais latentes:
1. **Culinária** (Ingredientes, receitas)
2. **Geografia** (Capitais, rios, montanhas)
3. **Finanças** (Investimentos, ações, economia)
4. **Inteligência Artificial** (Redes neurais, modelos, algoritmos)

## 🚀 Funcionalidades

O projeto está dividido nas seguintes etapas/seções:

### 1. Geração de Embeddings (BERT)
Utilização do modelo pré-treinado **BERT (`bert-base-uncased`)** para converter sentenças em vetores numéricos de 768 dimensões.
- **Técnica:** *Mean Pooling* (média da última camada oculta) para obter uma representação semântica rica da frase inteira, superior ao uso isolado do token `[CLS]`.

### 2. Redução de Dimensionalidade e Visualização
Aplicação de três algoritmos distintos para projetar os dados em 2D e investigar a estrutura do *manifold*:
- **PCA (Principal Component Analysis):** Para visualizar a variância global dos dados.
- **t-SNE (t-Distributed Stochastic Neighbor Embedding):** Para focar na estrutura local e separação de clusters.
- **UMAP (Uniform Manifold Approximation and Projection):** Para um equilíbrio eficiente entre estrutura global e local.

### 3. Clusterização e Classificação Zero-Shot
Implementação de um classificador semântico sem necessidade de treino supervisionado (rótulos):
- **K-Means:** Agrupamento automático dos embeddings em 4 clusters.
- **Classificador:** Uma função que recebe um novo texto, gera seu embedding e infere a qual grupo temático ele pertence baseando-se na distância euclidiana para os centroides encontrados.

## 🛠️ Tecnologias Utilizadas

- **Python 3**
- **Transformers (Hugging Face):** Para o modelo BERT.
- **PyTorch:** Backend para processamento dos tensores.
- **Scikit-Learn:** Para PCA, t-SNE e K-Means.
- **UMAP-Learn:** Para a projeção UMAP.
- **Matplotlib:** Para visualização dos gráficos.

## 📦 Como Executar

Recomenda-se a execução no **Google Colab**

## 📊 Resultados Esperados
Ao final da execução, espera-se observar gráficos onde as frases de temas similares (ex: todas as frases sobre "comida") se agrupam visualmente em "ilhas" distintas, demonstrando que o modelo BERT capturou com sucesso a semântica dos textos e que as técnicas de redução (especialmente t-SNE e UMAP) preservaram essa estrutura.
