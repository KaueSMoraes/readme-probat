
## Sobre o Projeto
O PROBAT é um motor de testes unitários que executa scripts de específicos configurados na aplicação servidora Protheus.Ele é orientado por programas desenvolvidos em TLPP, e o próprio framework da linguagem executa testes unitários, coordenando a execução e marcando uma análise criteriosa sobre os nossos fontes.

Apontado para a pasta "tests", dentro do master, ele utiliza uma infraestrutura dentro do Appserver para rodar os scripts, e em tempo de execução, analisa a cobertura de código e emite um porcentagem, denominada Code Coverage. 

Além disso, ele retorna um resultado dos testes executados, em três opções: 
- SKIP
- OK
- FAILURE
  
Para retornar tais resultados, utilizei o conceito de Asserts, isto é, existe funções nativas do TlppCore, que monitoram os resultados de uma execução por meio dos seus parâmetros.

![image](https://github.com/KaueSMoraes/readme-probat/assets/126820310/229dc11c-3462-4be9-9851-bce54491e314)

Os resultados são gerados num arquivo XML, denominado no .ini do Appserver.

![image](https://github.com/KaueSMoraes/readme-probat/assets/126820310/9e46adfe-a4eb-4e4f-9d48-105ef45a8f58)

No desenvolvimento das Suites, utilizei o conceito de Herança das Classes, haja vista que existem processos que realizam o mesmo tipo de execução, porém com parâmetros e variáveis diferentes.

![image](https://github.com/KaueSMoraes/readme-probat/assets/126820310/7bc8e152-cbbd-4427-9df3-c55ee7f29784)


Utilizo execução de rotinas via JOB, por meio da função do MsExecAuto. Em casos de Erros na execução do JOB ele envia um email com log de resultados 

![image](https://github.com/KaueSMoraes/readme-probat/assets/126820310/c89fbf8c-0553-4035-a2e1-bd53ed2fca8e)


LOG

![image](https://github.com/KaueSMoraes/readme-probat/assets/126820310/83e65c88-2ae9-4217-a21d-c2956e2d0959)


A execução do CI emite resultados via Pipelines

![probat1](https://github.com/KaueSMoraes/readme-probat/assets/126820310/45c247c7-425c-47e8-9d46-9ef66940faac)

A execução das suítes de testes devem atender aos requisitos apontados no desenvolvimento. Para estabelecer um padrão, deve-se utilizar POO(Programação Orientada a Objetos) nativa do TLPP.
Todos os resultados também são gravados, em tempo de execução, no Banco de Dados.

Ademais, a execução via CI/CD, é coordenada pelo GitLab, que acessa a estrutura do Kubernets, e utiliza uma imagem específica com as configurações do PROBAT no Appserver.

O projeto desenvolvido é de licença da AGRO AMAZÔNIA PRODUTOS AGROPECUÁRIOS S.A, por isso, 
Dados Sensíveis foram ocultados.
