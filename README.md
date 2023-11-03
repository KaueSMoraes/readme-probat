
## Sobre o Projeto
O PROBAT é um motor de testes unitários que executa scripts' específicos configurados na aplicação servidora Protheus. Ele é orientado por programas desenvolvidos em TLPP, e o próprio framework da linguagem executa testes unitários, coordenando a execução e marcando uma análise criteriosa sobre os nossos fontes.

Apontado para a pasta "tests", dentro do master, ele utiliza uma infraestrutura dentro do Appserver para rodar os scripts, e em tempo de execução, analisa a cobertura de código e emite uma porcentagem, denominada Code Coverage. 

Além disso, ele retorna um resultado dos testes executados, em três opções: 
- SKIP
- OK
- ERROR
  
Para retornar tais resultados, utilizei o conceito de Asserts, isto é, existe funções nativas do TlppCore, que monitoram os resultados de uma execução por meio dos seus parâmetros.

![image](https://github.com/KaueSMoraes/readme-probat/assets/126820310/229dc11c-3462-4be9-9851-bce54491e314)

Os resultados são gerados num arquivo XML, denominado no .ini do Appserver.

![image](https://github.com/KaueSMoraes/readme-probat/assets/126820310/9e46adfe-a4eb-4e4f-9d48-105ef45a8f58)

No desenvolvimento das Suites, utilizei o conceito de Herança das Classes, haja vista que existem processos que realizam o mesmo tipo de execução, porém com parâmetros e variáveis diferentes.

![image](https://github.com/KaueSMoraes/readme-probat/assets/126820310/7bc8e152-cbbd-4427-9df3-c55ee7f29784)


Utilizo execução de rotinas via JOB, por meio da função do MsExecAuto. Em casos de Erros na execução do JOB ele envia um email com log de resultados 

![image](https://github.com/KaueSMoraes/readme-probat/assets/126820310/c89fbf8c-0553-4035-a2e1-bd53ed2fca8e)


### LOG

![image](https://github.com/KaueSMoraes/readme-probat/assets/126820310/83e65c88-2ae9-4217-a21d-c2956e2d0959)


### A execução do CI emite resultados via Pipelines

O GitLab Enterprise, tem sua prórpia infraestrutura para exibição de Testes via Pipelines, integrando com a ferramenta de CI/CD configurada no projeto. Dessa forma, internamente, foi criada uma estrutura de imagens específicas em Docker, que são atualizadas automaticamente por um projeto versionado nos próprios repositórios da organização. Assim, quando um "Merge Resquest" no projeto principal é criado, as pipilenes são executadas se baseando nessa estrutura do Docker, escalonando e simulando a aplicação real. 

![image](https://github.com/KaueSMoraes/readme-probat/assets/126820310/0f5794d6-29f2-4045-97a7-c7778e37f693)

Nesse sentido, podemos, por pipeline executada, monitorar os testes que deram falha e quais passaram.

![image](https://github.com/KaueSMoraes/readme-probat/assets/126820310/6a2af8c5-3540-4b13-8688-700a389c506e)

Na aba de Overview do Merge Request também é possível monitorar a pipeline de testes executada em conjunto com o ajuste que está feito e commitado no mesmo MR.
![probat1](https://github.com/KaueSMoraes/readme-probat/assets/126820310/45c247c7-425c-47e8-9d46-9ef66940faac)

Por se tratar de uma aplicação servidora, hospedada em hosts Oracle Linux, utilizando "bash", todo o método de integração contínua realizado pelos Runners do GitLab são coordenados scripts de manipulação de pastas, arquivos, e principalmente um arquivo XML gerado com os resultados dos testes do Probat. Esse arquivo é carregado para diretório atual do Gitlab e carregado no merge request pela ferramente de Artefatos, que seguem o padrão de arquivos no formato jUNIT.

![image](https://github.com/KaueSMoraes/readme-probat/assets/126820310/65797229-2d48-4225-968b-905bb2e8fef8)

A execução das suítes de testes devem atender aos requisitos apontados no desenvolvimento. Para estabelecer um padrão, deve-se utilizar POO(Programação Orientada a Objetos) nativa do TLPP.
Todos os resultados também são gravados, em tempo de execução, no Banco de Dados.

### Conclusão
Toda aplicação, seja ela servidora, web ou mobile, requer uma sólida estrutura de Garantia da Qualidade de Software para garantir que atenda plenamente às necessidades dos usuários. No mundo da tecnologia, o ato de "testar" vai além de mera avaliação; ele assegura que o aplicativo ou site entregue os resultados desejados de acordo com os requisitos estabelecidos. Afinal, são os usuários que tiram proveito da tecnologia implementada, tornando a garantia de qualidade essencial para a sua satisfação.

A automação desempenha um papel fundamental nesse processo. Ela não substitui a mão de obra humana, mas aprimora a análise crítica, permitindo a entrega contínua de sistemas de alta qualidade. Em outras palavras, as automatizações são aliadas, não concorrentes, no esforço de aprimorar a excelência dos produtos tecnológicos.

O projeto desenvolvido é de licença da AGRO AMAZÔNIA PRODUTOS AGROPECUÁRIOS S.A, por isso, 
Dados Sensíveis foram ocultados.
