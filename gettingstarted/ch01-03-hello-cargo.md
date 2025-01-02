## Olá, Cargo!

Cargo é o sistema de construção e gerenciador de pacotes do Rust. A maioria dos Rustaceans (como carinhosamente nos chamamos) usa esta ferramenta para gerenciar seus projetos Rust. Isso porque o Cargo cuida de muitas tarefas para você, como compilar seu código, baixar as bibliotecas que seu código precisa (chamamos essas bibliotecas de _dependências_) e compilá-las.

Os programas Rust mais simples, como o que escrevemos até agora, não têm dependências. Se tivéssemos construído o projeto "Olá, mundo!" com o Cargo, ele usaria apenas a parte do Cargo que lida com a compilação do seu código. À medida que você escrever programas Rust mais complexos, você adicionará dependências, e se começar um projeto usando o Cargo, adicionar essas dependências será muito mais fácil.

Como a grande maioria dos projetos Rust usa o Cargo, o resto deste livro assume que você também está usando o Cargo. O Cargo vem instalado com o Rust se você usou os instaladores oficiais discutidos na seção "Instalação". Se você instalou o Rust por outros meios, verifique se o Cargo está instalado digitando o seguinte no seu terminal:

```console
$ cargo --version
```

Se você vir um número de versão, você tem o Cargo! Se vir um erro, como `comando não encontrado`, consulte a documentação do seu método de instalação para determinar como instalar o Cargo separadamente.

### Criando um projeto com o Cargo

Vamos criar um novo projeto usando o Cargo e ver como ele difere do nosso projeto original "Olá, mundo!". Volte para o seu diretório _projects_ (ou onde quer que você tenha decidido armazenar seu código). Então, em qualquer sistema operacional, execute o seguinte:

```console
$ cargo new hello_cargo
$ cd hello_cargo
```

O primeiro comando cria um novo diretório e projeto chamado _hello_cargo_. Nomeamos nosso projeto _hello_cargo_, e o Cargo cria seus arquivos em um diretório com o mesmo nome.

Entre no diretório _hello_cargo_ e liste os arquivos. Você verá que o Cargo gerou dois arquivos e um diretório para nós: um arquivo _Cargo.toml_ e um diretório _src_ com um arquivo _main.rs_ dentro.

Também inicializou um novo repositório Git junto com um arquivo _.gitignore_. Os arquivos Git não serão gerados se você executar `cargo new` dentro de um repositório Git existente; você pode substituir esse comportamento usando `cargo new --vcs=git`.

> Nota: Git é um sistema de controle de versão comum. Você pode mudar `cargo new` para usar um sistema de controle de versão diferente ou nenhum sistema de controle de versão usando a flag `--vcs`. Execute `cargo new --help` para ver as opções disponíveis.

Abra _Cargo.toml_ no seu editor de texto preferido. Deve ser parecido com o código na Listagem 1-2.

<span class="filename">Nome do arquivo: Cargo.toml</span>

```toml
[package]
name = "hello_cargo"
version = "0.1.0"
edition = "2021"

# Veja mais chaves e suas definições
# em https://doc.rust-lang.org/cargo/reference/manifest.html

[dependencies]
```

