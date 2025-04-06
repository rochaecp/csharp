# C# - Modificadores de Acesso

- Por padrão, todos os **membros** de uma classe (métodos, campos e propriedades) são ```private```.
- Por padrão todos os **tipos** (classes, estruturas, delegados, enumerações) são ```internal```.

# Modificadores de Acesso para classes

- ```public```
    - Classe pública, sem restrições de visualização.   
- ```private```
    - Pouco usada. Classe fica disponível somente dentro de outra classe, onde foi definida.
- ```internal```
    - Classe acessível somente dentro do mesmo projeto (mesmo assembly).    

# Algumas palavras reservadas para classes

- ```abstract```
    - Classe será uma classe base para outras classes.
    - Classes abstract não podem ser instanciadas.
- ```sealed```
    - Classe não pode ser herdada. 
- ```static```
    - Classe não permite a instanciação de objetos e seus membros devem ser todos static

# Modificadores de Acesso para métodos

- ```public```
    - Método sem restrições de acesso.
- ```private```
    - Método só pode ser acessado dentro da própria classe que ele faz parte.
- ```protected```
    - Método acessível pela mesma classe ou por classes que derivem da mesma.    
- ```protected internal```
    - Código acessível dentro do mesmo assembly ou em classes que derivam da mesma (inclusive fora do assembly).    
- ```private protected```
    - Código acessível dentro do mesmo assembly ou em classes que derivam da mesma (somente no mesmo assembly).       

## Algumas palávras reservadas para métodos

- ```static```
    - Método pode ser chamado mesmo sem a instanciação de um objeto.
    - Geralmente métodos static são membros de classes static.
- ```virtual```
    - Indica que o método pode ser sobrescrito na classe derivada.
- ```override```
    - Indica que o método sobrescreve o da superclasse.  