# Trabalho 2 — Projeto final

**Curso:** Redes Neurais e Aprendizado Profundo (EMA9824)
**Semestre:** 2026/2
**Turmas:** Integral e Noturno
**Lançamento:** 07/10/2026
**Peso:** 40 % da nota final
**Formato:** grupos de 2 ou 3
**Apresentação:** 19/11/2026

**O que entregar:**

1. o código, executável de ponta a ponta;
2. um artigo de quatro páginas em PDF, no modelo SBC ou IEEE;
3. uma apresentação de 10 minutos, com arguição de 3 a 5 minutos.

O artigo, o código e os slides são entregues pelo Classroom até 19/11/2026; a apresentação é em aula, em 19/11/2026.

---

## 1. Objetivo

Resolver um problema com redes neurais e aprendizado profundo, do início ao fim: escolher o problema, obter os dados, construir a solução, medir se ela funciona e comunicar o resultado em artigo e em seminário.

A novidade deste trabalho não é o método, já praticado nas atividades semanais e no T1. É o problema: delimitá-lo, decidir a métrica que o representa, enfrentar os dados como eles vêm e fazer a solução funcionar de ponta a ponta. O rigor de medida já conhecido — um fator por vez, sementes repetidas, dispersão declarada, teste consultado ao final — acompanha o trabalho como hábito, e não como uma lista nova de exigências.

O tema é livre. A seção 7 traz vinte e uma sugestões; nenhuma é obrigatória, e um tema próprio é bem-vindo.

## 2. Entregas e marcos

O trabalho tem três marcos. Os dois primeiros são curtos e existem para evitar que um grupo descubra na última semana que o conjunto de dados não serve ou que o modelo não treina.

| # | Data | O que se entrega | Extensão |
|---|------|------------------|----------|
| M1 | 22/10 | Proposta, nos sete campos da seção 7.1 | 1 página |
| M2 | 05/11 | Baseline rodando: uma curva de treino e validação, o valor da métrica e o tempo de execução | 1 figura + 1 parágrafo |
| M3 | 19/11 | Artigo (4 páginas, modelo SBC ou IEEE) e código | — |
| — | 19/11 | Apresentação e arguição, em aula | 10 + 3 a 5 min |

Os marcos M1 e M2 não recebem nota em separado, mas a sua ausência é considerada na avaliação: eles registram que o trabalho se desenvolveu ao longo das quatro semanas.

## 3. O que o projeto precisa ter

1. **Dados reais**, de origem pública e declarada, com a licença verificada.
2. **Um baseline medido pelo grupo**, isto é, o método mais simples que resolveria o problema de forma aceitável, avaliado nas mesmas condições do modelo final — mesma divisão, mesma métrica, mesmo pré-processamento. Ele pode não ser uma rede neural: uma regressão logística, uma árvore de decisão, a média sazonal de uma série, a classe majoritária. A sua função é exigir do grupo a demonstração de que a rede profunda se justifica. Quando implementar o ponto de comparação for, por si só, um projeto — um detector publicado, por exemplo —, utilize o modelo pré-treinado disponível e declare essa escolha.
3. **Uma melhoria, justificada antes de ser medida.** Declare o que se espera que ela altere, e por quê; em seguida, meça. Uma melhoria que não funcionou, acompanhada da investigação da causa, vale mais que três alterações simultâneas coincidentes com um número maior.
4. **O método já praticado na disciplina:** um fator por vez, três conjuntos, ao menos três sementes com média e dispersão, e o conjunto de teste consultado uma única vez.
5. **Escopo compatível com o prazo.** Não há teto de computação imposto pela disciplina (seção 6.1), mas há calendário: o projeto precisa estar medido e escrito até a entrega. Se um treino não couber no tempo disponível, reduza o problema — menos classes, imagens menores, um recorte do conjunto — e declare a redução no artigo.

