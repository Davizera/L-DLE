# Notas
Algumas anotações e links que fiz e usei para estudar durante o curso, [C#: Eventos, Delegates e Lambda](https://cursos.alura.com.br/course/csharp-eventos-delegates-lambda).  
Tópicos dividos de acordo com os tópicos do curso.

# Aula 1: Comportamentos e eventos
### Modificador `partial`:
Muito usado em classes, ele permite que você consiga definir classes em mais de um arquivo, por exemplo: caso você tenha uma classe muito grande, nisso é possível dividi-lá em arquivos do tipo um arquivo só para a definição de métodos, outro para definição de propriedades e por aí em diante.  
Quando o código é compilado todas as fontes são mergeadas.  
Caso em algum dos arquivos seja realizado a herença de uma classe qualquer TODO os arquivos terão isso repassado. (Não era de se esperar outra coisa né? Imagina uma classe que apenas parte dela é herdada 😲😲😲).  
Os arquivos que editam a class com o modificador `partial` devem estar no mesmo módulo/dll.  

# Aula 2: Delegates
### O que é um `delegate`?
É uma estrutura de dados paara a representação fortemente tipada da assinatura de um método, seu tipo de retorno, a ordem e os tipos de seu parâmetros.
é possível fazer uma cadeia de execução com os delegates, pois eles herdam da classe abstrata `delegate` que sabe lidar com esse tipo de operação. Desta maneira, a gente pode manipular de uma melhor forma o fluxo de comportamento dos métodos. (Isso foi visto mais adiante no curso)  
**OBS**: os `delegates` permitem que a gente trabalhe com métodos como se fossem objetos! Como acontece no javascripto.  
*Ex.*: Suponhamos o seguinte código.
```csharp
// Exemplo abaixo soma os métodos, fazendo com que o OkEventHandler 
// tenha a seguinte cadeia de execução: Btn_Click -> Fechar. 
// Isso é possível graças a classe `MulticastDelegate`
var OkEventHandler = (EventeHandler)Btn_Click + (EventHandler)Fechar;
```
**OBS**: essa implementação acima me lembrou muito o design pattern de chain of responsability (cadeia de responsabilidade).


### O que é um `event`?
É uma mensagem de algo que aconteceu, seja um clique em um botão, uma mudança no item selecionado de uma lista ou uma pausa em um serviço do windows.  
Podemos assinar eventos para receber essa notificações de que determinada aconteceu por meio de delegates ou métodos anônimos que dêem match com a assinatura requisitada pelo evento. (Vimos mais sobre isso um pouco mais adiante no curso)
Algo importante de citar é, não é possível mudar o comportamento de um evento, apenas adicionar/remover (usando os operadores mostrados acima com o exemplo do delegate, +=, -= ou então os métodos do evento que pode adicionar/remover) comportamentos à ele atribuídos.  
**OBS**: a assinatura do delegate devem dar match com a do evento que está sendo assinado.
# Aula 3: Manipulando Delegates


# Aula 4: Funções e nosso próprio evento


# Aula 5: Avançando em eventos