# Avaliação da Educação Doutoral no Espaço Lusófono: Um Modelo Multidimensional

Este repositório contém o código computacional e a estrutura de análise utilizados na investigação sobre as percepções docentes e os impactos das políticas de avaliação nos doutoramentos de Brasil, Portugal, Moçambique e Cabo Verde.


## 📝 Descrição

O objetivo deste código é processar dados de pesquisa (*survey*) e executar análises estatísticas multivariadas para validar um modelo multidimensional de qualidade na pós-graduação. A análise inclui:

* Tratamento e limpeza de dados (Imputação por média e tratamento de NAs).
* Estatística descritiva e visualização de dados.
* Testes de confiabilidade (Alpha de Cronbach).
* Análise Fatorial Exploratória (AFE) com rotação Oblimin.
* Testes de correlação não-paramétricos (Spearman).

## 🛠️ Tecnologias e Requisitos

As análises foram desenvolvidas em linguagem **R** (versão 4.x ou superior).

### Bibliotecas Necessárias

Para executar os scripts, instale os seguintes pacotes:

```r
install.packages(c("tidyverse", "psych", "rstatix", "arsenal", "corrplot", "readr", "here"))

```

## 📂 Estrutura de Arquivos

* `scripts/01_comandos.R`: Preparação do ambiente e importação.
* `scripts/02_analises_descritivas.R`: Geração de frequências e gráficos de média.
* `scripts/03_alpha_por_section.R`: Cálculo da consistência interna das escalas.
* `scripts/04_analise_fatorial.R`: Execução da AFE e diagramas fatoriais.
* `scripts/05_correlacao.R`: Matrizes de correlação e testes de hipóteses.
* `data/`: Pasta destinada ao arquivo CSV anonimizado.

## 🚀 Como Executar

1. Clone este repositório:
```bash
git clone https://github.com/teu-usuario/teu-repositorio.git

```


2. Abra o projeto no **RStudio**.
3. Certifique-se de que o arquivo de dados `Respostas ao formulário 1.csv` está na pasta `data/`.
4. Execute os scripts seguindo a ordem numérica sugerida.

**Nota Metodológica:** O script de limpeza utiliza a substituição de valores ausentes (NAs) pela média da coluna para preservar o tamanho da amostra na análise fatorial, conforme discutido no corpo do artigo.

## 🎓 Como Citar

Se utilizar este código ou parte dele na sua investigação, por favor, cite da seguinte forma:

**Citação do Software:**

> Sobrenome, Nome. (2024). Código de Análise Fatorial: Avaliação da Pós-Graduação no Espaço Lusófono (v1.0.0). Zenodo. [https://doi.org/10.5281/zenodo.XXXXXXX](https://doi.org/10.5281/zenodo.XXXXXXX)

**Artigo de Referência:**

> .
Para complementar o seu arquivo `README.md`, elaborei as seções de **Resultados Esperados** e o **Detalhamento Metodológico**, mantendo o tom objetivo e a estrutura técnica solicitada.

---

### ## Resultados Esperados

A aplicação deste modelo busca identificar dimensões latentes que definem a qualidade da educação doutoral nos países lusófonos. Espera-se:

* **Validação do Modelo:** Confirmação de uma estrutura multidimensional que agrupe indicadores de infraestrutura, supervisão, internacionalização e produção científica.
* **Perfis Comparativos:** Identificação de variações nas percepções docentes entre as realidades geográficas (Brasil, Portugal, Moçambique e Cabo Verde).
* **Subsídios para Políticas Públicas:** Dados que permitam refinar os critérios de avaliação da pós-graduação, indo além de métricas meramente quantitativas.

---

### ## Detalhamento dos Procedimentos Estatísticos

Os scripts contidos neste repositório seguem os seguintes critérios técnicos:

#### 1. Consistência Interna

A confiabilidade das escalas é mensurada pelo **Alfa de Cronbach** (). O código está configurado para considerar valores aceitáveis de , garantindo que os itens do questionário meçam o mesmo constructo de forma coerente.

#### 2. Análise Fatorial Exploratória (AFE)

Utilizada para reduzir o conjunto de variáveis e identificar os fatores subjacentes.

* **Critérios de Retenção:** Baseados em autovalores (eigenvalues) maiores que 1 e na análise do gráfico de sedimentação (*scree plot*).
* **Rotação Oblimin:** Aplicada por se assumir que as dimensões de qualidade na educação possuem correlação entre si.
* **Testes de Adequação:** O código executa o teste de **Kaiser-Meyer-Olkin (KMO)** e o **Teste de Esfericidade de Bartlett**.

#### 3. Teste de Correlação de Spearman

Dado que os dados de percepção (Escala Likert) possuem natureza ordinal e podem não apresentar distribuição normal, utiliza-se o coeficiente de correlação de postos de Spearman ():

Onde:

* : diferença entre os postos de cada observação.
* : número de observações.

---

### ## Como Contribuir

Se encontrar inconsistências nos scripts ou desejar sugerir melhorias na lógica de imputação de dados, sinta-se à vontade para abrir uma *Issue* ou enviar um *Pull Request*.


## 📄 Licença

Este projeto está licenciado sob a **licença MIT**. O uso é livre para fins acadêmicos, desde que citada a fonte.

**Contato:** Juan Carlos Teran Briceno / E-mail: juanfisico23@furg.br