**Recomendado, não exigido:** procure um artigo que trate do mesmo problema ou do mesmo conjunto de dados e situe o resultado obtido em relação ao dele. Esse número da literatura não substitui o baseline do item 2: ele vem de outra divisão, outro orçamento e, às vezes, outra forma de calcular a métrica, de modo que serve para situar o trabalho, não para medir a melhoria. Não se espera igualar o valor publicado — e sim saber dizer a que distância se está e por quê. Uma frase como "o artigo de referência obtém 94 % treinando a rede inteira; obtivemos 88 % com o tronco congelado" vale mais que qualquer número isolado.

## 4. O artigo

Quatro páginas, incluindo figuras e referências, no modelo SBC ou IEEE para artigos, disponível em LaTeX e em Word; recomenda-se o LaTeX. Estrutura esperada:

| Seção | O que contém |
|-------|--------------|
| Título, autores, resumo | O resumo diz o problema, o que foi feito e o número principal |
| 1. Introdução | A pergunta, por que ela importa, o que o artigo conclui |
| 2. Dados | Origem, licença, tamanho, divisão em treino/validação/teste, pré-processamento |
| 3. Método | O baseline, a arquitetura escolhida e a melhoria proposta, com a justificativa |
| 4. Experimentos | O que foi variado, quantas sementes, como a métrica foi medida |
| 5. Resultados | Tabela com média ± dispersão, figuras com eixos rotulados, comparação com o baseline |
| 6. Limitações e conclusão | O que o experimento não mostra, e o que faria com mais tempo |
| Referências | No padrão da ABNT, IEEE ou da SBC |

Três regras herdadas do T1:

- nenhuma afirmação de desempenho sem o número que a sustenta;
- nenhuma diferença reportada sem a dispersão ao lado;
- o conjunto de teste consultado uma única vez, ao final.

## 5. A apresentação

Dez minutos por grupo, mais 3 a 5 minutos de arguição, em 19/11. O grupo decide quantos integrantes apresentam; a arguição é individual, e é nela que se verifica a participação de todos.

Divisão sugerida dos 10 minutos:

- problema e dados (2);
- método e baseline (3);
- resultados (4);
- limitações e conclusão (1).

Recomenda-se o uso de 8 a 10 lâminas. A apresentação expõe o resultado e o caminho até ele; o detalhe permanece no artigo.

## 6. Reprodutibilidade

O código é avaliado por executar, e não por elegância. Entregue:

- um README com o comando que reproduz a figura principal do artigo;
- a especificação do ambiente de trabalho (`requirements.txt`, `uv.lock` ou a célula de instalação do Colab);
- a semente fixada e o número de execuções registrado;
- o script ou a célula que obtém os dados a partir da fonte original, sem arquivos grandes no repositório.

### 6.1 Onde treinar

Há mais de um caminho, e o grupo declara no M1 qual pretende usar. Nenhum tema exige GPU paga, e nenhum está limitado a CPU:

- **A máquina do grupo**, se algum integrante tiver GPU.
- **Os computadores do laboratório da disciplina**, com GPU, nos horários combinados.
- **Google Colab**, para desenvolver o código e para experimentos curtos: a sessão gratuita dura no máximo 12 horas e os recursos não são garantidos, de modo que a sessão deve ser tratada como descartável.
- **Kaggle Notebooks**, para treinos longos: oferece GPU com cota semanal e sessões longas. As cotas e os limites de armazenamento mudam; confira a documentação antes de planejar o treino.

Em qualquer caminho, o conjunto de dados precisa caber no armazenamento disponível, e o ambiente utilizado é declarado no artigo. Duas práticas protegem o trabalho de uma sessão interrompida e evitam repetições desnecessárias de treino:

- **Checkpoints.** Salve os pesos a cada época, ou a cada melhora da validação, em disco persistente, e faça o código retomar do último ponto.
- **Parada antecipada.** Interrompa quando a validação não melhora há algumas épocas, guardando o melhor estado. Além de regularizar, impede que um treino consuma horas para repetir o mesmo resultado.

Os recursos não entram na nota. Um grupo com GPU dedicada e outro que executou tudo no Colab são avaliados pelo mesmo critério: a qualidade da solução e da medida. Modelo maior não rende pontos.

