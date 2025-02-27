# Trabalhos de IA - Classificação e Análise de Dígitos Manuscritos

Repositório contendo dois trabalhos de redes neurais convolucionais e análise de features para o dataset MNIST.

## 📚 Trabalho 1: Implementação de CNNs (LeNet e AlexNet)

### Objetivo
Implementar e comparar as arquiteturas LeNet e AlexNet para classificação de dígitos manuscritos do dataset MNIST.

### Principais Componentes
- **Dataset**: MNIST (60k imagens 28x28 em tons de cinza)
- **Arquiteturas**:
  - **LeNet**: 
    - 2 camadas convolucionais + pooling
    - 3 camadas totalmente conectadas
  - **AlexNet** (adaptada):
    - 5 camadas convolucionais com ReLU e MaxPooling
    - 3 camadas totalmente conectadas
    - Dropout para regularização

### Implementação
- Código desenvolvido no [Google Colab](https://drive.google.com/drive/folders/1NE70IVYdpitop1SFJoQ2TCFGfphsOKhv)
- Pré-processamento: Normalização de pixels (0-255 → 0-1)
- Parâmetros chave:
  - Taxa de aprendizado: 1e-3
  - Batch size: 64
  - Épocas: 10
  - Otimizador: Adam

### Resultados e Análise
| Métrica       |  CNN  |  LeNet  | AlexNet | 
|---------------|-------|---------|---------|
| Acurácia      |  99%  |   99%   |   99%   |
| Loss          | 0.396 |  0.047  | 0.0412  |

**Discussão**:
- AlexNet mostrou melhor performance devido à profundidade da rede
- Overcome do LeNet com aumento de épocas
- Justificativa de parâmetros: otimização via grid search

## 🔍 Trabalho 2: Análise de Features com Clustering

### Metodologia
1. **Feature Extraction**:
   - Remoção da última camada FC
   - Extração de vetores de 512 dimensões (penúltima camada)
   
2. **Redução Dimensional**:
   - t-SNE (3 componentes)
   
3. **Clustering**:
   - K-means (k=10)
   - Hierárquico Agglomerative (método ward)

### Principais Descobertas
- **Correlação Clusters-Classes**:
  - Acurácia de silhueta: 0.61 (K-means)
  - Cluster 3 mostra maior mistura (dígitos 3/8)
  
- **Exemplos Confusos**:
  - Casos analisados: dígitos 4 vs 9 (traço superior similar)
  - 5 vs 6 (curvatura ambígua)

### Ferramentas Utilizadas
- Scikit-learn (K-means, AgglomerativeClustering)
- Seaborn/Matplotlib para visualização
- PCA complementar ao t-SNE

## ⚙️ Como Executar
1. Clone o repositório:
```bash
git clone https://github.com/Gefft3/CNN4Classication.git