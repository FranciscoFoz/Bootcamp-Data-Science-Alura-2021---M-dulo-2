

# Bootcamp Data Science Alura 2021 - Módulo 2
# Imunizações para Febre Amarela no Brasil: Uma análise dos casos entre 2019/2020-2021

<img src="https://independente.com.br/wp-content/uploads/2021/04/Vacina-contra-a-febre-amarela-1-696x464.jpg" height="600" width="1000"></a>  
Fonte da foto: [Grupo Independente](https://independente.com.br/confirmacao-da-presenca-de-virus-causador-da-febre-amarela-em-areas-silvestres-reforca-importancia-da-vacina-contra-a-doenca/) 
  


Elaborado por Francico Foz

<a href="https://img.shields.io/badge/author-gustavolq-blue.svg)](https://www.linkedin.com/in/francisco-tadeu-foz/" target="_blank"><img src="https://img.shields.io/badge/-LinkedIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a>  

---

Olá! 

Neste repositório você encontrará o meu projeto do módulo 2 do Bootcamp Data Science 2021 da [Alura](https://www.alura.com.br/).

Durante todo o Bootcamp irei mergulhar no oceano da Ciência de Dados a partir de dados reais da área da saúde em 6 módulos.



## Projeto 

Os dados propostos inicialmente no Bootcamp foi dos de [Imunizações](https://datasus.saude.gov.br/acesso-a-informacao/producao-hospitalar-sih-sus//)  do [Tabnet - DATASUS](https://datasus.saude.gov.br/informacoes-de-saude-tabnet/).


Você poderá encontrar o notebook completo [aqui](https://colab.research.google.com/drive/1EARIJqxlCzOMej80W9SzkwSiKuEstt6O?usp=sharing)

## Introdução

A febre amarela é uma doença viral transmitida pela picada de mosquitos
infectados a humanos e primatas não humanos (macacos). 

Ela possui dois ciclos de transmissão: 


*   Silvestre (transmissão em área rural ou floresta)
*   Urbana

Durante os meses de **dezembro** a **maio** é período de maior frequência da doença, devido ao maior índice de chuvas por conta da proliferação dos mosquitos.

A **vacina** é a principal ferramenta de prevenção e controle da febre amarela. 

O Sistema Único de Saúde (SUS) oferece a vacina contra febre amarela para a população. 

Desde abril de 2017, o Brasil adota o esquema vacinal de apenas uma dose durante toda a vida, sendo que a pessoa que recebeu uma dose da vacina antes de completar 5 anos, está indicada a dose de reforço, independentemente da idade que tiver. 

> Fonte: [Secretaria do estado de Saúde](https://www.saude.mg.gov.br/febreamarela).



Para haver uma maior controle, são realizadas vigiâncias em torno dos casos de febre amarela em humanos e em primatas não humanos (PNH).

São passadas por análises até averiguar os casos confirmados.

De acordo com os boletins epidemiológicos da Secretária de Vigilância em Saúde do Brasil: 
*   [Volume 51, Nº 46](https://www.gov.br/saude/pt-br/assuntos/media/pdf/2020/dezembro/09/boletim_epidemiologico_svs_46.pdf)
*   [Volume 52, Nº 31](https://www.gov.br/saude/pt-br/media/pdf/2021/agosto/30/boletim_epidemiologico_svs_31.pdf)


Entre julho de 2019 e junho de 2020, tivemos:    

> 19 casos confirmados de Febre Amarela em humanos, sendo **17 em Santa Catarina (89%)**

> 390 casos confirmados de Febre Amarela em PMH, sendo **88 em Santa Catarina (22,5%) e 298 no Paraná (76,4%).**

Entre julho de 2020 e abril de 2021, tivemos:    


> 5 casos confirmados, **todos no estado de Santa Catarina**.

> 218 casos confirmados de Febre Amarela em PMH, sendo **17 no Paraná (7,8%), 47 no Rio Grande do Sul (21,6%) e 127 em Santa Catarina (58,25%).**

Além dos dados podemos observar que de fato há uma tendência do vírus estar se deslocando no sentido do sul já há alguns anos. Conforme vemos na figura seguinte:  

#### **Distribuição dos casos humanos e/ou em PNH confirmados de 07/2014 a 06/2020**

![CasosConfirmados_FebreAmarela_2014-2020.png](https://github.com/FranciscoFoz/Projeto_Modulo2_Bootcamp_Data_Science_Alura_2021/raw/main/Imagens/CasosConfirmados_FebreAmarela_2014-2020.png)

> Legenda: </p>
> (ACRV) Área Com Recomendação de Vacinação </p>
> (ASRV) Área Sem Recomendação de Vacinação 

> Fonte: [Volume 52, Nº 31](https://www.gov.br/saude/pt-br/media/pdf/2021/agosto/30/boletim_epidemiologico_svs_31.pdf)

### <font color= MediumSpringGreen> Cobertura Vacinal </font>

De acordo com a [RIPSA (Rede Internacional de Informações para Saúde)](http://tabnet.datasus.gov.br/tabdata/livroidb/Com2007/Com_F13.pdf), este é um índice calculado através do número de doses aplicadas, dividido pelo número total da população alvo e multiplicado por 100, em uma área e tempo considerados.

<img src="https://github.com/FranciscoFoz/Projeto_Modulo2_Bootcamp_Data_Science_Alura_2021/raw/main/Imagens/Cobertura_Vacinal_Formula.png" width="600"/>

A população alvo para a imunização da febre amarela no Brasil sofreu alteração no ano de 2020, quando todos os municípios da nação passaram a fazerem parte da área de recomendação e atualizaram as indicações de vacina. 

Desta forma se ampliou o quadro geral da população alvo:

<img src="https://github.com/FranciscoFoz/Projeto_Modulo2_Bootcamp_Data_Science_Alura_2021/raw/main/Imagens/Populacao_Alvo.png" width="600"/>

> [Fonte](https://www.ufrgs.br/telessauders/perguntas/qual-recomendacao-para-vacinacao-contra-febre-amarela/)

De acordo com a [Organização Pan-Americana da Saúde (OPAS)](https://www.paho.org/pt/node/40) é importanto vacinar **80%** ou mais da população em risco, entretanto ela tem recomendado que os países das Américas garantam pelo menos **95%** da população que vive nesta área. 


### <font color= MediumSpringGreen> Projeto </font>

Esta análise pretende explorar os dados de **imunizações** para febre amarela, nas UFs e municípios que tiveram casos confirmados no período entre jul/2019 - 2021.


>  *Delimitou-se a partir do ano de 2019 devido aos dados serem semestrais e estarem entre 2019 e 2020. Além de um melhor entendimento do cenário atual de vacinação nos estados selecionados.*



A análise será realizada através do entendimento dos seguintes dados:

**1. Cobertura vacinal por UF com casos confirmados de Febre Amarela**
  *   Número da cobertura vacinal para cada ano entre 2020-2021

**2. Cobertura vacinal por municípios em UF com casos confirmados de Febre Amarela**
  *   Número da cobertura vacinal para cada município e ano entre 2020-2021

### <font color= MediumSpringGreen> Questionamentos </font>

A partir destes dados, procuro entender os seguintes questionamento
 
  *   Como foi a cobertura vacinal para os estados que atualmente estão afetados de 2009-2019?
  *   Como foi a cobertura vacinal para os estados que atualmente estão afetados em 2020-2021?
  *   Qual é a distribuição da cobertura vacinal dos municípios destes estados em 2020 e 2021?
  *   A cobertura vacinal dos municípios afetados em 2020 e elevou em 2021?
  *   Qual é a quantidade dos municípios, dos estados afetados em 2021 que estão abaixo do mínimo de 80% de cobertura vacinal?
  *   Quais são estes municípios? 


### <font color= MediumSpringGreen> Objetivos </Font>

*   Explorar os dados atuais  de cobertura vacinal, das imunizações de febre amarela de acordo com os estados afetados.
*   Verificar a distribuição das coberturas vacinais ao decorrer dos municípios destes estados.
*   Averiguar a cobertura vacinal dos municípios afetados em 2020 e sua modificação em 2021.
*   Entender quais os municípios estão com coberturas vacinais abaixo de 80% em 2021.

### <font color= MediumSpringGreen> Hipóteses </Font>

Diante dos boletins lidos inicialmente, boletins de anos anteriores e das informações adquiridas durante o primeiro módulo do bootcamp, deduzo que: 

*    O número de coberturas vacinais tenha tido um pico em 2019 devido ao surto de casos em 2017/2018.
*    Houve uma queda em 2020, por conta da modificação e ampliação do público alvo e também por conta da crise do COVID-19. Entretanto é possível que tenha subido em 2021, principalmente nos estados afetados e principalmente no estado de SC onde ocorreu o maior índice de casos em humanos. 

*   Deduzo que os municípios com baixa cobertura vacinal em 2021 não são os que foram afetados em 2020.

### Considerações Finais

Foi possível averiguar que os dados de cobertura vacinal em estados onde foram afetados em 2020 e 2021 estão menores em 2021.

Principamente em estados da região sul, onde se encontra atualmente a maior concentração de casos em PNH (primatas não humanos) e humanos.

O que é uma notícia grave, diante de uma doença que tem como a vacina o principal combate.

É possível que este quadro seja devido:
*    Transição do vírus ao decorrer dos anos para a região sul
*    Crise do COVID-19, no qual diminuiu o volume de pessoas vacinadas no período
*    Movimento de grupos anti-vacina, no qual nos últimos anos vem tomando frente em redes sociais
*    Ampliação para o país inteiro da população alvo, no qual diminui assim a cobertura vacinal local proporcionalmente.

Estamos em novembro de 2021 e é importante termos campanhas de vacinação, devido a época de maior incidência da doença chegando.

Para que desta forma, o vírus seja controlado e não cause danos maiores a população.