## 7. Temas sugeridos

O tema é livre, e um problema trazido pelo grupo — do estágio, da iniciação científica, de um interesse pessoal — é bem-vindo. Os temas abaixo existem para quem prefere partir de um problema já delimitado; adaptá-los, trocando o conjunto de dados ou a métrica, também é aceito. Cada linha traz o problema e onde obter os dados; todas as fontes foram conferidas em 07/10/2026.

O que decide se a solução serve — métrica, limiar, orçamento, horizonte — é escolha do grupo, declarada no M1 (seção 7.1).

### Bioinformática e genética

1. **Prever a estrutura secundária de uma proteína** a partir da sequência (hélice, folha ou alça). Hugging Face `proteinea/secondary_structure_prediction`, 10 792 sequências, 30 MB.
2. **Classificar a função biológica de uma proteína desconhecida**, com o ProtBERT ajustado ou com os seus vetores e um classificador por cima. Hugging Face, modelo `Rostlab/prot_bert`.
3. **Triar mutações de nucleotídeo único** entre benignas e patogênicas. ClinVar (NCBI), com as anotações públicas do registro.
4. **Identificar regiões promotoras em sequências de DNA** com uma CNN 1-D. genomic-benchmarks (Hugging Face `katielink/genomic-benchmarks`, 847 mil sequências, 9,7 MB).
5. **Prever a estabilidade de uma enzima mutada** a partir da estrutura 3-D gerada pelo ColabFold, com uma rede em grafo. Estruturas geradas pelo grupo; medidas de estabilidade de bases públicas de termoestabilidade. *(Avançado: exige GPU, tempo de geração das estruturas e um método — redes em grafo — que o curso não cobre.)*

### Visão computacional

6. **Classificar a gravidade da retinopatia diabética** em fotos de fundo de olho. APTOS 2019 (Kaggle), com transferência de aprendizado.
7. **Contar pragas em folhas de soja ou milho**, a partir de um detector pré-treinado ajustado ao conjunto do grupo. Conjuntos públicos de pragas (IP102 e similares).
8. **Reconhecer sinais estáticos de LIBRAS** e medir se o modelo funciona para uma pessoa que não apareceu no treino. Conjunto público de LIBRAS, ou gravado pelo grupo.
9. **Indicar quais vagas de estacionamento estão livres**, com o modelo treinado em um estacionamento e avaliado em outro. PKLot (UFPR), público.
10. **Identificar o estilo arquitetônico de prédios históricos** em fotos urbanas. Conjuntos públicos de estilos arquitetônicos (Kaggle).
11. **Detectar peça defeituosa treinando apenas com peças boas.** Defeitos em placas de circuito (Hugging Face `keremberke/pcb-defect-segmentation`, 198 imagens).

### Linguagem

12. **Moderar discurso de ódio em português**, ajustando o BERTimbau. HateBR (GitHub `franciellevargas/HateBR`; também no Hugging Face).
13. **Responder perguntas sobre um regulamento ou edital da universidade**, ajustando um modelo de linguagem com LoRA ou QLoRA — o tamanho depende da GPU disponível — e medindo o acerto em um conjunto de perguntas escrito pelo grupo antes do ajuste.
14. **Priorizar as reclamações que o atendimento consegue ler no dia.** B2W-Reviews01 (GitHub `americanas-tech`), 132 373 resenhas.
15. **Medir e reduzir o erro de transcrição de aulas em português (Whisper)**, comparando tamanhos de modelo e um ajuste leve ao vocabulário da disciplina. Common Voice em português, e áudio gravado pelo grupo.
16. **Ordenar notícias de saúde para checagem humana**, sem depender de pistas superficiais. Fake.br-Corpus (GitHub `roneysco`).

### Áudio, séries temporais e dados tabulares

