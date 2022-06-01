# Anotações dos meus estudos de Ruby

## Estrutura de Dados
<details>
  <summary> Arrays </summary>
  <summary> Métodos </summary>
  numeros = [1, 2, 3] -> cria o array numeros <br />
  numeros.first -> acessa o primeiro elemento do array numeros <br />
  numeros.last -> acessa o último elemento <br />
  numeros << 4 -> adiciona o elemento 4 ao final do array <br />
  Para criar um array de palavras, podemos fazer de duas formas: <br />
  palavras = ['ola', 'mundo'] ou palavras = %w{ola mundo} <br />
  Com o %w dá pra fazer interpolação dentro do próprio array: palavras = %w{ola #{nome}} <br />
  <summary> Percorrer o array </summary>
  Para percorrer todos os itens do array, primeiro precisa popular o array (.new) e depois usar o loop for: </br>
          ```ruby
          biblioteca = Biblioteca.new 
          for livro in biblioteca.livros do
              p livro.valor 
          end
  ```
</details>
<details>
  <summary> Hash </summary> </br>
</details>

## Programação Funcional
