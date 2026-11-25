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
   * Filtrei as variáveis qualitativas e apliquei `pd.get_dummies()` para converter atributos textuais (`sexo`, `posse_de_veiculo`, `posse_de_imovel`, `tipo_renda`, `educacao`, `estado_civil` e `tipo_residencia`) em colunas binárias numéricas.
   * Consolidei o dataset final compatível com os requisitos de entrada do **Scikit-Learn**.

## 🛠️ Tecnologias Utilizadas
* **Python 3**
* **Pandas** (auditoria de schema, criação de metadados e `pd.get_dummies`)
* **NumPy** (verificação de tipos numéricos e booleanos)
* **Seaborn & Matplotlib** (análise visual da distribuição da variável alvo)
* **Scikit-Learn** (preparação da matriz de atributos para Árvores de Decisão)



TAREFA 02 - 