17. **Prever a geração de energia solar de uma usina** a partir do histórico e de dados climáticos. Geração por usina, ONS (dados.ons.org.br).
18. **Emitir apenas os alertas de fraude que a equipe consegue investigar por dia.** Fraude em cartão de crédito (Kaggle, `mlg-ulb/creditcardfraud`), com classe raríssima.
19. **Reconhecer comandos de voz em português para automação residencial**, em ambiente ruidoso. Common Voice em português, ou gravações do grupo.
20. **Recomendar faixas musicais semelhantes a partir do áudio**, com vetores aprendidos. FMA — Free Music Archive, recorte `fma_small`.
21. **Prever internações por problema respiratório** a partir da qualidade do ar. DATASUS para internações e a rede de monitoramento de ar do estado.

### 7.1 O formato da proposta (M1)

A proposta de uma página, entregue em 22/10, tem sete campos. Eles valem tanto para os temas acima quanto para um tema próprio, e o seu preenchimento é o que dimensiona o projeto; por essa razão o M1 precede qualquer código.

1. **A pergunta**, em uma frase, cuja resposta ainda não se conhece.
2. **Os dados:** origem, licença, tamanho e divisão.
3. **O baseline:** o método simples que pode vencer a rede.
4. **A melhoria** e a razão pela qual se espera que funcione.
5. **As condições comparadas:** em que situações a comparação será repetida (tamanhos de treino, limiares, horizontes, níveis de ruído).
6. **O risco e o plano alternativo:** o que pode falhar, e qual a alternativa.
7. **O critério de empate:** qual resultado seria aceito como resposta negativa. Fixá-lo antes da medição é o que impede o relatório de procurar efeito onde não há.

#### Exemplo preenchido — tema 8 (vagas de estacionamento)

> **Pergunta:** um detector de vaga livre treinado em um estacionamento continua válido em outro, ou é preciso reanotar a cada instalação?
>
> **Dados:** PKLot (UFPR), 12 417 imagens de 1 280×720 de dois estacionamentos, em dias de sol, nuvem e chuva; os arquivos XML recortam cerca de 695 900 imagens de vagas individuais. Uso acadêmico, fonte pública.
>
> **Baseline:** classificador clássico sobre o recorte da vaga — média e variância de intensidade com regressão logística —, treinado e avaliado no mesmo estacionamento.
>
> **Melhoria:** CNN pequena sobre o recorte, com aumentação de brilho e contraste para enfrentar a variação de clima.
>
> **Condições comparadas:** treino em parking1 e teste em parking2, e o inverso; e, dentro do mesmo estacionamento, separação por condição de tempo (sol, nuvem, chuva). São quatro combinações, cada uma com três sementes.
>
> **Risco e plano alternativo:** o conjunto completo é grande e a preparação dos recortes consome tempo; começamos por um subconjunto de dias de cada condição e só ampliamos se couber no prazo.
>
> **Critério de empate:** se a queda ao trocar de estacionamento ficar dentro da dispersão entre sementes, a resposta é "o modelo transfere", e o trabalho está completo — não é preciso que a CNN vença o clássico para o projeto ter resultado.

## 8. Esclarecimentos

- **Composição dos grupos.** Podem ser entre dois e três integrantes. Grupos de um integrante são aceitos apenas em caso justificado, sem redução de escopo.
- **Tema próprio.** Permitido e incentivado, mediante aprovação no M1. Mudança de tema após o M1 deve ser comunicada; após o M2, raramente é viável.
- **Relação com o T1.** O T2 não pode ser continuação do T1: problema novo e conjunto de dados novo.
- **Modelos pré-treinados.** Permitidos, e em vários temas constituem a própria melhoria. Declare qual modelo, a sua procedência e o que foi efetivamente treinado.
- **Dados com pessoas.** Se o conjunto contiver imagens, voz ou texto de pessoas identificáveis, declare a licença e não republique os dados no repositório.
- **O conjunto de dados não serviu.** É uma ocorrência comum. Substitua-o até o M2 e registre no artigo o que levou à troca: isso é parte do método, e não uma falha.
- **Divisão do trabalho.** O artigo declara, em uma linha, a contribuição de cada integrante. Todos devem ser capazes de explicar o projeto inteiro na arguição.
