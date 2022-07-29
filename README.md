# Orientação a Objetos em Python e suas Aplicações no Deep Learning
" Deep learning ou aprendizagem profunda baseia-se no machine learning para, a partir de uma grande quantidade de dados e após inúmeras camadas de processamento com algoritmos, conseguir que um computador aprenda por si mesmo e execute tarefas semelhantes às dos seres humanos, tais como a identificação de imagens, o reconhecimento de voz ou a realização de predições, de forma progressiva."  - [IBERDROLA](https://www.iberdrola.com/inovacao/deep-learning)

## OOP em Python
Antes de introduzir o uso de Orientação a Objetos no Deep Learning em Python, precisamos saber como exatamente a linguagem por si só trabalha com OOP.

**Obs.:** Ao chegar aqui, imaginamos que você já tenha noções básicas sobre Orientação a Objeto num geral, logo não nos extenderemos neste sentido e iremos direto aos pontos:

### Declaração de Classes:
Para declarar uma classe em Python é bem simples:  
```
class PessoaFisica():
    # Atributos e métodos da classe
```
No Python, todas as classes devem, por boas práticas, possuir nomes que **comecem com letra maiúscula** e, caso sejam compostos, a primeira letra de cada palavra deve ser maiúscula, o que chamamos de formato ``CamelCase``.

### Criando um Construtor:
Para declarar um construtor em Python basta definir o nome do atributo no método especial chamado ``__init__``, este método define o **construtor da classe**.  

Para definir os atributos de uma classe em seu construtor, basta passá-los como parâmetro, como podemos ver abaixo:
```
class PessoaFisica:
    def __init__(self, nome, sexo, cpf):
        self.nome = nome
        self.sexo = sexo
        self.cpf = cpf
```
Observe que o uso de ``self.atributo`` se parece com o uso de ``this.atributo`` em Java.

### Instanciando Objetos:
Parecido com Java, para instanciar um objeto em Python basta:
```
if __name__ == "__main__":
    pessoa1 = PessoaFisica("João", "M", "123456")
```

### Declarando Métodos:
Um dos principais aspectos de qualquer linguagem é a declaração de Métodos/Funções para fazer o que precisamos dentro do nosso programa. Em Python não é diferente. Para **declarar um método** dentro de uma classe em Python é simples: 

```
class PessoaFisica:
    def __init__(self, nome, sexo, cpf, ativo):
        self.nome = nome
        self.sexo = sexo
        self.cpf = cpf
        self.ativo = ativo
        
    def desativar(self):
        self.ativo = False
        print("A pessoa foi desativada com sucesso")

if __name__ == "__main__":
    pessoa1 = PessoaFisica("João", "M", "123456", True)
    pessoa1.desativar()
```

Para criar um método utilizamos a palavra reservada ``def`` seguido do nome da classe, nesse caso ``desativar``. Após isso é só definir o comportamente deste método. Neste caso estamos desativando a ``PessoaFisica`` em questão.

### Encapsulamento em Python
Um dos pilares da OOP é o encapsulamento, e é claro que há implementação de tal pilar em Python. Porém ela aparece de forma um pouco diferente quando comparada a linguagens de paradigma totalmente voltado para OOP.

#### Definir Atributo como Privado:
Utilizamos dois underlines ``__`` antes do nome do atributo ou método: 
```
class PessoaFisica:
    def __init__(self, nome, sexo, cpf, ativo):
        ...
        self.__ativo = ativo
        
    def desativar(self):
        self.__ativo = False
        print("A pessoa foi desativada com sucesso")

if __name__ == "__main__":
    pessoa1 = PessoaFisica("João", "M", "123456", True)
    pessoa1.desativar()
    print(pessoa1.ativo)
```

Podemos utilizar Getters e Setters para modificar estes atributos, porém, os criadores da linguagem desenvolveram uma forma alternativa de fazer isso: as **Properties**.
```
class PessoaFisica:
    def __init__(self, nome, sexo, cpf, ativo):
        self.__nome = nome
        self.__sexo = sexo
        self.__cpf = cpf
        self.__ativo = ativo

    @property
    def nome(self):
        return self.__nome
    
    @nome.setter
    def nome(self, nome):
        self.__nome = nome

if __name__ == "__main__":
    pessoa1 = PessoaFisica("João", "M", "123456", True)
    # Utilizando properties
    pessoa1.nome = "José"
    print(pessoa1.nome)
```

A utilização continua a mesma, o que torna tudo mais limpo!



## Deep Learning e OOP

### Exemplo de uso de OOP em modelos de Deep Learning

### Vantagens do uso de OOP
### Desvantagens do uso de OOP

## Créditos
https://www.youtube.com/watch?v=QQkUoE58QMA&ab_channel=ConnorShorten
https://github.com/kuangliu/pytorch-cifar
https://www.treinaweb.com.br/blog/orientacao-a-objetos-em-python#:~:text=No%20paradigma%20orientado%20%C3%A0%20objetos,constante%20no%20desenvolvimento%20de%20programas.&text=Como%20vimos%20acima%2C%20para%20declarar,seguido%20do%20nome%20desta%20classe.