Este arquivo está no formato _TOML_ (Tom's Obvious, Minimal Language), que é o formato de configuração do Cargo.

A primeira linha, `[package]`, é um cabeçalho de seção que indica que as declarações seguintes estão configurando um pacote. À medida que adicionarmos mais informações a este arquivo, adicionaremos outras seções.

As próximas três linhas definem as informações de configuração que o Cargo precisa para compilar seu programa: o nome, a versão e a edição do Rust a ser usada. Falaremos sobre a chave `edition` no Apêndice E.

A última linha, `[dependencies]`, é o início de uma seção para você listar todas as dependências do seu projeto. Em Rust, chamamos os pacotes de código de _crates_. Não precisaremos de nenhum outro crate para este projeto, mas precisaremos para o primeiro projeto do Capítulo 2, então usaremos esta seção de dependências lá.

Agora abra _src/main.rs_ e dê uma olhada:

<span class="filename">Nome do arquivo: src/main.rs</span>

```rust{.line-numbers}
fn main() {
    println!("Olá, mundo!");
}
```

O Cargo gerou um programa "Olá, mundo!" para você, igual ao que escrevemos na Listagem 1-1! Até agora, as diferenças entre nosso projeto e o projeto gerado pelo Cargo são que o Cargo colocou o código no diretório _src_ e temos um arquivo de configuração _Cargo.toml_ no diretório principal.

O Cargo espera que seus arquivos fonte estejam dentro do diretório _src_. O diretório do projeto de nível superior é apenas para arquivos README, informações de licença, arquivos de configuração e qualquer outra coisa não relacionada ao seu código. Usar o Cargo ajuda você a organizar seus projetos. Há um lugar para tudo, e tudo está no seu lugar.

Se você iniciou um projeto que não usa o Cargo, como fizemos com o projeto "Olá, mundo!", você pode convertê-lo em um projeto que usa o Cargo. Mova o código do projeto para o diretório _src_ e crie um arquivo _Cargo.toml_ apropriado. Uma maneira fácil de obter esse arquivo _Cargo.toml_ é executar `cargo init`, que o criará automaticamente para você.

### Construindo e executando um projeto Cargo

Agora vamos ver o que é diferente quando construímos e executamos o programa "Olá, mundo!" com o Cargo! No seu diretório _hello_cargo_, construa seu projeto digitando o seguinte comando:

```console
$ cargo build
   Compiling hello_cargo v0.1.0 (file:///projects/hello_cargo)
    Finished dev [unoptimized + debuginfo] target(s) in 2.85 secs
```

Este comando cria um arquivo executável em _target/debug/hello_cargo_ (ou _target\debug\hello_cargo.exe_ no Windows) em vez de no seu diretório atual. Como a compilação padrão é uma compilação de debug, o Cargo coloca o binário em um diretório chamado _debug_. Você pode executar o executável com este comando:

```console
$ ./target/debug/hello_cargo # ou .\target\debug\hello_cargo.exe no Windows
Olá, mundo!
```

Se tudo correr bem, `Olá, mundo!` deve ser impresso no terminal. Executar `cargo build` pela primeira vez também faz com que o Cargo crie um novo arquivo no nível superior: _Cargo.lock_. Este arquivo acompanha as versões exatas das dependências em seu projeto. Este projeto não tem dependências, então o arquivo está um pouco vazio. Você nunca precisará mudar este arquivo manualmente; o Cargo gerencia seu conteúdo para você.

Acabamos de construir um projeto com `cargo build` e o executamos com `./target/debug/hello_cargo`, mas também podemos usar `cargo run` para compilar o código e então executar o executável resultante, tudo em um comando:

```console
$ cargo run
    Finished dev [unoptimized + debuginfo] target(s) in 0.0 secs
     Running `target/debug/hello_cargo`
Olá, mundo!
```

Usar `cargo run` é mais conveniente do que ter que lembrar de executar `cargo build` e então usar o caminho completo para o binário, então a maioria dos desenvolvedores usa `cargo run`.

Observe que desta vez não vimos a saída indicando que o Cargo estava compilando `hello_cargo`. O Cargo percebeu que os arquivos não haviam mudado, então não recompilou, apenas executou o binário. Se você tivesse modificado seu código-fonte, o Cargo teria recompilado o projeto antes de executá-lo, e você teria visto esta saída:

```console
$ cargo run
   Compiling hello_cargo v0.1.0 (file:///projects/hello_cargo)
    Finished dev [unoptimized + debuginfo] target(s) in 0.33 secs
     Running `target/debug/hello_cargo`
Olá, mundo!
```

O Cargo também fornece um comando chamado `cargo check`. Este comando verifica rapidamente seu código para garantir que ele compila, mas não produz um executável:

```console
$ cargo check
   Checking hello_cargo v0.1.0 (file:///projects/hello_cargo)
    Finished dev [unoptimized + debuginfo] target(s) in 0.32 secs
```

Por que você não iria querer um executável? Frequentemente, `cargo check` é muito mais rápido que `cargo build`, porque pula a etapa de produzir um executável. Se você estiver verificando continuamente seu trabalho enquanto escreve o código, usar `cargo check` acelerará o processo de informar se seu projeto ainda está compilando! Como tal, muitos Rustaceans executam `cargo check` periodicamente enquanto escrevem seu programa para garantir que ele ainda está compilando. Então eles executam `cargo build` quando estão prontos para usar o executável.

Vamos recapitular o que aprendemos até agora sobre o Cargo:

- Podemos criar um projeto usando `cargo new`.
- Podemos construir um projeto usando `cargo build`.
- Podemos construir e executar um projeto em uma etapa usando `cargo run`.
- Podemos construir um projeto sem produzir um binário para verificar erros usando `cargo check`.
- Em vez de salvar o resultado da compilação no mesmo diretório que nosso código, o Cargo o armazena no diretório _target/debug_.

Uma vantagem adicional de usar o Cargo é que os comandos são os mesmos, independentemente do sistema operacional em que você esteja trabalhando. Então, a partir deste ponto, não forneceremos mais instruções específicas para Linux e macOS versus Windows.

### Compilando para lançamento

Quando seu projeto estiver finalmente pronto para lançamento, você pode usar `cargo build --release` para compilá-lo com otimizações. Este comando criará um executável em _target/release_ em vez de _target/debug_. As otimizações fazem seu código Rust rodar mais rápido, mas ativá-las aumenta o tempo que leva para seu programa compilar. É por isso que existem dois perfis diferentes: um para desenvolvimento, quando você quer reconstruir rapidamente e frequentemente, e outro para construir o programa final que você dará a um usuário que não será reconstruído repetidamente e que rodará o mais rápido possível. Se você estiver fazendo benchmarks do tempo de execução do seu código, certifique-se de executar `cargo build --release` e fazer o benchmark com o executável em _target/release_.

### Cargo como convenção

Com projetos simples, o Cargo não oferece muito valor além de apenas usar `rustc`, mas provará seu valor à medida que seus programas se tornarem mais intrincados. Uma vez que os programas cresçam para vários arquivos ou precisem de uma dependência, é muito mais fácil deixar o Cargo coordenar a compilação.

Mesmo que o projeto `hello_cargo` seja simples, ele agora usa muito das ferramentas reais que você usará no resto da sua carreira Rust. De fato, para trabalhar em qualquer projeto existente, você pode usar os seguintes comandos para verificar o código usando Git, mudar para o diretório desse projeto e construir:

```console
$ git clone example.org/someproject
$ cd someproject
$ cargo build
```

Para mais informações sobre o Cargo, confira [sua documentação](https://doc.rust-lang.org/cargo/).

## Resumo

Você já está com um ótimo começo na sua jornada Rust! Neste capítulo, você aprendeu como:

- Instalar a versão estável mais recente do Rust usando `rustup`
- Atualizar para uma versão mais nova do Rust
- Abrir a documentação instalada localmente
- Escrever e executar um programa "Olá, mundo!" usando `rustc` diretamente
- Criar e executar um novo projeto usando as convenções do Cargo

Este é um ótimo momento para construir um programa mais substancial para se acostumar a ler e escrever código Rust. Então, no Capítulo 2, vamos construir um programa de jogo de adivinhação. Se você preferir começar aprendendo como conceitos de programação comuns funcionam em Rust, veja o Capítulo 3 e depois volte ao Capítulo 2.
