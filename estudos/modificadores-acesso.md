# C# - Modificadores de Acesso

- ``` public ```
    - Código acessível por todas as classes.
    
- ``` private ```
    - Código acessível somente na mesma classe.
    
- ``` protected ```
    - Código acessível pela mesma classe ou por classes que derivem da mesma.
    
- ``` internal ```
    - Código acessível somente dentro do mesmo assembly.
    
- ``` protected internal ```
    - Código acessível dentro do mesmo assembly ou em classes que derivam da mesma (inclusive fora do assembly).
    
- ``` private protected ```
    - Código acessível dentro do mesmo assembly ou em classes que derivam da mesma (somente no mesmo assembly).

> Por padrão, todos os **membros** de uma classe (métodos, campos e propriedades) são ``` private ```.      
> Por padrão todos os **tipos** (classes, estruturas, delegados, enumerações) são ``` internal ```.    


## Outros

- ``` virtual ```
    - Indica que o método pode ser sobrescrito na classe derivada.
