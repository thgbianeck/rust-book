## Olá, Mundo!

Agora que você já instalou o Rust, vamos criar seu primeiro programa! É uma tradição quando se aprende uma nova linguagem escrever um programinha que mostra "Olá, mundo!" na tela. Vamos fazer isso juntos!

> Observação: Este livro pressupõe que você já tenha uma familiaridade básica com a linha de comando. O Rust não exige nada específico sobre onde seu código fica ou quais ferramentas você usa. Se preferir usar um ambiente de desenvolvimento integrado (IDE) em vez da linha de comando, fique à vontade! Muitas IDEs já têm suporte para Rust. A equipe do Rust tem se concentrado em melhorar o suporte às IDEs através do `rust-analyzer`. Dê uma olhada no Apêndice D para mais detalhes.

### Criando um diretório para o projeto

Vamos começar criando um lugar para guardar seu código Rust. O Rust não se importa onde seu código fica, mas para os exercícios e projetos deste livro, sugerimos criar uma pasta chamada _projects_ no seu diretório pessoal.

Abra um terminal e digite os seguintes comandos para criar a pasta _projects_ e uma subpasta para o projeto "Olá, mundo!".

Para Linux, macOS e PowerShell no Windows, use:

```console
$ mkdir ~/projects
$ cd ~/projects
$ mkdir hello_world
$ cd hello_world
```

Para o CMD do Windows, use:

```cmd
> mkdir "%USERPROFILE%\projects"
> cd /d "%USERPROFILE%\projects"
> mkdir hello_world
> cd hello_world
```

### Escrevendo e executando um programa Rust

Agora, vamos criar um novo arquivo chamado _main.rs_. Os arquivos Rust sempre terminam com a extensão _.rs_. Se o nome do arquivo tiver mais de uma palavra, use um underscore para separá-las. Por exemplo, use _hello_world.rs_ em vez de _helloworld.rs_.

Abra o arquivo _main.rs_ que você acabou de criar e digite o código da Listagem 1-1.

<span class="filename">Nome do arquivo: main.rs</span>

```rust{.line-numbers}
fn main() {
    println!("Olá, mundo!");
}
```

<figcaption>Listagem 1-1: Um programa que imprime "Olá, mundo!"</figcaption>

Salve o arquivo e volte para a janela do terminal na pasta _~/projects/hello_world_. No Linux ou macOS, digite os seguintes comandos para compilar e executar o arquivo:

```console
$ rustc main.rs
$ ./main
Olá, mundo!
```

No Windows, use `.\main.exe` em vez de `./main`:

```powershell
> rustc main.rs
> .\main.exe
Olá, mundo!
```

Independentemente do seu sistema operacional, você deve ver a frase "Olá, mundo!" impressa no terminal. Se não vir essa saída, volte à seção "Solução de problemas" da parte de Instalação para obter ajuda.

Se "Olá, mundo!" apareceu, parabéns! Você acabou de escrever oficialmente um programa em Rust. Isso faz de você um programador Rust - bem-vindo ao clube!

### Anatomia de um programa Rust

Vamos dar uma olhada mais detalhada nesse programa "Olá, mundo!". Aqui está a primeira parte do quebra-cabeça:

```rust{.line-numbers}
fn main() {

}
```

Essas linhas definem uma função chamada `main`. A função `main` é especial: é sempre o primeiro código a ser executado em todo programa Rust. Aqui, a primeira linha declara uma função chamada `main` que não tem parâmetros e não retorna nada. Se houvesse parâmetros, eles iriam dentro dos parênteses `()`.

O corpo da função está entre chaves `{}`. O Rust exige chaves ao redor de todos os corpos de função. É considerado um bom estilo colocar a chave de abertura na mesma linha da declaração da função, com um espaço entre elas.

> Observação: Se quiser seguir um estilo padrão em todos os projetos Rust, você pode usar uma ferramenta de formatação automática chamada `rustfmt` para formatar seu código de uma maneira específica (mais sobre `rustfmt` no Apêndice D). A equipe do Rust incluiu esta ferramenta com a distribuição padrão do Rust, assim como o `rustc`, então ela já deve estar instalada no seu computador!

O corpo da função `main` contém o seguinte código:

```rust{.line-numbers}
    println!("Olá, mundo!");
```

Esta linha faz todo o trabalho neste pequeno programa: ela imprime texto na tela. Há quatro detalhes importantes para notar aqui:

1. O estilo Rust é usar quatro espaços para indentação, não uma tabulação.

2. `println!` chama uma macro Rust. Se fosse uma função normal, seria escrito como `println` (sem o `!`). Discutiremos as macros do Rust em mais detalhes no Capítulo 19. Por enquanto, você só precisa saber que usar `!` significa que você está chamando uma macro em vez de uma função normal, e que macros nem sempre seguem as mesmas regras que as funções.

3. Você vê a string `"Olá, mundo!"`. Passamos esta string como um argumento para `println!`, e ela é impressa na tela.

4. Terminamos a linha com um ponto e vírgula (`;`), o que indica que esta expressão terminou e a próxima está pronta para começar. A maioria das linhas de código Rust termina com um ponto e vírgula.

### Compilação e execução são etapas separadas

Você acabou de executar um programa recém-criado, então vamos examinar cada etapa do processo.

Antes de executar um programa Rust, você deve compilá-lo usando o compilador Rust digitando o comando `rustc` e passando o nome do seu arquivo fonte, assim:

```console
$ rustc main.rs
```

Se você tem experiência com C ou C++, notará que isso é semelhante a `gcc` ou `clang`. Após compilar com sucesso, o Rust gera um executável binário.

No Linux, macOS e PowerShell no Windows, você pode ver o executável digitando o comando `ls` no seu shell:

```console
$ ls
main  main.rs
```

No Linux e macOS, você verá dois arquivos. Com o PowerShell no Windows, você verá os mesmos três arquivos que veria usando o CMD. Com o CMD no Windows, você digitaria o seguinte:

```cmd
> dir /B %= a opção /B diz para mostrar apenas os nomes dos arquivos =%
main.exe
main.pdb
main.rs
```

Isso mostra o arquivo do código-fonte com a extensão _.rs_, o arquivo executável (_main.exe_ no Windows, mas _main_ em todas as outras plataformas) e, ao usar o Windows, um arquivo contendo informações de depuração com a extensão _.pdb_. A partir daqui, você executa o arquivo _main_ ou _main.exe_, assim:

```console
$ ./main # ou .\main.exe no Windows
```

Se o seu _main.rs_ é o programa "Olá, mundo!", esta linha imprimirá `Olá, mundo!` no seu terminal.

Se você está mais familiarizado com uma linguagem dinâmica, como Ruby, Python ou JavaScript, pode não estar acostumado a compilar e executar um programa como etapas separadas. Rust é uma linguagem compilada antecipadamente, o que significa que você pode compilar um programa e dar o executável para alguém, e eles podem executá-lo mesmo sem ter o Rust instalado. Se você der a alguém um arquivo _.rb_, _.py_ ou _.js_, eles precisam ter uma implementação de Ruby, Python ou JavaScript instalada (respectivamente). Mas nessas linguagens, você só precisa de um comando para compilar e executar seu programa. Tudo é uma troca na concepção da linguagem.

Compilar apenas com `rustc` é bom para programas simples, mas à medida que seu projeto cresce, você vai querer gerenciar todas as opções e facilitar o compartilhamento do seu código. A seguir, vamos apresentar a ferramenta Cargo, que o ajudará a escrever programas Rust do mundo real.
