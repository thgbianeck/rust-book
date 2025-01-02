# Introdução

> **Nota:** Esta edição do livro é a mesma que "A Linguagem de Programação Rust" disponível em formato impresso e ebook pela No Starch Press.

Bem-vindo ao "A Linguagem de Programação Rust", um livro introdutório sobre Rust. A linguagem de programação Rust te ajuda a escrever software mais rápido e confiável. Normalmente, a ergonomia de alto nível e o controle de baixo nível entram em conflito no design de linguagens de programação; Rust desafia essa dicotomia. Ao equilibrar capacidade técnica poderosa e uma ótima experiência para o desenvolvedor, Rust te dá a opção de controlar detalhes de baixo nível (como o uso de memória) sem todo o aborrecimento tradicional associado a esse controle.

## Para Quem Rust é Feito

Rust é ideal para muitas pessoas por diversas razões. Vamos ver alguns dos grupos mais importantes.

### Equipes de Desenvolvedores

Rust está se mostrando uma ferramenta produtiva para colaboração entre grandes equipes de desenvolvedores com diferentes níveis de conhecimento em programação de sistemas. Código de baixo nível é suscetível a vários bugs sutis, que na maioria das outras linguagens só podem ser detectados por testes extensivos e revisões de código cuidadosas feitas por desenvolvedores experientes. Em Rust, o compilador atua como um guardião, recusando-se a compilar código com esses bugs, incluindo bugs de concorrência. Ao trabalhar ao lado do compilador, a equipe pode focar no raciocínio lógico do programa em vez de caçar bugs.

Rust também traz ferramentas contemporâneas para o mundo da programação de sistemas:

- **Cargo**, o gerenciador de dependências e ferramenta de compilação inclusa, torna a adição, compilação e gestão de dependências algo indolor e consistente em todo o ecossistema Rust.
- A ferramenta de formatação **Rustfmt** garante um estilo de codificação consistente entre desenvolvedores.
- O **rust-analyzer** potencializa a integração com Ambientes de Desenvolvimento Integrado (IDEs) para funcionalidades como autocompletar código e mensagens de erro inline.
  Ao usar essas e outras ferramentas do ecossistema Rust, os desenvolvedores podem ser produtivos enquanto escrevem código em nível de sistema.

### Estudantes

Rust é para estudantes e aqueles interessados em aprender conceitos de sistemas. Usando Rust, muitas pessoas têm aprendido sobre tópicos como desenvolvimento de sistemas operacionais. A comunidade é muito acolhedora e está feliz em responder perguntas de estudantes. Por meio de esforços como este livro, as equipes Rust querem tornar os conceitos de sistemas mais acessíveis a mais pessoas, especialmente aquelas novas na programação.

### Empresas

Centenas de empresas, grandes e pequenas, usam Rust em produção para uma variedade de tarefas, incluindo ferramentas de linha de comando, serviços web, ferramentas de DevOps, dispositivos embarcados, análise e transcodificação de áudio e vídeo, criptomoedas, bioinformática, motores de busca, aplicações de Internet das Coisas (IoT), aprendizado de máquina e até mesmo partes significativas do navegador web Firefox.

### Desenvolvedores de Código Aberto

Rust é para pessoas que querem construir a linguagem de programação Rust, a comunidade, ferramentas de desenvolvedor e bibliotecas. Adoraríamos que você contribuísse para a linguagem Rust.

### Pessoas que Valorizam Velocidade e Estabilidade

Rust é para quem busca velocidade e estabilidade em uma linguagem. Por velocidade, queremos dizer tanto a rapidez com que o código Rust pode rodar quanto a rapidez com que Rust permite escrever programas. As verificações do compilador Rust garantem estabilidade durante adições de funcionalidades e refatorações. Isso contrasta com o código legado frágil em linguagens sem essas verificações, que os desenvolvedores frequentemente têm medo de modificar. Ao buscar abstrações sem custo adicional, Rust se esforça para fazer com que código seguro também seja código rápido.

A linguagem Rust espera apoiar muitos outros usuários também; aqueles mencionados aqui são apenas alguns dos maiores interessados. No geral, a maior ambição de Rust é eliminar os compromissos que os programadores aceitaram por décadas, fornecendo segurança e produtividade, velocidade e ergonomia. Experimente Rust e veja se suas escolhas funcionam para você.

## Para Quem Este Livro é Feito

Este livro assume que você já escreveu código em outra linguagem de programação, mas não faz suposições sobre qual. Tentamos tornar o material acessível a pessoas com uma ampla variedade de experiências de programação. Não passamos muito tempo explicando o que é programação ou como pensar sobre isso. Se você é totalmente novo na programação, seria melhor ler um livro que forneça uma introdução específica à programação.

## Como Utilizar Este Livro

Em geral, este livro assume que você o está lendo em sequência, do início ao fim. Capítulos posteriores constroem sobre conceitos apresentados em capítulos anteriores, e capítulos anteriores podem não mergulhar em detalhes de um tópico específico, mas revisitarão o tópico em um capítulo posterior.

Você encontrará dois tipos de capítulos neste livro: capítulos de conceitos e capítulos de projetos. Nos capítulos de conceitos, você aprenderá sobre um aspecto do Rust. Nos capítulos de projetos, construiremos pequenos programas juntos, aplicando o que você aprendeu até agora. Os capítulos 2, 12 e 20 são capítulos de projetos; os demais são de conceitos.

