
## Sobre o Projeto
O PROBAT é um motor de testes unitários que executa scripts de específicos configurados na aplicação servidora Protheus.Ele é orientado por programas desenvolvidos em TLPP, e o próprio framework da linguagem executa testes unitários, coordenando a execução e marcando uma análise criteriosa sobre os nossos fontes.

Apontado para a pasta "tests", dentro do master, ele utiliza uma infraestrutura dentro do Appserver para rodar os scripts, e em tempo de execução, analisa a cobertura de código e emite um porcentagem, denominada Code Coverage. 

Além disso, ele retorna um resultado dos testes executados, em três opções: 
- SKIP
- OK
- FAILURE
  
Para retornar tais resultados, utilizei o conceito de Asserts, isto é, existe funções nativas do TlppCore, que monitoram os resultados de uma execução por meio dos seus parâmetros.

![image](https://github.com/KaueSMoraes/readme-probat/assets/126820310/4c05fe51-938c-4950-a55f-8b4467326a57)

Os resultados são gerados num arquivo XML, denominado no .ini do Appserver.
![image](https://github.com/KaueSMoraes/readme-probat/assets/126820310/8b4bd0d8-7ec0-4a9e-a5dc-5a7e16f81648)

No desenvolvimento das Suites, utilizei o conceito de Herança das Classes, haja vista que existem processos que realizam o mesmo tipo de execução, porém com parâmetros e variáveis diferentes.

![image](https://github.com/KaueSMoraes/readme-probat/assets/126820310/0bb210c8-2475-4591-b3a3-a2816e9d151a)

Utilizo execução de rotinas via JOB, por meio da função do MsExecAuto. Em casos de Erros na execução do JOB ele envia um email com log de resultados 

![image](https://github.com/KaueSMoraes/readme-probat/assets/126820310/deffb298-04f6-4a23-8edd-74bc0d8a9ff6)

LOG

![image](https://github.com/KaueSMoraes/readme-probat/assets/126820310/6b6af0fa-9662-426c-a433-8d7ddb45e610)

A execução do CI emite resultados via Pipelines

![probat1](https://github.com/KaueSMoraes/readme-probat/assets/126820310/16aab596-8ba9-4c4d-9d9d-71cf84d94ed8)

A execução das suítes de testes devem atender aos requisitos apontados no desenvolvimento. Para estabelecer um padrão, deve-se utilizar POO(Programação Orientada a Objetos) nativa do TLPP.
Todos os resultados também são gravados, em tempo de execução, no Banco de Dados.

Ademais, a execução via CI/CD, é coordenada pelo GitLab, que acessa a estrutura do Kubernets, e utiliza uma imagem específica com as configurações do PROBAT no Appserver.

O projeto desenvolvido é de licença da AGRO AMAZÔNIA PRODUTOS AGROPECUÁRIOS S.A, por isso, 
Dados Sensíveis foram ocultados.
