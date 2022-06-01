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
 <br /> <br /> Com o %w dá pra fazer interpolação dentro do próprio array: 
  ```rb
palavras = %w{ola #{nome}}
```
  <br />  
  <summary> Percorrer o array </summary>
  <br /> Para percorrer todos os itens do array, primeiro precisa popular o array (.new) e depois usar o loop for: 
  
```rb
biblioteca = Biblioteca.new 
  for livro in biblioteca.livros do
    p livro.valor 
  end
```
  <br />
</details> 
<details>
  <summary> Hash </summary> </br>
  Com o Hash é possível separar os itens por categorias, por meio da adição de atributos.Para acessar cada valor, precisamos passar um objeto que representa a chave identificadora, em vez de passar um inteiro que represente o índice (como acontece no caso do array). Para inicializar a hash livros faremos:
  
`livros = {}`
  
   A chave do Hash é um identificador único e, geralmente, é um símbolo (:teste). Já o valor é qualquer tipo de objeto ruby. Para acessar um valor dentro de um Hash, basta invocar o método [:chave], passando a chave identificadora do container.
   <br />
   Existe também o operador ||=, que executa o mesmo comportamento do unless, ou seja, só vai incluir um elemento no hash se o valor daquele índice for nil. Senão, vai manter o valor que já está lá, mas não vai retornar nenhum erro.
   <br />
   O método set precisa ser importado (arquivo set.rb, que já vem junto com o interpretador). A classe Set tem um método initialize que recebe um array com os elementos que formarão a coleção, e desses elementos ele só guarda os que não são repetidos. Exemplo:
   
```rb
require 'set'
numero_sem_repeticao = Set.new [1, 2, 2, 3, 2, 1]
for numero in numero_sem_repeticao do
  p numero
end
```

</details>

## Programação Funcional
