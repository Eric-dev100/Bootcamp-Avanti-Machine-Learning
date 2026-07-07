# Atividade 02 (ATIV-02) - Programação em Python e Análise de Dados

### 1. Escreva uma função que receba uma lista de números e retorne outra lista com os números ímpares.
```python
def filtrar_impares(lista):
    return [num for num in lista if num % 2 != 0]

```

---

### 2. Escreva uma função que receba uma lista de números e retorne outra lista com os números primos presentes.

```python
def filtrar_primos(lista):
    def eh_primo(n):
        if n < 2:
            return False
        for i in range(2, int(n ** 0.5) + 1):
            if n % i == 0:
                return False
        return True

    return [num for num in lista if eh_primo(num)]

```

---

### 3. Escreva uma função que receba duas listas e retorne outra lista com os elementos que estão presentes em apenas uma das listas.

```python
def elementos_unicos(lista1, lista2):
    return list(set(lista1) ^ set(lista2))

```

---

### 4. Dada uma lista de números inteiros, escreva uma função para encontrar o segundo maior valor na lista.

```python
def encontrar_segundo_maior(lista):
    lista_unica = list(set(lista))
    if len(lista_unica) < 2:
        return None
    lista_unica.sort()
    return lista_unica[-2]

```

---

### 5. Crie uma função que receba uma lista de tuplas, cada uma contendo o nome e a idade de uma pessoa, e retorne a lista ordenada pelo nome das pessoas em ordem alfabética.

```python
def ordenar_por_nome(lista_pessoas):
    return sorted(lista_pessoas, key=lambda pessoa: pessoa[0])

```

---

### 6. Como identificar e tratar outliers em uma coluna numérica usando desvio padrão ou quartis?

Para identificar e tratar outliers, utilizo uma das duas abordagens estatísticas abaixo:

* **Abordagem por Quartis (IQR):**
Identifico o primeiro quartil (Q1) e o terceiro quartil (Q3) da coluna. Com isso, calculo o Intervalo Interquartil (IQR = Q3 - Q1). Os limites aceitáveis são definidos por:
* Limite Inferior = Q1 - 1.5 * IQR
* Limite Superior = Q3 + 1.5 * IQR
Qualquer valor que fique fora desse intervalo é classificado como um outlier.


* **Abordagem por Desvio Padrão (Z-Score):**
Calculo a média e o desvio padrão da coluna numérica. Defino como outliers os valores que estão muito distantes da média, geralmente acima ou abaixo de 3 desvios padrões (Z-Score > 3 ou < -3).
* **Tratamento:**
A forma de tratar depende do contexto. Posso remover essas linhas do DataFrame utilizando filtros booleanos do Pandas (caso sejam dados corrompidos ou erros de medição) ou substituir os valores discrepantes pela mediana da coluna para mitigar o impacto em modelos preditivos que são sensíveis a discrepâncias.

---

### 7. Como concatenar vários DataFrames (empilhando linhas ou colunas), mesmo que tenham colunas diferentes?

Para juntar múltiplos DataFrames, utilizo a função `pd.concat()`. O comportamento muda conforme o eixo escolhido no parâmetro `axis`:

* **Empilhar linhas (Vertical):** Utilizo `axis=0`. Se os DataFrames tiverem colunas diferentes, o Pandas inclui todas as colunas existentes no resultado final e preenche automaticamente com `NaN` as células dos DataFrames que não possuíam aquela coluna originalmente.
* **Empilhar colunas (Horizontal):** Utilizo `axis=1`. Ele faz o alinhamento dos registros combinando os índices das linhas.

```python
import pandas as pd

# Exemplo empilhando linhas e ignorando os índices antigos
df_final = pd.concat([df1, df2, df3], axis=0, ignore_index=True)

```

---

### 8. Utilizando pandas, como realizar a leitura de um arquivo CSV em um DataFrame e exibir as primeiras linhas?

Utilizo a função `pd.read_csv()` para carregar o arquivo para a memória e o método `.head()` para visualizar o topo da estrutura.

```python
import pandas as pd

df = pd.read_csv('seu_arquivo.csv')
print(df.head())

```

---

### 9. Utilizando pandas, como selecionar uma coluna específica e filtrar linhas em um "DataFrame" com base em uma condição?

É possível fazer isso aplicando uma indexação booleana para filtrar as linhas correspondentes à condição e, em seguida, especificando o nome da coluna desejada entre colchetes (ou utilizando o operador `.loc`).

```python
import pandas as pd

# Filtra linhas onde a Idade é maior que 25 e traz apenas a coluna 'Nome'
resultado = df[df['Idade'] > 25]['Nome']

```

---

### 10. Utilizando pandas, como lidar com valores ausentes (NaN) em um DataFrame?

Para manipular dados nulos (`NaN`), uso as duas principais abordagens da biblioteca:

* **Remoção:** Se os registros nulos forem poucos ou irrelevantes, utilizo o método `dropna()` para descartar as linhas ou colunas completas que contêm valores ausentes.
* **Preenchimento (Imputação):** Utilizo o método `fillna()` para substituir os valores nulos por um valor fixo, ou por métricas agregadas da coluna (como média ou mediana).

```python
import pandas as pd

# Removendo linhas com valores nulos
df_limpo = df.dropna()

# Substituindo os nulos de uma coluna específica pela sua respectiva mediana
df['Coluna'] = df['Coluna'].fillna(df['Coluna'].median())

```

```
