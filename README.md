# pt-bR

[![translation status](https://translate.rx.studio/widgets/r-project/pt_BR/svg-badge.svg?native=1)](https://translate.rx.studio/languages/pt_BR/r-project/)
[![MIT license](https://img.shields.io/github/license/clente/pt-bR)](https://github.com/clente/pt-bR/blob/main/LICENSE)

_This repository is a hub for all people who want to help translate R into
Brazilian Portuguese. This README is in English, but you can reach out to
[@ctlente](https://twitter.com/ctlente) on Twitter if you need any additional
information about the project._

## About

The goal of the pt-bR project is to bring together all people interested in
helping translate the [R
language](https://en.wikipedia.org/wiki/R_(programming_language)) into Brazilian
Portuguese 🇧🇷 If you use R a lot, we need your help!

Unlike other languages, R tries to display every message in the same language as
the computer it's running on. In principle, this reduces R's barrier to entry;
warnings and errors are very common in code written by beginners, so it's
essential that these messages are as clear as possible.

Many other countries already have consolidated translation
[teams](https://developer.r-project.org/TranslationTeams.html), but (maybe
because of the complexity of the
[job](https://developer.r-project.org/Translations30.html)) Brazil lacked any
official collaborators. Nowadays, however, it's easier than ever to help with
translations and that's why we wanted to collect our efforts on this page.

To help in the translation process, you need to:

1. Sign up to the [R Contributors
   Slack](https://contributor.r-project.org/slack) and introduce yourself in the
   `#core-translations` channel;
1. Read the [Resources](https://github.com/clente/pt-bR#resources) section of
   this document, because the translation has some conventions that should be
   followed;
1. Create an account on [Weblate](https://translate.rx.studio/) (currently
   maintained by [@daroczig](https://twitter.com/daroczig));
1. List every Brazilian Portuguese
   [component](https://translate.rx.studio/languages/pt_BR/r-project/);
1. Choose a component that's not 100% translated (like, for example, the [utils
   package](https://translate.rx.studio/projects/r-project/utils-r/pt_BR/));
1. Click **Unfinished strings** to list all messages that haven't been
   translated and
1. Start!

## Resources

This is a living document that lists some common problems that come up when
translating R to Brazilian Portuguese. Every suggestion here is open to debate
and, if you disagree about something, simply create an
[issue](https://github.com/clente/pt-bR/issues) or a new topic in the
[discussions](https://github.com/clente/pt-bR/discussions) tab.

### Style

R is a programming language that's almost 30 years old and, therefore, its
messages were written by many people with very different writing styles. We
should always follow Portuguese's grammar and orthography, including the new
[Spelling
Reform](https://www2.senado.leg.br/bdsf/bitstream/handle/id/508145/000997415.pdf),
but we also want to preserve the original language as much as possible.

In English it is possible to omit many connectors without changing the meaning.
The Italian and French teams usually restore these connectors when the
alternative wouldn't sound as natural.

> _Maybe package installed with version of R newer than %s ?_

> Talvez o pacote tenha sido instalado com uma versão do R mais recente que %s ?

We also don't translate anything that is a technical term from R like, for
example, function names, objects and arguments (usually between quotes).

> _'MARGIN' does not match dim(X)_

> 'MARGIN' não corresponde a dim(X)

In exceptional situations, a function can be used as a verb. Following the
French and Italian teams, the only solution is to completely reconstruct the
sentence.

> _cannot xtfrm data frames_

> impossível utilizar xtfrm em um data frame


### Formatting

The use of spaces and paragraphs in Portuguese is standardised and well
established. R texts, however, have space and formatting limitations that are
not always obvious when translating.

Most R messages have some kind of reference to the code that generated them.
This happens through [format
specifiers](https://cplusplus.com/reference/cstdio/printf/) and we need to keep
them in the same order as they appear in the reference text.

> _%s and %s must have the same length_

> %s e %s devem ter o mesmo comprimento

If it's not possible to keep the same order, you need to specify the index of
the desired substitution with `%n$<fmt>` (e.g. `%1$s`, `%2$s`, and so on).

Messages can also have special characters such as single quotes (`'`), double
quotes (`"`), tabs (`\t`) and new lines (`\n`), as well as extra spaces in
strange places. To maintain a standard, we don't change this type of formatting
even if its use is not strictly correct.

> _Conflicts attaching package %s:<br>%s_

> Conflitos ao anexar pacote %s:<br>%s

### Gender

Unlike Portuguese, English does not specify grammatical gender. We will try to
follow the [Manual for Non Sexist Use of Language (in
Portuguese)](https://edisciplinas.usp.br/pluginfile.php/3034366/mod_resource/content/1/Manual%20para%20uso%20n%C3%A3o%20sexista%20da%20linguagem.pdf)
in translations as much as we can, but unfortunately that is not always
possible.

Grammatical gender of arguments, acronyms and other nouns can usually be
inferred by context. In the example below, we translate "_DLL_" as "a
biblioteca de vínculo dinâmico" (dynamic-link library).

> _DLL %s was not loaded_

> DLL %s não foi carregada

In the following example, although "_scale_" is a feminine noun in Portuguese,
the masculine is used because it is replacing "_argument_", "o argumento", which
is a masculine noun.

> _'scale' should be numeric or NULL_

> 'scale' deve ser numérico ou NULL

In certain situations, we can simply ignore genders. In the following
expression, we could translate "_author_" to "autor(a)", but there are
alternatives that allow us to completely omit it.

> _Authors@R field gives no person with name and author role_

> Campo Authors@R não fornece nenhuma pessoa com nome e papel 'author'

In rare cases, the messeges references who doing the programming. In
these cases, the best we can do without jeopardising comprehension or overly
increasing the length of the sentence is to use "o(a)".

> _Not enough arguments passed to user macro '%s'_

> Não foram passados argumentos suficientes para a macro '%s' do(a) usuário(a)

It's important to note that this strategy is not adopted by the French and
Italian teams, who prefer to simply use the masculine term "usuário". Unless
there is some guideline discouraging resources such as "o(a)", we believe that
our standard is preferable.

### Glossary

Here we have put together some terms that appear repeatedly in R messages and
which can be difficult to translate. If you have problems with a word that is
not in the table below, look up the translation on
[Linguee](https://www.linguee.com) or Wikipedia and let us know so we can
include it in this section.

We have tried to use the most common versions of each term, but it's not always
possible to keep a precise account. For example, if you are searching for
"_caching_", the corresponding entry is "_cache_". The same word can also have
several functions, such as "_replacement_", which simultaneously means
"substituto" and "substituição".

Finally, we have chosen to keep some of the terms in English, as their
translations are not widely used, but this perception is purely subjective; the
words marked with an asterisk \* are those that we ourselves are questioning.

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
| layout               | layout\*                                     |
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
| non-interactively    | de forma não interativa                      |
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
| profile              | perfil (substantivo), perfilar (verbo)       |
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
| unlisted             | não listado                                  |
| viewport             | viewport                                     |
| vignette             | vignette                                     |
| warning              | alerta                                       |
| workspace            | ambiente de trabalho                         |
| wrapup               | finalização\*                                |
