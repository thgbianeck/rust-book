## Vamos Começar: Instalando o Rust!

Bem-vindo ao mundo do Rust! Vamos dar o primeiro passo juntos: instalar o Rust em seu computador. Usaremos uma ferramenta incrível chamada `rustup`, que é como um assistente mágico para gerenciar tudo relacionado ao Rust. Só não se esqueça: você vai precisar de internet para baixar!

> Dica de amigo: Se por algum motivo você não quiser usar o `rustup`, não se preocupe! Dê uma olhada na [página de Métodos Alternativos de Instalação do Rust](https://forge.rust-lang.org/infra/other-installation-methods.html). Tem outras opções lá!

Seguindo os passos abaixo, você vai instalar a versão mais recente e estável do Rust. O legal é que o Rust é super confiável: os exemplos que você encontrar neste livro vão continuar funcionando mesmo com as novas versões. As mensagens de erro e avisos podem ficar ainda melhores com o tempo, mas o básico permanece o mesmo.

> ### Falando a língua do terminal
>
> Ao longo do livro, vamos usar alguns comandos de terminal. Sempre que você vir um `$` no início da linha, é a deixa para você digitar o comando (mas não precisa digitar o `$`, tá?). Se não tiver o `$`, geralmente é o computador respondendo ao seu comando. Ah, e se você estiver usando PowerShell no Windows, vai ver um `>` no lugar do `$`.

### Instalando o Rust no Linux ou macOS

Se você está no time Linux ou macOS, abra seu terminal e digite este comando mágico:

```console
$ curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
```

Este comando vai baixar um script e iniciar a instalação do `rustup`, que por sua vez vai instalar o Rust mais recente. Pode ser que peça sua senha. Se tudo der certo, você vai ver esta mensagem animadora:

```text
Rust is installed now. Great!
```

Você também vai precisar de um _linker_. É como um ajudante que o Rust usa para juntar as peças do seu programa. Provavelmente você já tem um, mas se tiver problemas, pode ser necessário instalar um compilador C. Isso é útil porque alguns pacotes Rust dependem de código C.

No macOS, é só rodar:

```console
$ xcode-select --install
```

Se você usa Linux, geralmente precisa instalar o GCC ou Clang. Dê uma olhada na documentação da sua distribuição. Por exemplo, no Ubuntu, você pode instalar o pacote `build-essential`.

### Instalando o Rust no Windows

Para o pessoal do Windows, é só visitar [https://www.rust-lang.org/tools/install](https://www.rust-lang.org/tools/install) e seguir as instruções. Em algum momento, vai pedir para instalar o Visual Studio. Não se assuste! Isso traz ferramentas importantes para o Rust funcionar no Windows. Se precisar de ajuda extra, dá uma olhada [neste guia](https://rust-lang.github.io/rustup/installation/windows-msvc.html).

Os comandos que usamos no livro funcionam tanto no bom e velho cmd.exe quanto no PowerShell. Se houver diferenças, a gente avisa!

### Ops, algo deu errado?

Vamos verificar se o Rust está instalado corretamente. Abra seu terminal e digite:

```console
$ rustc --version
```

Se tudo estiver certo, você verá algo assim:

```text
rustc x.y.z (abcabcabc yyyy-mm-dd)
```

Isso significa que o Rust está instalado e pronto para usar! Se não aparecer, vamos checar se o Rust está no lugar certo do sistema.

No Windows CMD:

```console
> echo %PATH%
```

No PowerShell:

```powershell
> echo $env:Path
```

No Linux e macOS:

```console
$ echo $PATH
```

Se ainda assim o Rust não estiver funcionando, não desanime! Tem muita gente pronta para ajudar. Dá uma olhada na [página da comunidade Rust](https://www.rust-lang.org/community) para encontrar outros Rustaceans (é assim que a gente se chama, legal né?).

### Mantendo o Rust em dia

Atualizar o Rust é moleza com o `rustup`. Só rodar:

```console
$ rustup update
```

E se um dia você quiser desinstalar (espero que não!), é só usar:

```console
$ rustup self uninstall
```

### Documentação na palma da mão

Sabia que o Rust vem com a documentação offline? É verdade! Para abrir, use:

```console
$ rustup doc
```

Sempre que você encontrar um tipo ou função da biblioteca padrão e ficar na dúvida, consulte a documentação da API. Ela é sua melhor amiga na jornada Rust!
