# Extração automática de palavras-chave em textos em Português
Benchmark de diferentes algoritmos de Extração de Palavras-chave (Keyword Extraction) em textos em Português.

### Experimentos
Os dados utilizados nos experimentos foram obtidos a partir de artigos científicos da Scielo Brazil. Estão na pasta /data e possuem a seguinte estrutura.

<img width="986" alt="image" src="https://user-images.githubusercontent.com/17749414/171950046-cf154d1d-1eb0-4885-b81e-bc1aaa425cda.png">

Foram utilizadas as seguintes métricas para avaliação dos experimentos: Mean Reciprocal Rank (MRR), Precision, Recall e F1. Visto que são utilizadas em trabalhos prévios da literatura (Hulth, 2003; Wan and Xiao, 2008; Mihalcea and Tarau, 2004; Hasan and Ng, 2014).

Essas métricas foram computadas utilizando diferentes rankings (k) dos resultados dos modelos (desempenho@k). Os valores de k utilizados variaram de 1 a 10. Por exemplo: precision@4 considera apenas as 4 primeiras palavras-chave retornadas pelo modelo para calcular a precisão.

A referência de alvo para comparação das palavras-chave relevantes são as palavras-chave que os autores de cada documento determinaram.

### Modelos comparados
Foram comparados os seguintes modelos de aprendizado não-supervisionado:
* Modelos estatísticos
  * FirstPhrases
  * YAKE [(Campos et al., 2020)](https://doi.org/10.1016/j.ins.2019.09.013)
* Modelos baseados em grafos
  * TextRank [(Mihalcea and Tarau, 2004)](http://www.aclweb.org/anthology/W04-3252.pdf)
  * SingleRank  [(Wan and Xiao, 2008)](http://www.aclweb.org/anthology/C08-1122.pdf)
  * TopicRank [(Bougouin et al., 2013)](http://aclweb.org/anthology/I13-1062.pdf)
  * PositionRank [(Florescu and Caragea, 2017)](http://www.aclweb.org/anthology/P17-1102.pdf)
  * MultipartiteRank [(Boudin, 2018)](https://arxiv.org/abs/1803.08721)

A implementação utilizada dos modelos pode ser encontrada no repositório [pke - python keyphrase extraction](https://github.com/boudinfl/pke).
