# pt-bR

[![translation status](https://translate.rx.studio/widgets/r-project/pt_BR/svg-badge.svg?native=1)](https://translate.rx.studio/languages/pt_BR/r-project/)
[![MIT license](https://img.shields.io/github/license/clente/pt-bR)](https://github.com/clente/pt-bR/blob/main/LICENSE)

_This repository is a hub for all people who want to help translate R into
Brazilian Portuguese. The rest of the README in in PT-BR, but non-Portuguese
speakers can reach out to [@ctlente](https://twitter.com/ctlente) on Twitter if
they need any additional information about the project._

## Sobre

O projeto pt-bR tem por objetivo reunir todas as pessoas interessadas em ajudar
a traduzir a linguagem
[R](https://en.wikipedia.org/wiki/R_(programming_language)) de programação para
o português brasileiro 🇧🇷 Se você sabe falar inglês e usa R com frequência,
precisamos da sua ajuda!

Diferentemente de outras linguagens, o R tenta exibir todas as suas mensagens no
mesmo idioma do computador em que ele é executado. Em princípio, isso reduz a
barreira de entrada para aprender R; alertas e erros são muito comuns no código
de quem está começando a programar, então o ideal é que essas mensagens sejam
o menos obscuras possível.

Vários outros países já têm
[times](https://developer.r-project.org/TranslationTeams.html) consolidados de
tradução, mas (talvez por causa da complexidade do
[processo](https://developer.r-project.org/Translations30.html) de contribuição)
o Brasil estava sem nenhum colaborador oficial. Hoje em dia, entretanto, ficou
mais fácil do que nunca ajudar na tradução e por isso quisemos reunir aqui os
nossos esforços.

Para ajudar no esforço de tradução, você precisa:

1. Entrar no [Slack](https://contributor.r-project.org/slack) R Contributors e
apresentar-se no canal `#core-translations`;
1. Ler a sessão [Recursos](https://github.com/clente/pt-bR#recursos) deste
documento, pois a tradução tem convenções que devem ser seguidas;
1. Criar uma conta na instância do [Weblate](https://translate.rx.studio/)
(atualmente mantida por [@daroczig](https://twitter.com/daroczig));
1. Listar todos os
[componentes](https://translate.rx.studio/languages/pt_BR/r-project/) do
português brasileiro;
1. Escolher um componente que não esteja 100% traduzido (como, por exemplo, o
pacote [utils](https://translate.rx.studio/projects/r-project/utils-r/pt_BR/));
1. Clicar em _Unfinished strings_ para listar todas as mensagens que ainda não
foram traduzidas e
1. Começar!

## Recursos

Este é um documento vivo que lista alguns problemas comuns no processo de
tradução do R para o português brasileiro. Todas as sugestões estão abertas a
revisão e, se você discordar de alguma coisa, é só abrir uma
[issue](https://github.com/clente/pt-bR/issues) ou criar um novo tópico na área
de [discussões](https://github.com/clente/pt-bR/discussions).

### Estilística

O R é uma linguagem com quase 30 anos e, portanto, suas mensagens foram escritas
por muitas pessoas com estilos bem diferentes. Sempre devemos seguir as regras
gramaticais e ortográficas do português, incluindo o novo
[Acordo Ortográfico](https://www2.senado.leg.br/bdsf/bitstream/handle/id/508145/000997415.pdf),
mas também queremos preservar o máximo possível a linguagem original.

Em inglês é possível omitir diversos conectores sem prejudicar o entendimento.
Os times da Itália e da França costumam recolocar esses conectores quando a
alternativa ficaria pouco sintática.

> _Maybe package installed with version of R newer than %s ?_

> Talvez o pacote tenha sido instalado com uma versão do R mais recente que %s ?

Também não traduzimos nada que seja um termo técnico do R como, por exemplo,
nomes de funções, objetos e argumentos (geralmente entre aspas).

> _'MARGIN' does not match dim(X)_

> 'MARGIN' não corresponde a dim(X)

Em ocasiões excepcionais, uma função pode ser utilizada como verbo. Seguindo o
exemplo dos times da França e da Itália, a única saída é reconstruir a frase
completamente:

> _cannot xtfrm data frames_

> impossível utilizar xtfrm em um data frame


### Formatação

O uso de espaços e parágrafos em português é normatizado e bem estabelecido. Os
textos do R, entretanto, têm limitações de espaço e formatação que nem sempre
são óbvias no momento da tradução.

Grande parte das mensagens do R possui algum tipo de referência ao código que a
gerou. Isso ocorre através de
[especificadores](https://cplusplus.com/reference/cstdio/printf/) de formato e
precisamos mantê-los na mesma ordem em que eles aparecem no texto de referência.

> _%s and %s must have the same length_

> %s e %s devem ter o mesmo comprimento

Se não for possível manter a mesma ordem, é necessário especificar o índice da
substituição desejada com `%n$<fmt>` (e.g. `%1$s`, `%2$s`, e assim por diante).

As mensagens também podem ter caracteres especiais como aspas simples (`'`),
aspas duplas (`"`), tabs (`\t`) e novas linhas (`\n`), além de espaços extras em
lugares estranhos. Para manter um padrão, não alteramos esse tipo de formatação
mesmo que seu uso não seja estritamente correto.

> _Conflicts attaching package %s:<br>%s_

> Conflitos ao anexar pacote %s:<br>%s

### Gênero

O inglês, diferentemente do português, não tem gênero gramatical. Sempre que
possível tentamos seguir o
[Manual para Uso não Sexista da Linguagem](https://edisciplinas.usp.br/pluginfile.php/3034366/mod_resource/content/1/Manual%20para%20uso%20n%C3%A3o%20sexista%20da%20linguagem.pdf)
nas traduções, mas infelizmente isso nem sempre é viável.

O gênero gramatical de argumentos, siglas e outros substantivos inanimados pode,
no geral, ser inferido pelo contexto. Na tradução abaixo, consideramos "_DLL_"
como sendo "a biblioteca de vínculo dinâmico".

> _DLL %s was not loaded_

> DLL %s não foi carregada

Já na tradução seguinte, apesar de "_scale_" ser um substantivo feminino em
português, aqui ele está fazendo fazendo o papel de "o argumento".

> _'scale' should be numeric or NULL_

> 'scale' deve ser numérico ou NULL

Em certas situações, conseguimos simplesmente remover a necessidade de
especificar um gênero gramatical. Na expressão abaixo poderíamos traduzir o
papel para "autor(a)", mas temos margem para o termo completamente.

> _Authors@R field gives no person with name and author role_

> Campo Authors@R não fornece nenhuma pessoa com nome e papel 'author'

Em raras situações, as mensagens fazem referência a quem está programando.
Nestes casos o melhor que podemos fazer sem prejudicar a compreensão ou aumentar
muito o comprimento da frase é recorrer ao "o(a)".

> _Not enough arguments passed to user macro '%s'_

> Não foram passados argumentos suficientes para a macro '%s' do(a) usuário(a)

É importante ressaltar que esta estratégia não é adotada pelos times da França e
da Itália, que preferem simplesmente utilizar o masculino "usuário". A menos que
haja alguma diretriz desencorajando recursos como "o(a)", acreditamos que o
nosso padrão é preferível.

### Glossário

Aqui reunimos alguns termos que aparecem repetidamente nas mensagens do R e que
podem ser difíceis de traduzir. Caso você tenha problemas com uma palavra que
não está no [glossário](https://www.isi-web.org/isi.cbs.nl/glossary/) do ISI
nem na tabela abaixo, procure a tradução no [Linguee](https://www.linguee.com)
ou na Wikipédia e nos avise para que possamos incluí-la nesta seção.

Tentamos registrar as versões mais comuns de cada termo, contudo nem sempre é
possível fazer uma contabilização precisa. Por exemplo, se você estiver
procurando por "_caching_", o verbete correspondente é "_cache_". Uma mesma
palavra também pode ter várias funções, como "_replacement_", que
simultaneamente significa "substituto" e "substituição".

Por fim, optamos por manter alguns dos termo em inglês, pois suas traduções são
pouco utilizadas, mas essa percepção é meramente subjetiva; as palavras marcadas
com um asterisco \* são aquelas que nós mesmos estamos questionando.

| Inglês               | Português                                    |
|:---------------------|:---------------------------------------------|
| abort                | interromper                                  |
| alias                | alias\*                                      |
| allocate             | alocar                                       |
| argument             | argumento                                    |
| array                | array                                        |
| assign               | atribuir                                     |
| attach               | anexar                                       |
| attribute            | atributo                                     |
| backslash            | barra invertida                              |
| bind                 | associar / vincular                          |
| bitmap               | bitmap                                       |
| boxplot              | boxplot                                      |
| break                | limite de categoria (para histogramas)       |
| browser              | navegador                                    |
| build                | compilar                                     |
| bytecode             | bytecode                                     |
| cache                | cachear                                      |
| call                 | chamar                                       |
| callback             | callback                                     |
| character string     | string de caracteres\*                       |
| check                | verificar                                    |
| chunk                | bloco (de código)\*                          |
| closure              | closure                                      |
| codoc                | codoc (da função do R)                       |
| coerce               | fazer coerção                                |
| colortype            | colortype                                    |
| console              | console                                      |
| data frame           | data frame                                   |
| database             | base de dados                                |
| dataset              | conjunto de dados                            |
| debug                | depurar\*                                    |
| defunct              | extinto                                      |
| deparse              | deparse                                      |
| deprecated           | obsoleto                                     |
| detach               | detach\*                                     |
| device               | dispositivo                                  |
| dispatch             | despachar                                    |
| documentation object | objeto de documentação\*                     |
| download             | baixar                                       |
| driver               | driver                                       |
| drop                 | descartar                                    |
| encoding             | codificação                                  |
| entry                | registro / campo                             |
| environment          | ambiente                                     |
| evaluate             | avaliar (por exemplo, `eval()`)\*            |
| factor               | fator                                        |
| fifo                 | fifo (de _first in, first out_)              |
| file pointer         | ponteiro de arquivo\*                        |
| file stream          | stream de arquivo                            |
| filename             | nome do arquivo                              |
| fit                  | ajustar                                      |
| flag                 | flag                                         |
| flush                | esvaziar                                     |
| frame                | quadro (para _stack_) / escopo (para _call_) |
| handle               | gerenciar                                    |
| hard-coded           | hard-coded\*                                 |
| history              | histórico                                    |
| implement            | implementar                                  |
| incoming checks      | verificações de recebimento\*                |
| index                | índice                                       |
| invalid              | inválido                                     |
| IO                   | IO                                           |
| label                | rótulo                                       |
| lag                  | defasagem                                    |
| layout               | layout ou estrutura????                      |
| lazy loading         | lazy loading\*                               |
| lazydata             | lazydata                                     |
| leading minor        | submatriz\*                                  |
| length               | comprimento                                  |
| library              | biblioteca                                   |
| link                 | link                                         |
| locale               | locale                                       |
| locator              | localizador                                  |
| locking              | travamento\*                                 |
| logical              | lógico (ao invés de booleano)                |
| macro                | macro                                        |
| magic number         | número mágico                                |
| match                | corresponder                                 |
| metafile             | metafile                                     |
| mirror               | espelho (por exemplo, do CRAN)               |
| mismatch             | incompatível                                 |
| missing              | ausente                                      |
| modulus              | módulo                                       |
| multibyte            | multibyte                                    |
| namespace            | namespace\*                                  |
| non-numeric type     | tipo não numérico                            |
| numeric-alike        | numérico ou similar\*                        |
| offending            | problemático                                 |
| offset               | deslocar / compensar (depende do contexto)   |
| opcode               | opcode                                       |
| outlier              | outlier\*                                    |
| overflow             | overflow                                     |
| override             | sobrescrever                                 |
| package              | pacote                                       |
| pager                | visualizador\*                               |
| pair list            | lista pareada                                |
| parse                | analisar\*                                   |
| path                 | caminho                                      |
| pipe                 | pipe                                         |
| pixmap               | pixmap                                       |
| platform             | plataforma                                   |
| polyline             | polyline                                     |
| port                 | porta (por exemplo, 8080)                    |
| portable             | portável                                     |
| profiling            | análise de desempenho                        |
| promise              | promessa                                     |
| prompt               | prompt                                       |
| proxy                | proxy                                        |
| push back            | voltar atrás                                 |
| quote symbol         | símbolo de citação                           |
| range                | intervalo / limite (depende do contexto)     |
| raw                  | raw (para o tipo de dado)                    |
| redraw               | redesenhar                                   |
| regular expression   | expressão regular                            |
| replace              | substituir                                   |
| report               | reportar                                     |
| repository           | repositório                                  |
| require              | requerer\*                                   |
| return               | retornar                                     |
| RNG                  | RNG                                          |
| role                 | papel\*                                      |
| routine              | rotina                                       |
| run                  | executar                                     |
| seal                 | selar                                        |
| search path          | caminho de busca                             |
| seed                 | semente                                      |
| seek                 | buscar                                       |
| sink                 | sink                                         |
| slash                | barra                                        |
| slot                 | slot (termo do R)\*                          |
| snapshot             | snapshot                                     |
| socket               | soquete                                      |
| source               | carregar                                     |
| splice               | juntar                                       |
| stack                | stack\*                                      |
| standardizable       | padronizável                                 |
| startup              | inicialização                                |
| strict               | rigoroso(a)                                  |
| subscript            | índice\*                                     |
| subset               | dividir em subconjuntos                      |
| tag                  | etiqueta                                     |
| tag                  | tag\*                                        |
| tangling             | tangling\*                                   |
| tarball              | tarball                                      |
| template             | modelo\*                                     |
| thread               | thread\*                                     |
| timeout              | limite de tempo                              |
| timer                | cronômetro                                   |
| timezone             | fuso horário                                 |
| top level            | nível superior                               |
| traceback            | traceback                                    |
| truncate             | truncar                                      |
| unary operator       | operador unário                              |
| unbind               | desvincular                                  |
| underflow            | underflow                                    |
| viewport             | viewport                                     |
| vignette             | vignette                                     |
| warning              | alerta                                       |
| workspace            | ambiente de trabalho                         |
| wrapup               | finalização\*                                |
