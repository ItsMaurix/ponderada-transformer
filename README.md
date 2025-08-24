# Percepções sobre o Tutorial de Transformer

## Pontos Positivos

### 1. **Boa didática**
- O tutorial segue uma progressão lógica, então começa com conceitos básicos e gradualmente constrói a arquitetura completa
- Cada componente é explicado individualmente antes de ser integrado ao modelo final
- As analogias (como a comparação da atenção com um dicionário) ajudam muito na compreensão

### 2. **Visualizações Muito Úteis**
- Os diagramas e gráficos facilitam enormemente o entendimento
- Os heatmaps de atenção no final são fascinantes - é incrível ver como o modelo "olha" para diferentes partes da frase
- Os gráficos de encoding posicional são bem esclarecedores

### 3. **Implementação Passo a Passo**
- Cada classe (BaseAttention, CrossAttention, etc.) é construída de forma modular
- O código é bem comentado e organizado, principalmente depois das alterações que o Jeff fez
- É possível ver como cada pedaço se encaixa no todo

### 4. **Boas Explicações Teóricas**
- A matemática por trás do positional encoding é bem explicada
- A diferença entre os tipos de atenção (self-attention, cross-attention, causal) fica clara

## Pontos Negativos e Limitações

### 1. **Complexidade**
- Mesmo com o autoestudo, a quantidade de conceitos novos é muito grande
- Seria útil ter mais analogias do mundo real, como a do dicionário

### 2. **Problemas de Compatibilidade**
- Tive que corrigir várias incompatibilidades entre TensorFlow e TensorFlow-text
- As versões das bibliotecas causam muitos problemas de instalação (ponto positivo para o professor Jefferson que corrigiu isso)

### 3. **Falta de Intuição Sobre Hiperparâmetros**
- O tutorial não explica muito bem por que escolher 4 layers, 8 heads, d_model=128, etc. Pra mudar isso sozinho tem que saber o que acontece por trás dos panos e eu senti falta de entender melhor o impacto desses parâmetros.

### 4. **Limitações Computacionais**
- O modelo demora muito para treinar, mesmo sendo pequeno, isso nos leva à comparação de CPU vs GPU.

- **CPU vs GPU**: Transformers fazem muitas operações matriciais paralelas (multiplicações de attention), e rodar isso em uma CPU é inviável, pois essas são operações ideais para GPU. Em CPU é impráticavel mesmo para essas três épocas que o tutorial deixou como default. Com com GPU, o tutorial prevê 1 hora, mas a única dispoinível era a T4 lá no Google Colab e, mesmo depois de 1h20 minutos, isso não tinha acabado, então optei por não rodar pela demora.