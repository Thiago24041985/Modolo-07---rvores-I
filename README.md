# 🌳 Módulo 07 - Árvores de Decisão e Pré-processamento para Scikit-Learn

Repositório dedicado aos estudos e exercícios práticos do **Módulo 07** do curso **Profissão: Cientista de Dados (EBAC)**, focado na preparação estrutural de dados (*Data Preprocessing*), construção de metadados e codificação de variáveis (*One-Hot Encoding*) para treinamento de modelos no **Scikit-Learn**.

## 💡 Como elaborei este projeto

Desenvolvi este projeto em Jupyter Notebook preparando a base de concessão de cartões de crédito (`demo01.csv`) para algoritmos de Machine Learning:

1. **Auditoria Inicial e Análise da Variável Resposta (`mau`):**
   * Carreguei o dataset com **16.650 registros e 16 variáveis** e validei a integridade dos dados com `df.info()` e `df.isna().sum()`, confirmando a ausência de valores faltantes.
   * Analisei o desbalanceamento da variável alvo (`mau`), identificando **97,66% de bons pagadores (`False`)** e **2,34% de maus pagadores (`True`)**, com visualização via `sns.countplot()`.
2. **Construção Automatizada de Metadados:**
   * Criei um DataFrame auxiliar (`info_df`) percorrendo dinamicamente as colunas da base para mapear o nome de cada variável, seu tipo de dado (`dtypes`) e a cardinalidade (`qtd_categorias`, via `len(df[col].unique())`), facilitando a distinção entre variáveis contínuas, binárias e categóricas nominais.
3. **Codificação de Variáveis Categóricas (*Dummy Variables*):**
   * Identifiquei as variáveis qualitativas e apliquei `pd.get_dummies()` para converter atributos textuais (`sexo`, `posse_de_veiculo`, `posse_de_imovel`, `tipo_renda`, `educacao`, `estado_civil` e `tipo_residencia`) em colunas binárias numéricas.
   * Separei a matriz contendo apenas os atributos numéricos e codificados, eliminando as colunas originais em formato texto (`str`/`object`) para deixar o dataset pronto para entrada no **Scikit-Learn**.

## 🛠️ Tecnologias Utilizadas
* **Python 3**
* **Pandas** (auditoria de schema, criação de metadados e `pd.get_dummies`)
* **NumPy** (verificação de tipos numéricos e booleanos)
* **Seaborn & Matplotlib** (análise visual da distribuição da variável alvo)
* **Scikit-Learn** (preparação da matriz de atributos para Árvores de Decisão)




TAREFA 02 -  # 🌳 Módulo 07 - Árvores de Decisão e Modelagem de Risco de Crédito

Repositório dedicado aos estudos e projetos práticos do **Módulo 07** do curso **Profissão: Cientista de Dados (EBAC)**, abrangendo o ciclo completo de preparação de dados e modelagem preditiva com **Árvores de Decisão (`DecisionTreeClassifier`)** no **Scikit-Learn** aplicado à concessão de cartões de crédito.

## 💡 Como elaborei este projeto

Estruturei o desenvolvimento em dois notebooks progressivos, conectando o pré-processamento estrutural da base ao treinamento, visualização e avaliação crítica do modelo:

### 1. Pré-processamento e Engenharia de Atributos (`Tarefa 01`)
* **Auditoria e Diagnóstico de Desbalanceamento:** Carreguei a base `demo01.csv` (**16.650 registros e 16 variáveis**), validei a ausência de missings (`df.isna().sum()`) e identifiquei o forte desbalanceamento da variável alvo (`mau`: **97,66% bons pagadores** vs. **2,34% maus pagadores**).
* **Construção de Metadados:** Criei um DataFrame dinâmico (`info_df`) mapeando nomes, tipos de dados (`dtypes`) e cardinalidade (`qtd_categorias`) de cada atributo.
* **Codificação (*One-Hot Encoding*):** Converti as variáveis qualitativas em colunas binárias via `pd.get_dummies()`, removendo as variáveis textuais originais para gerar uma matriz puramente numérica (`variaveis_dummy.csv`) compatível com o **Scikit-Learn**.

### 2. Treinamento, Poda e Avaliação da Árvore de Decisão (`Tarefa 02`)
* **Separação Treino/Teste:** Dividi a matriz de atributos (`X`) e a variável resposta (`y`) utilizando `train_test_split()`.
* **Modelagem e Visualização da Árvore:** Treinei um classificador `DecisionTreeClassifier` e gerei a representação gráfica das regras de decisão com `plot_tree()`, avaliando a **Matriz de Confusão** (`ConfusionMatrixDisplay`) com rótulos de negócio (`Aprovados` e `Reprovados`) e a **acurácia** (~97,9% no treino).
* **Controle de Complexidade (Poda / *Pruning*):** Ajustei hiperparâmetros de regularização (`max_depth=10` e `min_samples_leaf=5`) para evitar *overfitting* e analisei a distribuição das predições na base de teste (onde menos de 1% dos proponentes foram classificados como maus pagadores).
* **Análise Crítica de Baseline e Desbalanceamento:** Realizei um experimento classificando todos os proponentes como bons pagadores (`False`), demonstrando na prática a limitação da métrica de acurácia isolada (~97,7%) em bases altamente desbalanceadas e a necessidade de métricas complementares ou técnicas de balanceamento.

## 🛠️ Tecnologias Utilizadas
* **Python 3**
* **Pandas & NumPy** (auditoria de schema, criação de metadados, `pd.get_dummies` e manipulação de arrays)
* **Scikit-Learn** (`train_test_split`, `DecisionTreeClassifier`, `plot_tree`, `accuracy_score`, `ConfusionMatrixDisplay`)
* **Matplotlib & Seaborn** (visualização exploratória e plotagem das árvores e matrizes de confusão)
* **Jupyter Notebook / Google Colab**


