# Classificação com Redes Neurais usando Fashion MNIST (Classes Generalizadas)

Este projeto implementa um modelo de aprendizado profundo (Deep Learning) utilizando o **TensorFlow** e **Keras** para classificar imagens de vestuário da base de dados **Fashion MNIST**. O diferencial desta abordagem é o uso de **classes generalizadas** por região do corpo (como *chestwear*, *legwear*, *footwear*, *fullbodywear* e *accessory*), agrupando as 10 categorias originais do dataset.

---

## 🛠️ Tecnologias e Bibliotecas Utilizadas

* **Python**
* **TensorFlow / Keras** (para a criação, compilação e treinamento da rede neural)
* **NumPy** (para manipulação de arrays e dados numéricos)
* **Matplotlib** (para visualização de dados e gráficos de desempenho)

---

## 📊 Sobre o Conjunto de Dados (Fashion MNIST)

O **Fashion MNIST** é composto por 70.000 imagens em tons de cinza de baixa resolução ($28 \times 28$ pixels), divididas em 10 categorias de roupas e acessórios. Os valores dos pixels variam originalmente de $0$ a $255$. 

Neste projeto, as classes foram mapeadas para categorias generalizadas por região do corpo:
* `chestwear` (vestuário superior)
* `legwear` (vestuário inferior)
* `fullbodywear` (corpo inteiro)
* `footwear` (calçados)
* `accessory` (acessórios)

---

## 🚀 Arquitetura do Modelo

O modelo é uma Rede Neural sequencial (`tf.keras.Sequential`) composta por três camadas principais:
1. **`Flatten`**: Converte a matriz de imagem de $28 \times 28$ pixels em um vetor unidimensional de $784$ elementos.
2. **`Dense` (128 nós com ativação ReLU)**: Camada oculta densamente conectada para extração de características.
3. **`Dense` (10 nós com ativação Softmax)**: Camada de saída que retorna um vetor de probabilidades correspondentes às 10 classes.

---

## ⚙️ Configuração e Execução

### Pré-requisitos
Certifique-se de ter o Python instalado junto com as bibliotecas necessárias:

```bash
pip install tensorflow numpy matplotlib

### Passos principais do código:
1. **Carregamento dos dados:** O dataset é baixado diretamente através do `keras.datasets.fashion_mnist`.
2. **Pré-processamento:** Os valores dos pixels são normalizados para o intervalo entre $0$ e $1$ dividindo-os por $255.0$.
3. **Compilação:** O modelo utiliza o otimizador `adam`, a função de perda `sparse_categorical_crossentropy` e a acurácia como métrica de avaliação.
4. **Treinamento:** O modelo é treinado por 20 épocas utilizando dados de validação para monitorar a capacidade de generalização e evitar o *overfitting*.

---

## 📈 Resultados e Validação

Durante o treinamento, são avaliadas a acurácia e a perda (*loss*) tanto para o conjunto de treinamento quanto para o de validação. O uso de dados de validação é essencial para:
- Identificar o momento ideal de parada e evitar *overfitting* (memorização excessiva dos dados de treino).
- Garantir que o modelo consiga generalizar de forma correta para novas imagens nunca antes vistas.

---

## 📝 Autores
Desenvolvido por Melyssa, Gabriel, Marcelo, Lucas e Pedro como parte de estudos práticos em Inteligência Artificial e Deep Learning.
