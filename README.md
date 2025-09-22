# Desafio-treinamento-de-Redes-Neurais-com-Transfer-Learning
# 🐱 vs 🐶 Classificação com Transfer Learning (VGG16) no Google Colab

Este projeto utiliza o dataset **Cats vs Dogs** da Microsoft, carregado diretamente via `tensorflow_datasets`, sem necessidade de downloads manuais. Foi estruturado em **22 blocos**, compatível com notebooks do Google Colab.

É realizada uma comparação entre um modelo **CNN simples** e outro usando **Transfer Learning com VGG16**. Todo o pipeline está pronto para execução: preprocessamento, treinamento, avaliação, e visualizações.
Tive que fazer algumas adaptações, e irei analisar os problemas que tive nas tentativas anteriores para poder aperfeiçoar.
---

## ✅ Principais Características

- ✅ **Dataset Cats vs Dogs** da Microsoft (via `tensorflow_datasets`)
- ✅ Imagens redimensionadas para **224x224**, compatíveis com VGG16
- ✅ Labels convertidas para **one-hot encoding**
- ✅ **Treinamento e validação** divididos automaticamente (85/15)
- ✅ Dois modelos: **CNN simples** e **VGG16 com Transfer Learning**
- ✅ **Plots funcionais** de loss/accuracy, sem KeyErrors
- ✅ Não é necessário **baixar nada manualmente**
- ✅ Código dividido em **22 blocos numerados**, pronto para Colab

---

## 📂 Estrutura do Notebook (Blocos)

| Bloco | Descrição |
|-------|-----------|
| 1     | Imports e configuração do ambiente |
| 2     | Carregamento do dataset Cats vs Dogs |
| 3     | Pré-processamento das imagens e labels (resize + one-hot) |
| 4     | Visualização de imagens do dataset |
| 5     | Criação de uma CNN simples (opcional, para comparação) |
| 6     | Treinamento da CNN simples |
| 7     | Plotagem dos gráficos de loss e accuracy da CNN |
| 8     | Avaliação da CNN simples no conjunto de validação |
| 9     | Criação do modelo com VGG16 (Transfer Learning) |
| 10    | Treinamento do modelo VGG16 |
| 11    | Comparação gráfica CNN vs VGG16 (val_loss e val_accuracy) |
| 12    | Avaliação do modelo VGG16 |
| 13-22 | (Espaço reservado para extensões futuras ou personalizações) |

---

## 📊 Exemplo de Resultados Esperados

### Acurácia de Validação
- CNN simples: ~70% após 5 épocas
- VGG16 (transfer learning): ~90% após 5 épocas

### Exemplo de Plot
| Loss | Accuracy |
|------|----------|
| ![Loss Plot](docs/loss_plot.png) | ![Accuracy Plot](docs/accuracy_plot.png) |

---

## 🔧 Requisitos

Você precisa apenas de um ambiente com **Google Colab** e internet:

- Python ≥ 3.7 (já incluído no Colab)
- TensorFlow ≥ 2.8
- `tensorflow_datasets` (já vem no Colab)
- Matplotlib (já vem no Colab)

---

## ▶️ Como Executar no Colab

1. Acesse o [Google Colab](https://colab.research.google.com/)
2. Crie um novo notebook.
3. Copie e cole os **22 blocos de código** na ordem.
4. Execute bloco por bloco para ver os resultados.

> 💡 Dica: Você pode dividir os blocos manualmente com `# %%` se estiver usando Colab com modo de células separadas.

---

## 📁 Dataset: Cats vs Dogs

- Fonte: [Microsoft Research](https://www.microsoft.com/en-us/download/details.aspx?id=54765)
- Acesso via: `tensorflow_datasets`
- Total de imagens: ~23.000
- Formato: JPEG
- Tamanhos variados (redimensionados para 224x224 neste projeto)

---

## 💡 Observações Técnicas

- O dataset é dividido automaticamente com `train[:85%]` e `train[85%:]`
- O modelo VGG16 usa pesos pré-treinados no ImageNet e **não é treinado novamente** (camadas congeladas)
- A saída é uma **softmax** com 2 classes (one-hot): `[1, 0]` para "cat", `[0, 1]` para "dog"
- O otimizador usado é o **Adam** com `learning_rate=0.0001` para o modelo VGG16
- As imagens são **normalizadas em [0,1]** para compatibilidade com o VGG16

---

## 📌 Extensões Sugeridas (Blocos 13 a 22)

- 🔍 Fine-tuning do VGG16 (descongelar algumas camadas)
- 📈 Callbacks como `EarlyStopping` e `ModelCheckpoint`
- 🧪 Avaliação com novas imagens
- 🧠 Grad-CAM para visualização de atenção
- 🧾 Exportação para `.h5` ou TensorFlow SavedModel

---

## 🧼 Limpeza e Boas Práticas

- Prefetch e batch configurados com `tf.data.AUTOTUNE`
- Shuffle e repeat para o treinamento
- Funções modulares para reuso

---

## 📝 Licença

Este projeto é open-source e pode ser utilizado livremente para fins educacionais e não comerciais.

---

## 🙋‍♀️ Contribuições

Sinta-se livre para abrir **issues**, sugerir melhorias ou enviar **pull requests**!

---

## ✉️ Contato

Para dúvidas ou sugestões:

- **Autor**: [Seu Nome Aqui]
- **Email**: seu.email@exemplo.com
- **GitHub**: [github.com/seuusuario](https://github.com/seuusuario)

---

