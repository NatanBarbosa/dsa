# Enter container
docker run -it -v .:/usr/src/dsa --workdir /usr/src/dsa  python sh

# Introdução a estrutura de dados

### Para que serve

- Melhor resolução de problemas
- Habilidade lógica de programação
- Intuição de escalabilidade
- habilidade agnóstica a linguagens

---

# Big O Notation

- Fala sobre escalabilidade, não necessariamente performance
- Diz o quanto o algorítimo escala com o tamanho do input
- Apesar de O(n) melhor que O(n2), não necessariamente o segundo vai performar melhor, mas ele vai escalar melhor para inputs maiores

## Complexidade temporal x Complexidade espacial
- Tempo de execução (runtime)
- exemplo: percorrer cada elemento de um array um por um para descobrir o maior elemento
- **Complexidade temporal:** Quantos acessos teve que fazer no array
    - Nesse caso, foi O(n), pq teve que percorrer elemento por elemento
- **Complexidade espacial:** Quanto de memória adicional foi necessário alocar
    - Nesse caso, foi O(1), pq só precisou alocar 1 espaço na memória para aramzenar o maior valor

## Classificações de Big(o)

Da que melhor escala pra que pior escala

### O(1)

- Temp/memória constante
- Independente do tamanho do input, tem o mesmo tempo de execução
- Independente do tamanho do input, o requisito de memória continua sendo o mesmo
- Exemplo: Encontrar o primeiro elemento em um array
    - Tempo: Esse algorítimo sempre terá o mesmo tempo, pq a gente já sabe a posição - O(1)
    - Memória: A gente só vai precisar alocar um novo espaço na memória - O(1)
- Exemplo 2: Encontrar os maiores 15 elementos de um array
    - Memória: O algorítimo sempre vai precisar de apenas 15 espaços na memória, idependente do tamanho do array - O(1)

### O(log n)

Primeiro. Logartimo = Quantas vezes o número precisa ser multiplicado por ele mesmo paradar o resultado da base

Exemplo: $$\log_{10} 100$$ = 2 -> Pq 10^2 = 100

Segundo. Escala logarítmica é uma escala onde, em vz dos valores aumentarem de 1 em 1, eles aumentam multiplicados por um valor fixo.

Exemplo: 1 → 10 → 100 → 1.000 → 10.000 → 100.000

#### Exemplo de algorítimo que escala em O(log n): Binary Search
- Conforme o input aumenta muito rápido, o tempo de execução não aumenta tão rápido quanto o input
    -$$\log_{2} 10$$ = 3.32
    -$$\log_{2} 20$$ = 4.32
    -$$\log_{2} 40$$ = 5.32
- Nesse caso, o input seria o logaritimando.
- Conforme a gente dobra ele, o resultado não dobra, mas sim aumenta apenas em 1 (linearmente)

- Como funciona o algorítimo:
    - Tem um array ordenado
    - A gente tá buscando um elemento x
    - A gente pega o elemento no meio do array
    - E vê se esse elemento é maior ou menor que o x
    - Descarta a outra metade do array
    - Vai dividindo até encontrar o elemento
- Se o array tiver 10 elementos, vai demorar 3 etapas para encontrar o x
- Se o array tiver 20 elementos, vai demorar 4 etapas para encontrar o x

### O(n)