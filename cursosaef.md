---
title: "Curso R"
author: "Edgar de Souza Vismara"
date: "2018-08-27"
output:
  rmdformats::material:
    keep_md: true
    highlight: tango
---




<script>
   $(document).ready(function() {
     $head = $('#header');
     $head.prepend('<img src=\"logo2.jpg\" style=\"float: right;width: 130px;\"/>')
   });
</script>


# O software R

O R não é um "aplicativo" e sim uma plataforma de trabalho para realização de análises estatísticas. Como software, suas características principais são segundo [Batista](http://cmq.esalq.usp.br/wiki/doku.php?id=publico:tutoriais:r-relampago:start):

INTERFACE: o R é uma interface para análises de dados, criando um ambiente de trabalho.

INTERATIVIDADE: essa interface é interativa, isto é, você digita comandos e obtém os resultados.

FUNCIONAL: a linguagem S, a linguagem que se fala dentro do R, é uma linguagem funcional, isto é, todas as análises e ações são realizadas por funções.

ORIENTAÇÃO PARA OBJETOS: a linguagem S é uma linguagem de programação orientada para objetos, isto é, todas as entidades no ambiente R (dados, análises, gráficos, funções) são efetivamente objetos.

MODULAR: o R é composto por módulos, que são chamados de pacotes (packages). O pacote básico traz a funcionalidade necessária para as análises matemáticas e estatísticas mais usuais.

COLABORATIVO: o R é um esforço mundial de programação em código aberto.


## A linha de comando

Para nos familiarizarmos com a linha de comando vamos realizar algumas operações matemáticas e criar alguns objetos:

```r
1 + 2
2 * 3
5 / 2
1 - 2
10 ^ 2
sqrt(4)
a <- 10^2
a
a <- sqrt(4)
a
b <- 10^2
b
x = 2
x
y = 7
y
z = x * y
z
w = x - y
w
prod(1:10)
```

Vejamos alguns exemplos com objetos vetoriais:
A função **c** cria vetores


```r
k = c(1.3, -5, 6.7, 4.8)
k
x * k
m = c(0, 1, 1, 0, 1, 1)
m
m * k
n = c(0, 1, 1, 0)
n * k
```
<center>
<iframe width="560" height="315" src="https://www.youtube.com/embed/5BCrv-dqy94" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</center>



<center>
<iframe width="560" height="315" src="https://www.youtube.com/embed/56isD6fyKsU" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</center>

## A Área de Trabalho

A área de trabalho é seu ambiente de trabalho na sua sessão de trabalho atual. Para listar os objetos presentes na área de trabalho use a função **ls**. 


```r
ls()
```

Para apagar os objetos indesejados, utilize a função **rm**, fornecendo os objetos que você deseja apagar:


```r
rm(w, x, y, z)
ls()
```

## Salvando sua sessão


```r
save.image()
save.image(file="sessao1.RData")
```

## Encerrando a sessão no R.


```r
q()
```


## Retomando a sessão anterior.

Va na pasta onde você direcionou o arquivo e clique duas vezes em sessão1.RData.
Pronto vamos voltar ao trabalho. primeiro vamos checar área de trabalho.


```r
ls()
```
Viu só? Você não perdeu nenhum objeto!!!!

# Sintaxe básica de comandos

A sintaxe básica é a seguinte:

* função(argumento1=valor1,argumento2=valor2,...)

<center>
<iframe width="560" height="315" src="https://www.youtube.com/embed/KGI2vLMJ0yM" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</center>

Vamos ver um exemplo:

Para que um comando seja executado pelo R é necessário ser acompanhado de parênteses '()'. Compare esse comando


```r
ls()
ls
```

Veja que esse comando não necessita nenhum argumento.

Vamos agora usar a função que calcula a média:


```r
k
mean(x=k)
```

<center>
<iframe width="560" height="315" src="https://www.youtube.com/embed/kxRwAm8zGlo" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</center>

## Sintaxe da linguagem S

Como em toda linguagem, o R tem algumas regras básicas de sintaxe e grafia:

1. O nome de comandos/funções e objetos no R pode ser compostos de:
letras (minúsculas ou maiúsculas), números, e ponto (.).
2. Evite qualquer outro caractere especial, incluindo o espaço em branco.
3. O nome não pode ser iniciado por um número.
4. O R é sensível a caixa.

## Conseguindo ajuda sobre comandos

Para conseguir ajuda sobre um comando pode ser usada a função **help**:


```r
help(mean)
```

# Os pacotes no R

Pacotes são conjuntos de funcionalidades (funções e dados) distribuídos em conjunto para realizar tarefas específicas. Por exemplo, o pacotes agricolae carrega na sua área de trabalho (deixa disponível para uso) um conjunto de ferramentas para análises de dados estatística experimental. 


```r
install.packages("agricolae") #instala o pacote
```


```r
library("agricolae") #carrega o pacote
example(LSD.test)
```

# Criação e manipulação de objetos vetoriais e matriciais

## Vetores

Já criamos alguns vetores no R, vamos criar mais alguns:


```r
v1=c(2,3,4,5,6);v1
v2=c(2:6);v2
v3=c(1,1,1,1,1);v3
v4=rep(x=1,times=5);v4
v5=rep(1,5);v5
nomes=c("Antônio","Maria","Jonas");nomes
nomes=="Antônio"#Teste lógico
teste<-nomes=="Antônio";teste
class(nomes);class(teste);class(v1)
```
Indexando vetores:


```r
V1
```

```r
v1
v1[3]
v1[1:3]
nomes[1]
```

## Matrizes


```r
m1=matrix(data=v1,nrow=2,ncol=3,byrow=TRUE)
vetor=c(1:10);vetor
m1=matrix(data=vetor,nrow=5,ncol=2,byrow=TRUE);m1
m2=matrix(data=vetor,nrow=2,ncol=5,byrow=TRUE);m2
m3=matrix(data=vetor,nrow=2,ncol=5,byrow=FALSE);m3
m4=matrix(vetor,2,5,TRUE);m4
vetor2=matrix(vetor,1,10,TRUE);vetor2
class(m4);class(vetor2)
```

Indexando matrizes:


```r
m3
m3[1,3]
m4[2,5]
```

## Operações com matrizes


```r
m1*m1
m1%*%m2
m5=m1%*%m2;m5
m2%*%v1
m3%*%v1
t(v1)
t(vetor2)
v1%*%m1
t(m3)
```

```r
solve(m3)
solve(m5)
```

```r
m6=matrix(6:15,5,2,FALSE);m6
m7=m2%*%m6;m7
solve(m7)
```


# Leitura e manipulação de dados

## Lendo/importando os dados - A função **read.table**.

Para importar dados externos. Usamos a função **read.table**:

```r
altura.mudas <- read.table("/media/vismara/39F783BB7B8CCFB1/saef/altura-mudas.csv",header=TRUE,sep=";",dec=",")
altura.mudas$substrato=as.factor(altura.mudas$substrato)
```
Agora vamos visualizar os dados. O comando read.table importou o conjunto de dados "csv" e armazenou no objeto recém criado "altura.mudas". Esse objeto é da classe "data.frame". Desta forma para visualiza-lo basta digitar:


```r
altura.mudas
```

Como você deve ter observado, são muitas linhas para se visualizar. As vezes é mais conveniente olhar apenas as primeiras ou ultimas linhas do data.frame


```r
class(altura.mudas)
head(altura.mudas)
tail(altura.mudas)
```

## Lendo os dados usando o Rstudio 

No canto superior direito clique em "import Dataset" e selecione a opção "From text (base)..."

## O conceito de tidy data

1. Cada variável forma uma coluna.
2. Cada observação compõe um linha.
3. Cada tipo de unidade observacional forma uma tabela.

## Exemplo de dados digitados incorrtamente

Taxa de mortes por milhares em Virginia/EUA no ano de 1940


```r
mortes<-as.data.frame(VADeaths);mortes
```

## Indexando data.frames
 * Maneira 1 (como uma matriz):
 

```r
dim(altura.mudas)
altura.mudas[1,3]
altura.mudas[1,]
altura.mudas[1:6,]#igual a função head
```


```r
altura.mudas[,2]
altura.mudas[,2:4]
altura.mudas[,-1]
```

 * Maneira 2 (aproveitando as características da classe data.frame)

```r
names(altura.mudas)
```

```r
altura.mudas[1,"substrato"]
altura.mudas[,c("bloco","substrato","altura")]
altura.mudas$substrato
altura.mudas$altura
```
Agora vamos combinar as duas maneiras para aumentar nossa capacidade de indexação.
Supondo que queiramos apenas as informações do bloco 2.


```r
altura.mudas[altura.mudas$bloco==2,]
#deixo a segunda 
#lacuna vazia pois quero todas as colunas mas apenas 
#as linhas cuja coluna bloco tenha valor iguala dois

altura.mudas[altura.mudas$bloco==2,"altura"]
altura.mudas[altura.mudas$bloco==2 & altura.mudas$especie=="paineira" & altura.mudas$substrato<=4,]
```

<center>
<iframe width="560" height="315" src="https://www.youtube.com/embed/Q3t_q1XpKe8" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</center>

Alguns operadores lógicos:

| Sintaxe | Significado    |
|---------|----------------|
| >=      | Maior ou igual |
| <=      | Menor ou igual |
| ==      | Igual          |
| !=      | Diferente      |
| &       |  e             |
| |       |  ou            |

## Realizando Operações matemáticas com "data.frames".

Assim como com matrizes, podemos realizar operações matemáticas com data.frames. Essa operação é especialmente útil quando queremos alterar a escala de uma variável.
Podemos fazer isso adicionando uma nova variável ao data.frame ou alterando a variável existente


```r
altura.mudas$logaltura<-log(altura.mudas$altura)
altura.mudas[1,]
altura.mudas$altura<-altura.mudas$altura/100
altura.mudas[1,]
altura.mudas$altura<-altura.mudas$altura*100
```


# Descrevendo observações através de estatísticas


```r
summary(altura.mudas)
var(altura.mudas$altura)
sd(altura.mudas$altura)
```

## Alguns Gráficos Exploratórios


```r
h=hist(altura.mudas$altura)
```


```r
#Histograma caprichado

hist(altura.mudas$altura,breaks="Sturges",
main="Histograma de frequências",
ylab="Frequência Absoluta",xlab="Altura (cm)",col="gray",
labels=T,border="red", xlim=c(15,60))
```


```r
attach(altura.mudas)
plot(as.factor(substrato),altura)
```

## Exportando Gráficos


```r
jpeg("histograma.jpeg")

hist(altura.mudas$altura,breaks="Sturges",main="Histograma de frequências",ylab="Frequência Absoluta",xlab="Altura (cm)",col="gray",labels=T,border="red",xlim=c(0,120))#histograma

dev.off()
```

## Gráficos com ggplot2


```r
library(ggplot2)
ggplot(altura.mudas, aes(x=altura))+
  geom_histogram(color="red", fill="gray",breaks=h$breaks)+
  labs(title = "Histograma de Frequências", y="Frequência Absoluta",x="Altura (cm)") +
  scale_x_continuous(breaks=h$breaks)


ggplot(altura.mudas, aes(x=altura))+
  geom_histogram(color="red", fill="gray",breaks = h$breaks)+
  labs(title = "Histograma de Frequências", y="Frequência Absoluta",x="Altura (cm)")+
  scale_x_continuous(breaks=h$breaks)+
  facet_grid(especie ~ .)
```

# Modelos lineares (Delineamento de experimentos)

## Modelo simples

Para ajustar modelos lineares usando o método dos mínimos quadrados usamos a função **lm** (linear model). Esta função tem como argumentos básicos a descrição do modelo numa formula e a indicação do "data.frame" que contém as variáveis a serem relacionadas. 

Vamos ajustar um modelo usando o "data.frame" alturamudas.csv.

O modelo linear a ser ajustado é:

$$y_{i}=\mu + \epsilon_i$$
onde: $y_{i}$ é a altura da i-ésima muda, $\mu$ é a média das alturas e $\epsilon_i$ é o i-ésimo erro aleatório.


```r
modelo=lm(formula=altura~1,data=altura.mudas)
summary(modelo)
mean(altura.mudas$altura)
sd(altura.mudas$altura)
```

Este é o modelo linear mais simples que existe. para descrever a variável usamos apenas a media e o desvio padrão. Nele a média é constante. 

Nos delineamentos de experimentos testamos se a média é constante ou não, ou seja se temos algum **efeito** de algum tratamento.

## Delineamento inteiramente casualizado

No exemplo altura mudas podemos querer saber se existe efeito do substrato no crescimento em altura do tamboril, por exemplo. Neste caso teremos um experimento em DIC.

Para isso, ajustamos o seguinte modelo:

$$y_{ij}=\mu + \tau_j+\epsilon_{ij}$$
onde: $y_{ij}$ é a altura da i-ésima muda de tamboril crescendo no j-ésimo substrato, $\mu$ é a média das alturas, $\tau_{ij}$ é o efeito do j-ésimo substrato e $\epsilon_{ij}$ é o erro aleatório correspondente.

Façamos isto no R. Primeiro vamos extrair a espécie tamboril do data.frame "altura.mudas".


```r
tamboril=altura.mudas[altura.mudas$especie=="tamboril",]
```

Agora ajustamos o modelo:


```r
dic=lm(formula=altura~substrato,data=tamboril)
summary(dic)
```
Este modelo ajustado segue certos pressupostos, sendo os mais importantes: homoscedasticidade da variância e normalidade dos erros. Assim precisamos testar este pressupostos:


```r
shapiro.test(resid(dic))#teste de normalidade de shapiro-wilk
bartlett.test(tamboril$altura,tamboril$substrato)#Teste de homogeneidade de variãncias de Barttlet.
```

Nem todos os pressupostos foram atendidos!!!!
Sendo assim tentamos alguma transformação, tentaremos a $log_{n}$.


```r
dic=lm(formula=log(altura)~substrato,data=tamboril)
shapiro.test(resid(dic))#teste de normalidade de shapiro-wilk
bartlett.test(log(tamboril$altura),tamboril$substrato)#Teste de homogeneidade de variãncias de Barttlet.
```
Agora tudo esta ok!

No contexto experimental temos que realizar a análise de variância do modelo ajustado, onde o teste F será aplicado para checagem do efeito do tratamento, que neste caso é o substrato.


```r
anova(dic)
```
O teste F mostra que existe efeito de substrato. Ou seja, a altura média de pelo menos um dos substratos difere dos demais Temos que determinar qual substrato difere de qual. Para isso, aplicamos um teste de comparações múltiplas (Tukey, por exemplo)


```r
dic=aov(formula=log(altura)~substrato,data=tamboril)
posthoc <- TukeyHSD(dic, "substrato", ordered = TRUE)
posthoc
plot(posthoc)
res=aggregate(altura~substrato,data=tamboril,mean)
res
res=res[order(-res$altura),] 
res
res$letra=c("a","ab","b")
res
```

Vamos agora gerar um gráfico:


```r
ggplot(res, aes(x=factor(substrato,levels = c(2,3,1)),y=altura,ymax=45))+
  geom_bar(stat="identity", fill="gray50",
colour = "black", width = 0.7)  +
geom_text(aes(label=letra,hjust=0, vjust=-1.5)) +
  labs(title = "Teste de Tukey", y="Altura média",x="Substratos")
```

## Delineamento em blocos casualizados

Os dados altura.mudas foram obtidos em blocos. Desta forma, devemos incluir isso no modelo:

$$y_{ijk}=\mu + \beta_k + \tau_j+\epsilon_{ijk}$$
onde: $y_{ijk}$ é a altura da i-ésima muda de tamboril crescendo no j-ésimo substrato do k-ésimo bloco, $\mu$ é a média das alturas, $\tau_{ij}$ é o efeito do j-ésimo substrato e $\epsilon_{ijk}$ é o erro aleatório correspondente.

No R basta incluirmos mais um elemento no modelo linear:


```r
dbc=aov(formula=log(altura)~bloco+substrato,data=tamboril)
shapiro.test(resid(dbc))#teste de normalidade de shapiro-wilk
bartlett.test(log(tamboril$altura),tamboril$substrato)#Teste de homogeneidade de variãncias de Barttlet.
anova(dbc)
```

Como não há efeito de bloco o resultado será o mesmo do exemplo anterior.

## Experimento fatorial

Nossos dados, no entanto, incluem duas espécies; paineira e tamboril, plantadas em três substratos. Temos então um fatorial duplo.

O modelo agora é descrito como:


```r
fat=aov(formula=log(altura)~bloco+substrato*especie,data=altura.mudas)
shapiro.test(resid(dbc))#teste de normalidade de shapiro-wilk
bartlett.test(log(altura.mudas$altura),altura.mudas$substrato)#Teste de homogeneidade de variãncias de Barttlet para substrato.
bartlett.test(log(altura.mudas$altura),altura.mudas$especie)#Teste de homogeneidade de variãncias de Barttlet para especie.
anova(fat)
```


```r
posthoc <- TukeyHSD(fat, "substrato", ordered = TRUE)
posthoc
plot(posthoc)
res=aggregate(altura~substrato,data=altura.mudas,mean)
res
res=res[order(-res$altura),] 
res
res$letra=c("a","a","b")
res
```

Vamos agora gerar um gráfico:


```r
ggplot(res, aes(x=factor(substrato,levels = c(2,3,1)),y=altura,ymax=45))+
  geom_bar(stat="identity", fill="gray50",
colour = "black", width = 0.7)  +
geom_text(aes(label=letra,hjust=0, vjust=-1.5)) +
  labs(title = "Teste de Tukey", y="Altura média",x="Substratos")
```

## Experimento com análise de regressão

Até agora vimos os delineamentos mais comuns usados em experimentação, mas nestes o tratamento sempre foi qualitativo. Podemos, no entanto ter experimentos com tratamentos quantitativos. Quando temos isso teremos que lançar mão de analise de regressão ao invés de teste de médias (Tukey). vamos considerar o seguinte exemplo:

Um experimento de campo foi implementado com de E. urophylla visando definir a dose ótima de N no plantio. Os tratamentos consistiram da aplicação de $0$, $60$, $120$ e $240~kg.ha^{-1}$ de N, como sulfato de amônio, em faixa de 0,5 m de largura ao lado da linha de plantio. 

Os tratamentos foram aplicados nas parcelas, com $0,6 ha$ cada, sendo 204 plantas úteis e duas fileiras de bordadura. O espaçamento entre as árvores foi de $3 x 2,8 m$. O delineamento experimental foi em blocos casualizados, em três repetições. Foi avaliado o volume por hectare após 30 meses. Os dados obtidos foram:


 doses    bloco    volume 
-------  -------  --------
   0        1        60   
   0        2        62   
   0        3        65   
  60        1        73   
  60        2        75   
  60        3        78   
  120       1        92   
  120       2        95   
  120       3        90   
  240       1        87   
  240       2        88   
  240       3        80   


Os primeiros passos são o ajuste do modelo, teste dos pressupostos e  a análise de variância:


```r
reg=aov(formula=volume~bloco+doses,data=df)
shapiro.test(resid(reg))
bartlett.test(df$vol,df$doses)
anova(reg)
```

Havendo efeito de doses passamos para a análise de regressão
Usaremos o método dos polinômios ortogonais. E para isso precisamos calcular a média por tratamento (dose).


```r
df2=aggregate(volume~doses,data=df,mean)
df2
```
Agora ajustamos os modelos usando a função "lm" e o argumento "poly". Como temos quatro níveis podemos ajustar um polinômio de até terceiro grau.


```r
lm1<-lm(volume ~ poly(doses, 1,raw=T),data=df2)
summary(lm1)
lm2<-lm(volume ~ poly(doses, 2,raw=T),data=df2)
summary(lm2)
lm3<-lm(volume ~ poly(doses, 3,raw=T),data=df2)
summary(lm3)
```

Selecionamos o modelo com o maior $R^2$. Desta forma ficamos com o polinômio do segundo grau.

O Gráfico fica assim:


```r
ggplot(df2, aes(x=doses, y=volume)) + geom_point(alpha=2/10, shape=21, fill="blue", colour="black", size=5)+
stat_smooth(method="lm",se=F, formula=y ~ poly(x, 2, raw=TRUE),colour="red")
```

Normalmente inserimos uma equação no gráfico


```r
p<-ggplot(df2, aes(x=doses, y=volume)) + geom_point(alpha=2/10, shape=21, fill="blue", colour="black", size=5)+
stat_smooth(method="lm",se=F, formula=y ~ poly(x, 2, raw=TRUE),colour="red")

#codigo para gerar equação de segundo grau
lm_eqn = function(df){
eq <- substitute(italic(y) == a + b %.% italic(x) - c %.% italic(x)^2*","~~italic(r)^2~"="~r2,
                   list(a = format(coef(lm2)[1], digits = 2),
                        b = format(coef(lm2)[2], digits = 2),
                        c = format(abs(coef(lm2)[3]), digits = 2),
                        r2 = format(summary(lm2)$r.squared, digits = 3)))
  as.character(as.expression(eq))
}


p + annotate("text", x=0.5, y=100, label=lm_eqn(df), hjust=0, size=8, 
             family="Times", parse=TRUE)
```

Agora precisamos descobrir a dose de N ótima, ou seja, o ponto de máximo do polinômio de segundo grau $a+bx+cx^2$. Para isso calcula-se a primeira derivada igualando a zero. O resultado é $\frac{-b}{2c}$


```r
max=-coef(lm2)[2]/(2*coef(lm2)[3])
max
```
Desta forma,  a dose que gera a produtividade máxima é $165,45 Kg.ha^{-1}$.
Se quisermos saber quanto seria esta produtividade basta aplicarmos esta dose como valor de "x" no nosso modelo. No R podemos fazer isso com a função "predict".


```r
predict(lm2,data.frame(doses=165.45))
```

Se quisermos podemos adicionar uma linha indicando o ponto de máximo: 


```r
p + annotate("text", x=0.5, y=100, label=lm_eqn(df), hjust=0, size=8, 
             family="Times", parse=TRUE)+
geom_vline(xintercept = max, linetype="dotted", 
                color = "blue", size=1.5)
```


# Modelo linear simples e multiplos aplicados à predição (biometria florestal)

Os engenheiros Florestais utilizam modelos lineares como ferramenta no inventário florestal. A principal função destes modelos é predizer o volume e a altura das árvores. 

Vamos primeiro ajustar modelos de relação hipsométrica, Estes modelos tem em geral apenas um preditor e são, portanto, modelos lineares simples da forma:

$$y_i=\beta_0 + \beta_1x_i+\epsilon_i$$
Nos modelos de relação hipsométrica $y_i$ se refere a altura das árvores e $x_i$ se refere ao dap. Desta forma, os modelos podem ser reescritos como:

$$h_i=\beta_0 + \beta_1dap_i+\epsilon_i$$
onde $h_i$ é altura das $i$ árvores, $dap_i$ corresponde ao dap das mesmas $i$ árvores, $\beta_0$ e $\beta_1$ são  coeficientes do modelo e $\epsilon_i$ é o erro aleatório ou resíduo.

Quase nunca a relação entre a altura e o dap é linear na escala original das variáveis. No entanto podemos obter relações lineares em outras escalas reescrevendo o modelo das seguintes formas:

$$ln(h_i)=\beta_0 + \beta_1ln(dap_i)+\epsilon_i$$ 

ou

$$ln(h_i)=\beta_0 + \beta_1\frac{1}{dap_i}+\epsilon_i$$ 

Vamos ajustar estes dois modelos usando o conjunto de dados "inventario":


```r
inv <- read.csv2("/media/vismara/39F783BB7B8CCFB1/saef/inventario.csv")
head(inventario)
```
Separando os dados de Relação hipsométrica excluindo árvores que não tenham a altura medida criando o objeto "rh". 


```r
rh<-inv[!is.na(inv$AltMed),]
```

Temos que separar por numero de medição!


```r
table(rh$NumMedicao)
table(rh$NumMedicao,rh$Codtalhao)
```

Vamos escolher o momento de medição 3 para trabalhar!



```r
inv3<-inv[inv$NumMedicao==3,] #dados de inventario no momento 3

rh3<-rh[rh$NumMedicao==3,] #dados para ajuste da rh no momento 3
```

Para o ajuste dos modelos usamos a função "lm":

1. Linear

```r
lin=lm(formula=AltMed~Dap,data=rh3)
summary(lin)
```

2. Stoffels

```r
loglog=lm(formula=log(AltMed)~log(Dap),data=rh3)
summary(loglog)
```

3. Curtis

```r
loginverso=lm(formula=log(AltMed)~I(1/Dap),data=rh3)
summary(loginverso)
```

O modelo de Curtis é o melhor. Agora podemos usa-lo para fazer as predições das alturas da árvores no inventário:


```r
inv3$HT<-ifelse(is.na(inv3$AltMed),exp(predict(loginverso,inv3)),inv3$AltMed)
inv3[1:30,]
```

# Confecção de relatórios com Rstudio, Knitr e Rmarkdown


## Introdução

O R permite através de pacotes específicos a geração de relatórios dinâmicos das análises realizadas e a integração com o Rstudio facilita bastante esta tarefa.

Podemos gerar relatórios das nossas análises no R em três formatos:

1. PDF
2. html
3. doc

Para gerar **PDFs** precisamos ter uma instalação do latex no computador (MiKtex no windows). Podemos, no entanto gerar arquivos **doc** ou **html** facilmente.

Para isso selecionamos no Rstudio no menu "file" $\rightarrow$ "newfile" $\rightarrow$ "R Markdown" e selecionamos a opção "word" ou "html".

O [Rstudio](https://www.rstudio.com/) cria um documento exemplo com vários elementos mas o fato é que o arquivo tem dois elementos básicos: 

1. o YAML (cabeçalho):

```yaml
---
title: "Untitled"
author: "Edgar de Souza Vismara"
date: "28 de agosto de 2018"
output: word_document
---
```
2. Os chuncks

<pre><code>```{r}
data(cars)
summary(cars)
```</code></pre>

Dentro dos chuncks utilizamos a linguagem do R e fora deles usamos o editor [markdown](https://www.rstudio.com/wp-content/uploads/2015/02/rmarkdown-cheatsheet.pdf). Este editor possui uma linguagem simples que pode ser utilizada para escrever um relatorio a cerca da sua análise enquanto voce a desenvolve. Para incluir equações no meio do texto usa-se a linguagem [latex](https://www.latex-project.org/) entre cifrões ($).

Os "chuncks" possuem várias [opções](https://rmarkdown.rstudio.com/lesson-3.html) que podem ser utilizadas para definir opções de integração do código com o texto. Estas são incluídas dentros das chaves e separadas por vírgula, como no exemplo:

<pre><code>```{r , echo=F, eval=F}
data(cars)
summary(cars)
```</code></pre>

Para incluir equações usa-se a linguagem [latex](https://www.latex-project.org/) entre cifrões ($).

Após a finalização do relatório basta clicar no botão "knit" do Rstudio e o relatório será gerado.

## Exemplo

```yaml
---
title: "Análise do Experimento de altura de mudas"
author: "Edgar de Souza Vismara"
date: "28 de agosto de 2018"
output: word_document
---
```


  # Introdução

  Deseja-se testar trẽs substratos na produção de mudas de tamboril. para   isso a ltura das mesmas foi medida em cm.
  
  # Métodos
  
  ## Modelo
  
  O modelo utilizado foi:
  
  ```
  $$y_{ij}=\mu + \tau_{j} +\epsilon_{ij}$$
  ```
  
  ## Método de ajuste 
  
  Trata-se de um experimento inteiramente casualizado, onde o modelo foi ajustado por mínimos quadrados para poterior aplicação da análise de variância e teste de Tukey. A análise foi realizada com software [R](https://cran.r-project.org/). 
  
  # Resultados
  
  ## ANOVA
  
  <pre><code>```{r , echo=F}
#Dados de importação
altura.mudas <- read.table("/media/vismara/39F783BB7B8CCFB1/saef/altura-mudas.csv",header=TRUE,sep=";",dec=",")

#Transformando substrato em fator
altura.mudas$substrato=as.factor(altura.mudas$substrato)

#Separando a espécie tamboril
tamboril=altura.mudas[altura.mudas$especie=="tamboril",]


#Análise
dic=aov(formula=log(altura)~substrato,data=tamboril)
posthoc <- TukeyHSD(dic, "substrato", ordered = TRUE)
plot(posthoc)

res=aggregate(altura~substrato,data=tamboril,mean)
res=res[order(-res$altura),] 
res$letra=c("a","ab","b")

#Resultado tabela
knitr::kable(res,align="c")

#Resultado Gráfico
library(ggplot2)
ggplot(res, aes(x=factor(substrato,levels = c(2,3,1)),y=altura,ymax=45))+
  geom_bar(stat="identity", fill="gray50",
colour = "black", width = 0.7)  +
geom_text(aes(label=letra,hjust=0, vjust=-1.5)) +
  labs(title = "Teste de Tukey", y="Altura média",x="Substratos")
```</code></pre>

  
  Os resultados mostram que o subtrato dois fez com que as mudas atingissem um altura média superior, não diferindo do substrato 3. 
  
  # Conclusão
  
  Baseado nos resultados recomenda-se a utilização do substrato 2 ou 3 no cultivo da espécie tamboril em viveiro. 
