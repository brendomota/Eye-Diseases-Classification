# Proposta M1

## Classificação de Doenças Oculares em Imagens de Fundo de Olho: Uma Abordagem Comparativa com Transfer Learning

**Disciplina:** Redes Neurais e Aprendizado Profundo, 2026/2 · **Turma:** Noturno
**Integrantes:** Brendo Mota, Joelle Ramos, Rafael Medeiros

---

## 1. Pergunta

Uma CNN pré-treinada classifica imagens de fundo de olho em quatro classes (normal, catarata, retinopatia diabética e glaucoma) com ganho de macro-F1 maior que a dispersão entre sementes em relação a um classificador clássico, e esse ganho se mantém quando o conjunto de treino diminui?

## 2. Dados

Eye Diseases Classification (Kaggle, autor gunavenkatdoddi), com cerca de 4.200 imagens coloridas e aproximadamente 1.000 por classe, agregadas de fontes públicas distintas. Licença: Database: Open Database, Contents: © Original Authors.

O conjunto não traz divisão oficial. Primeiro removeremos duplicatas exatas e quase-duplicatas (hash de imagem), para evitar vazamento entre treino e teste. Depois faremos divisão estratificada de 70 % treino, 15 % validação e 15 % teste, fixada uma única vez, e o teste só será consultado ao final. O script baixa os dados direto do Kaggle, sem arquivos no repositório.

## 3. Baseline

Regressão logística (com Random Forest como variação) sobre atributos clássicos: média e variância de intensidade por canal de cor e histograma de cor, com imagens redimensionadas. Mesma divisão, mesma métrica e mesmo pré-processamento da rede.

## 4. Melhoria

MobileNetV2 pré-treinada na ImageNet, com camada final substituída e fine-tuning. Esperamos que supere o baseline porque os filtros pré-treinados capturam bordas e texturas (vasos, disco óptico, opacidade) que estatísticas globais de intensidade não capturam.

Em um segundo passo, mediremos o efeito isolado da aumentação de dados (flip, rotação, brilho e contraste), que deve reduzir o sobreajuste e a sensibilidade à iluminação, que varia entre as fontes de imagens.

## 5. Condições comparadas

Baseline e CNN são avaliados com 25 %, 50 % e 100 % do treino. Na CNN com 100 %, comparamos também com e sem aumento de dados (um fator por vez). Cada configuração roda com 3 sementes, e reportamos acurácia e macro-F1 em média ± desvio-padrão, mais a matriz de confusão do melhor modelo.

## 6. Risco e plano alternativo

**Risco 1:** as classes vêm de fontes diferentes, então a rede (ou até o baseline) pode distinguir a origem da imagem (cor, resolução, enquadramento) em vez da doença, inflando a métrica.
**Plano 1:** se o baseline simples já ficar muito alto, tratamos isso como resultado e investigamos com Grad-CAM e padronização de cor e tamanho.

**Risco 2:** tempo de treino.
**Plano 2:** imagens em 128×128 ou 224×224, checkpoints por época, parada antecipada e treino no Kaggle Notebooks ou Colab.

## 7. Critério de empate

Se a diferença de macro-F1 entre a CNN e o baseline, com 100 % do treino, ficar abaixo de 2 pontos percentuais ou dentro da dispersão entre as três sementes (a maior das duas), a resposta é negativa: a rede profunda não se justifica neste recorte. Do mesmo modo, a aumentação só é considerada eficaz se o ganho superar a dispersão.