- O **Capítulo 1** explica como instalar Rust, como escrever um programa "Hello, world!" e como usar Cargo, o gerenciador de pacotes e ferramenta de compilação do Rust.
- O **Capítulo 2** é uma introdução prática à escrita de um programa em Rust, onde você construirá um jogo de adivinhação de números. Aqui, cobrimos conceitos de forma mais geral, e capítulos posteriores fornecerão mais detalhes. Se você quer colocar a mão na massa logo de cara, o Capítulo 2 é o lugar para isso. O Capítulo 3 aborda recursos do Rust que são semelhantes aos de outras linguagens de programação, e no Capítulo 4 você aprenderá sobre o sistema de propriedade do Rust. Se você é um aprendiz meticuloso que prefere aprender todos os detalhes antes de passar para o próximo, talvez queira pular o Capítulo 2 e ir direto para o Capítulo 3, retornando ao Capítulo 2 quando quiser trabalhar em um projeto aplicando os detalhes aprendidos.

- O **Capítulo 5** discute structs e métodos.
- O **Capítulo 6** cobre enums, expressões match e o constructo de fluxo de controle if let. Você usará structs e enums para criar tipos personalizados em Rust.

- O **Capítulo 7**, você aprenderá sobre o sistema de módulos do Rust e as regras de privacidade para organizar seu código e sua Interface de Programação de Aplicações (API) pública.
- O **Capítulo 8** discute algumas estruturas de dados comuns que a biblioteca padrão fornece, como vetores, strings e hash maps.
- O **Capítulo 9** explora a filosofia e técnicas de tratamento de erros do Rust.

- O **Capítulo 10** se aprofunda em genéricos, traits e lifetimes, dando a você o poder de definir código que se aplica a múltiplos tipos.
- O **Capítulo 11** é todo sobre testes, que mesmo com as garantias de segurança do Rust são necessários para assegurar que a lógica do seu programa esteja correta.
- O **Capítulo 12**, construiremos nossa própria implementação de um subconjunto de funcionalidades da ferramenta de linha de comando grep, que pesquisa texto dentro de arquivos. Para isso, usaremos muitos dos conceitos discutidos nos capítulos anteriores.

- O **Capítulo 13** explora closures e iterators: recursos do Rust que vêm das linguagens de programação funcional.
- O **Capítulo 14**, examinaremos o Cargo mais profundamente e falaremos sobre melhores práticas para compartilhar suas bibliotecas com outros.
- O **Capítulo 15** discute ponteiros inteligentes que a biblioteca padrão fornece e as traits que habilitam sua funcionalidade.

- O **Capítulo 16**, percorreremos diferentes modelos de programação concorrente e falaremos sobre como Rust te ajuda a programar em múltiplas threads sem medo.
- O **Capítulo 17** compara os idiomas do Rust com os princípios de programação orientada a objetos que você pode conhecer.

- O **Capítulo 18** é uma referência sobre padrões e pattern matching, que são maneiras poderosas de expressar ideias ao longo dos programas Rust.
- O **Capítulo 19** contém uma variedade de tópicos avançados de interesse, incluindo Rust inseguro, macros e mais sobre lifetimes, traits, tipos, funções e closures.

- O **Capítulo 20**, implementaremos um projeto em que construiremos um servidor web multithread de baixo nível!

Finalmente, alguns apêndices contêm informações úteis sobre a linguagem em um formato mais de referência. O Apêndice A cobre as palavras-chave do Rust, o Apêndice B cobre os operadores e símbolos do Rust, o Apêndice C discute traits deriváveis fornecidos pela biblioteca padrão, o Apêndice D cobre algumas ferramentas de desenvolvimento úteis, e o Apêndice E explica as edições do Rust. No Apêndice F, você pode encontrar traduções do livro, e no Apêndice G discutiremos como o Rust é feito e o que é Rust noturno (nightly).

## Aprendendo a Ler Mensagens de Erro

Uma parte importante do processo de aprendizado de Rust é aprender a ler as mensagens de erro que o compilador exibe: essas te guiarão em direção a um código funcional. Portanto, forneceremos muitos exemplos que não compilam juntamente com a mensagem de erro que o compilador mostrará em cada situação. Saiba que se você inserir e tentar rodar um exemplo aleatório, ele pode não compilar! Certifique-se de ler o texto ao redor para ver se o exemplo que você está tentando rodar é para dar erro. Ferris também te ajudará a distinguir código que não deve funcionar:

| Ferris                                                                                      | Significado                                      |
| ------------------------------------------------------------------------------------------- | ------------------------------------------------ |
| ![Ferris com um ponto de interrogação](./img/svg/does_not_compile.svg)                      | Este código não compila!                         |
| ![Ferris com as mãos para o alto](./img/svg/panics.svg)                                     | Este código causa pânico!                        |
| ![Ferris com uma garra levantada, encolhendo os ombros](./img/svg/not_desired_behavior.svg) | Este código não produz o comportamento desejado. |

Na maioria das situações, te guiaremos para a versão correta de qualquer código que não compile.

## Código-Fonte

Os arquivos-fonte dos quais este livro é gerado podem ser encontrados no GitHub.

<!-- ![Ferris com um ponto de interrogação](https://doc.rust-lang.org/book/img/ferris/does_not_compile.svg)
![Ferris com as mãos para o alto](https://doc.rust-lang.org/book/img/ferris/panics.svg)
![Ferris com uma garra levantada, encolhendo os ombros](https://doc.rust-lang.org/book/img/ferris/not_desired_behavior.svg) -->
