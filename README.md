# Simple Overview Go

A linguagem **Go** foi lançada em 2009 com propósito de torna as coisas mais fáceis para resolução de problemas quando o assunto é desenvolvimento em **camadas de rede, escalabilidade, desempenho, produtividade e o mais importante concorrência.**

Go teve muitas influências de diversos paradigmas de linguagens e quebrou muitas delas ao criar algo novo e enxuto com o mínimo necessário para resolver os problemas propostos isto eu chamo de **inovação**, **Go** inovou ao quebrar os paradigmas de linguagens e implementar algo novo de forma simples e muito poderoso.

Um dos pontos mais relevantes e importantes é o trablho com **concorrência** ele inovou ao quebrar o modelo tradicional de threads e sua nova forma de utilização ao criar as **goroutines.**
As **goroutines** são responsáveis por executarmos as coisas em **Go** de forma **assíncrona**, muito poderosas e uma simples máquina de **1G de Ram** poderá subir milhares delas.

**Go** é muito poderoso e o mais importante simples de codar,  a resolução de muitos problemas é bem mais eficiente utilizando **concorrência** este é o **poder de Go** por isto ele tornou um **Deus** quando o assunto é **concorrẽncia** e devido a isto todos os problemas englobados neste universo ele irá resolver com muita eficiência e o mais importante com muito **pouco recurso computacional**.

Para ter uma pequena ideia em uma máquina de **1CPU e 1G Ram** conseguimos com uma API simples com poucas linhas aguentar **5k a 6k** por segundo de requests em um protocolo** TCP** utilizando **RPC** ou nativo **TCP** e gravando em um banco de dados Relacional o Postgresql, sem derrubar o postgres consumindo em média somente 60Mb a 70Mb de memória de 8% a 15% de CPU..
Exemplos na net é que não faltam mostrando soluções utilizando **concorrência** e a eficiência monstro que ocorre quando utilizado **Go**.

Para projetos simples ou complexos **Go** sempre será uma excelente alternativa, pois torna-se tudo mais simples e enxuto para codar, dar manutenção.

**Go** é uma linguagem compilada um like de **C** muito focada na produtividade.

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
