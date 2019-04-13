# Simple Overview Go

A linguagem **Go** foi lançada em 2009 com propósito de facilitar a resolução de problemas quando o assunto é desenvolvimento em **camadas de rede, escalabilidade, desempenho, produtividade e o mais importante concorrência.**

**Go** teve influências de diversas linguagens de programação e paradigmas diferentes, e se sobressaiu ao juntar o que tinham de melhor e criou algo novo e enxuto, com o mínimo necessário para resolver os problemas propostos, acredito que isto podemos chamar de **inovação**. Go inovou ao quebrar os paradigmas de linguagens e implementar algo novo de forma simples e muito poderosa.

Um dos pontos mais relevantes e importantes é o trablho com **concorrência**, ele inovou ao quebrar o modelo tradicional de threads e sua forma de utilização ao criar um novo modelo, as **goroutines**.
As **goroutines** são responsáveis por realizar execuções em **Go** de forma **assíncrona**. São muito poderosas e uma simples máquina de 1G de Ram poderá subir milhares delas.

**Concorrência** em **Go** é muito poderosa e também simples de codar. A resolução de muitos problemas é bem mais eficiente utilizando **concorrência** e este é o **poder** de **Go**, por isto, se tornou um **Deus** quando o assunto é **concorrẽncia**. Devido a isto, problemas englobados neste universo serão resolvidos com muita eficiência e o mais importante, com muito pouco recurso computacional.

Para se ter uma pequena ideia, em uma máquina de **1CPU e 1G Ram**, conseguimos com uma API simples, com poucas linhas de código, aguentar de **5k a 6k** requisições por segundo em um protocolo **TCP**, utilizando **RPC** ou **TCP nativo** e gravando em um banco de dados relacional como o **Postgresql**, sem derrubá-lo e consumindo em média somente 60Mb a 70Mb de memória e de **8% a 15% de CPU**.

Para projetos simples ou complexos Go sempre será uma excelente alternativa, pois torna tudo mais simples e enxuto, fácil de codar e dar manutenção.

**Go** é uma linguagem compilada, um **like de C**, muito focada na produtividade.

**Exemplos** na Internet mostrando soluções utilizando **concorrência** e a eficiência da da liguagem para resolver problemas e utilizando **pouco recurso computacional**.

1) Lendo um arquivo txt de **3G** e fazendo parse em menos de **5 segundos**.

[Reading large files](https://marcellanz.com/post/file-read-challenge)

--------------------------------------------------------------------------------------

### Alguns exemplos simples

Hello World..
```go
package main
import "fmt"
func main() {
    fmt.Printf("Olá, eu amo Go!\n")
}
```
Executando seu programa sem precisar compilar
```bash
$ go run main.go
```

Compilando seu programa
```bash
$ go build -o main main.go
```

Uma API em Go, fazendo um Get no google
```go
package main

import (
    "fmt"
    "io/ioutil"
    "net/http"
    "os"
)

func main() {
    resp, err := http.Get("https://google.com")
    check(err)
    body, err := ioutil.ReadAll(resp.Body)
    check(err)
    fmt.Println(len(body))
}

func check(err error) {
    if err != nil {
        fmt.Println(err)
        os.Exit(1)
    }
}
```
Executando seu programa sem precisar compilar
```bash
$ go run main.go
```

Uma API simples
```go
package main

import (
    "fmt"
    "log"
    "net/http"
)

func Hello(w http.ResponseWriter, r *http.Request) {
    w.WriteHeader(http.StatusOK)
    w.Write([]byte("Hello, welcome to the world, Go!"))
}

func main() {

    mux := http.NewServeMux()
    mux.Handle("/api/hello", http.HandlerFunc(Hello))

    server :=
        &http.Server{
            Addr:    ":8080",
            Handler: mux,
        }

    fmt.Printf("Server Run port: 8080\n")
    if err := server.ListenAndServe(); err != nil {
        log.Printf("Eror while serving metrics: %s", err)
    }
}
```
Executando seu programa sem precisar compilar
```bash
$ go run main.go
```

Testando sua API com **cURL**
```bash
$ curl localhost:8080/api/hello
```
