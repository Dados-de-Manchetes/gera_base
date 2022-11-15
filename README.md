# Gerar base

Esse repositório tem como objetivo gerar uma base de dados de manchetes.

A base que vai ser construída utilizará os dados das páginas baixadas. Para realizar essa tarefa primeiro os dados serão extraídos via python3, depois será consultado a API GET /paginas para verificar se uma determinada página foi adicionada, caso não for vai ser adicionada.

Ao final do processo é esperado ter uma base de dados com todas as informações das manchetes.


```mermaid
graph TD;

    

    subgraph Gerar base
        subgraph Para um pagina
            GerarBase2[Verifica se a página existe]
            GerarBase3[Solicita adicionar elementos]
        end
        GerarBase1[Percorre todas as páginas]    
    end
    
    subgraph APIPaginas[API /paginas]
        APIGetPaginas[GET]
    end

    GerarBase1-->GerarBase2
    GerarBase2-->APIGetPaginas
    APIGetPaginas--Caso não existir-->GerarBase3 
```