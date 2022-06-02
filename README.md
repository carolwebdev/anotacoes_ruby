# Anotações dos meus estudos de Ruby

## Estrutura de Dados
<details>
  <summary> Arrays </summary>
  <br />
  <summary> Métodos </summary> <br />
    
```rb
numeros = [1, 2, 3] #-> cria o array numeros
numeros.first #-> acessa o primeiro elemento do array numeros
numeros.last #-> acessa o último elemento
numeros << 4 #-> adiciona o elemento 4 ao final do array
```

  Para criar um array de palavras, podemos fazer de duas formas: <br />
`palavras = ['ola', 'mundo'] ou palavras = %w{ola mundo}`
 <br /> <br /> Com o *%w* dá pra fazer interpolação dentro do próprio array: 
  ```rb
palavras = %w{ola #{nome}}
```
  <br />  
  <br /> <summary> Percorrer o array </summary> <br />
  Para percorrer todos os itens do array, primeiro precisa popular o array (.new) e depois usar o loop for:
  <br />
  <br />
  
```rb
biblioteca = Biblioteca.new 
  for livro in biblioteca.livros do
    p livro.valor 
  end
```
  <br />
</details> 
<details>
  <summary> Hash </summary> 
  Com o Hash é possível separar os itens por categorias, por meio da adição de atributos.Para acessar cada valor, precisamos passar um objeto que representa a chave identificadora, em vez de passar um inteiro que represente o índice (como acontece no caso do array).  
  
  <br /> <summary> Inicialização do Hash </summary> 
  Para inicializar a *hash* livros faremos:
  
`livros = {}`
  
  <br /> <summary> Chave e Valor </summary> <br />
   A chave do Hash é um identificador único e, geralmente, é um símbolo *(:teste)*. Já o valor é qualquer tipo de objeto ruby. Para acessar um valor dentro de um Hash, basta invocar o método *[:chave]*, passando a chave identificadora do container. </br> </br>
  
   <br /> <summary> Operador ||= </summary> <br />
   Existe também o operador ||=, que executa o mesmo comportamento do *unless*, ou seja, só vai incluir um elemento no *hash* se o valor daquele índice for *nil*. Senão, vai manter o valor que já está lá, mas não vai retornar nenhum erro.
      
   <br /> <summary> Método Set </summary> <br />
   O método *set* precisa ser importado (arquivo *set.rb*, que já vem junto com o interpretador). A classe *Set* tem um método *initialize* que recebe um array com os elementos que formarão a coleção, e desses elementos ele só guarda os que não são repetidos. Exemplo:
   
```rb
require 'set'
numero_sem_repeticao = Set.new [1, 2, 2, 3, 2, 1]
for numero in numero_sem_repeticao do
  p numero
end
```

</details>

## Programação Funcional
<details>
  <summary> Funções Puras </summary>
  <br />
As funções criadas nas linguagens imperativas podem causar efeitos colaterais, alterando o valor calculado anteriormente. O resultado da função, quando invocada, vai depender do estado atual no momento de sua execução. No paradigma funcional, as funções dependem apenas dos argumentos passados em sua chamada, então vão ter sempre o mesmo resultado. Essas são as funções puras.   <br />
Um exemplo de função pura é o método *upcase* aplicado a uma string. Ele vai criar outra string com as letras maiúsculas, em vez de alterar a string original. Todavia, se utilizarmos o método *upcase!*, ele vai alterar a string original. Assim, o método deixa de ser funcional puro, porque passa a ter efeitos colaterais.  
  
<br /> <summary> Método for x map </summary> 

O *for* retorna um array com os mesmos valores inseridos no array antigo, assim como o *each*. Já o *map* cria um novo array com os valores retornados por cada interação.
  
<br /> <summary> Métodos sem return </summary> 
  Todo método em Ruby retorna o resultado da última expressão declarada, sem a necessidade de colocar um *return*

</details>
<details> 
  <summary> Funções de Alta Ordem </summary>
  <br />
São funções de alta ordem aquelas que têm a capacidade de receber outras funções como argumentos ou retornar funções como resultado. Isso é feito usando *Blocos*, *Lambdas* e *Procs*.
  <summary> Blocos </summary>
  <br />
  Blocos são muito utilizados para percorrer coleções. Exemplo:
  
  ```rb
  numeros = [1, 2, 3, 4]
  numeros.each { |numero| p numero }
  # => 1
  # => 2
  # => 3
  # => 4
  ```
  
  Agora, se quiser criar um bloco próprio, precisa chamar o método yield, passando os argumentos que serão recebidos pelo bloco declarado na chamada do método. O yield executará automaticamente o bloco que for passado na chamada do método. Blocos são uma maneira de flexibilizar os métodos da API. 
 <br />
  Para evitar que retorne um erro porque nenhum bloco foi informado, podemos usar o método *block_given?*. Exemplo:
  
```rb
class Biblioteca
  def livros_por_categoria(categoria)
      @livros[categoria].each do |livro|
          yield livro if block_given?
      end
  end
end
```
  
  lalal
  <summary> Lambdas </summary>
  <br />
  <summary> Procs </summary>
  <br />
  <summary> Funções de Alta Ordem </summary>
  <br />
</details>
