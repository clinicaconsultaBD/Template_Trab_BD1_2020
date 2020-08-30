# TRABALHO 01:  Título do Trabalho
Trabalho desenvolvido durante a disciplina de BD1

# Sumário

### 1. COMPONENTES<br>
Integrantes do grupo<br>
primeiro_componente_do_grupo:luciano.ananias.50@gmail.com<br>
segundo_componente_do_grupo:guguandrade_08@hotmail.com<br>
...<br>

### 2.INTRODUÇÃO E MOTIVAÇÃO<br>

> A empresa “GL Projetos” tem como principal objetivo acelerar processos em diversas áreas, assim poupando o recurso mais caro nos dias de hoje, o tempo.
O Sistema criado pela nossa empresa visa acelerar diversas atividades e burocracias tendo em vista a utilização de um software capaz de otimizar processos como marcações de consultas, resultados de exames e evitar aglomerações em um período onde devemos ficar a maior parte do tempo dentro de nossas residências.

 

### 3.MINI-MUNDO<br>

> Um laboratório necessita de um sistema que armazene os dados dos pacientes (nome, CPF, data de nascimento, endereço e telefone) e dos funcionários (nome, registro, endereço, horário de entrada e saída) para melhor controle dos dados e eficiência da empresa. 
Cada paciente poderá fazer mais de um tipo de exames e os resultados dos mesmos deverão ser armazenados de acordo. O paciente é atendido com um funcionário que realiza o processo de coleta de sangue.
O objetivo do projeto é entregar os resultados de maneira simples, rápida e intuitiva ao paciente.

### 4.PROTOTIPAÇÃO, PERGUNTAS A SEREM RESPONDIDAS E TABELA DE DADOS<br>
#### 4.1 RASCUNHOS BÁSICOS DA INTERFACE (MOCKUPS)<br>

![Alt text](https://github.com/clinicaconsultaBD/Template_Trab_BD1_2020/blob/master/images/Tela%201.png?raw=true "Title")
![Alt text](https://github.com/clinicaconsultaBD/Template_Trab_BD1_2020/blob/master/images/Tela%202.png?raw=true "Title")
![Alt text](https://github.com/clinicaconsultaBD/Template_Trab_BD1_2020/blob/master/images/Tela%203.png?raw=true "Title")
![Alt text](https://github.com/clinicaconsultaBD/Template_Trab_BD1_2020/blob/master/images/Tela%204.png?raw=true "Title")
![Alt text](https://github.com/clinicaconsultaBD/Template_Trab_BD1_2020/blob/master/images/Tela%205.png?raw=true "Title")

![Arquivo PDF do Protótipo Balsamiq](https://github.com/clinicaconsultaBD/Template_Trab_BD1_2020/blob/master/arquivos/Mockups.pdf?raw=true "Clínica")

#### 4.2 QUAIS PERGUNTAS PODEM SER RESPONDIDAS COM O SISTEMA PROPOSTO?
    a) O sistema proposto poderá fornecer quais tipos de relatórios e informaçes? 
    b) Crie uma lista com os 5 principais relatórios que poderão ser obtidos por meio do sistema proposto!
    
> A Empresa DevCom precisa inicialmente dos seguintes relatórios:
* Relatório que mostre o nome de cada supervisor(a) e a quantidade de empregados supervisionados.
* Relatório relativo aos os supervisores e supervisionados. O resultado deve conter o nome do supervisor e nome do supervisionado além da quantidade total de horas que cada supervisionado tem alocada aos projetos existentes na empresa.
* Relatorio que mostre para cada linha obtida o nome do departamento, o valor individual de cada salario existente no  departamento e a média geral de salarios dentre todos os empregados. Os resultados devem ser apresentados ordenados por departamento.
* Relatório que mostre as informações relacionadas a todos empregados de empresa (sem excluir ninguém). As linhas resultantes devem conter informações sobre: rg, nome, salario do empregado, data de início do salario atual, nomes dos projetos que participa, quantidade de horas e localização nos referidos projetos, numero e nome dos departamentos aos quais está alocado, informações do historico de salário como inicio, fim, e valores de salarios antigos que foram inclusos na referida tabela (caso possuam informações na mesma), além de todas informações relativas aos dependentes. 
>> ##### Observações: <br> a) perceba que este relatório pode conter linhas com alguns dados repetidos (mas não todos). <br>  b) para os empregados que não possuirem alguma destas informações o valor no registro deve aparecer sem informação/nulo. 
* Relatório que obtenha a frequencia absoluta e frequencia relativa da quantidade de cpfs únicos no relatório anterior. Apresente os resultados ordenados de forma decrescente pela frequencia relativa.

 
 
#### 4.3 TABELA DE DADOS DO SISTEMA:
    a) Esta tabela deve conter todos os atributos do sistema e um mínimo de 10 linhas/registros de dados.
    b) Esta tabela tem a intenção de simular um relatório com todos os dados que serão armazenados 
    
![Exemplo de Tabela de dados da Empresa Devcom](https://github.com/discipbd1/trab01/blob/master/arquivos/TabelaEmpresaDevCom_sample.xlsx?raw=true "Tabela - Empresa Devcom")
    
    
### 5.MODELO CONCEITUAL<br>
    
![Modelo Conceitual](https://github.com/clinicaconsultaBD/Template_Trab_BD1_2020/blob/master/images/Modelo%20Conceitual.png?raw=true "Modelo Conceitual")
    
#### 5.1 Validação do Modelo Conceitual
    [Grupo01]: [Nomes dos que participaram na avaliação]
    [Grupo02]: [Nomes dos que participaram na avaliação]

#### 5.2 Descrição dos dados 
    [objeto]: [descrição do objeto]
    
    EXEMPLO:
    CLIENTE: Tabela que armazena as informações relativas ao cliente<br>
    CPF: campo que armazena o número de Cadastro de Pessoa Física para cada cliente da empresa.<br>


### 6	MODELO LÓGICO<br>

![Modelo Logico](https://github.com/clinicaconsultaBD/Template_Trab_BD1_2020/blob/master/images/Logico.png?raw=true "Modelo Logico")

### 7	MODELO FÍSICO<br>

```
CREATE TABLE pessoa(
    id_pessoa int not null,
    id_telefone int not null,
    id_endereco int not null,
    nome_pessoa varchar(45),
    cpf int,
    PRIMARY KEY (id_pessoa)
);

CREATE TABLE contato(
    id_telefone int not null,
    id_pessoa int not null,
    tipo_contato varchar(20),
    contato varchar(50),
    PRIMARY KEY (id_telefone),
    FOREIGN KEY(id_pessoa) REFERENCES pessoa(id_pessoa)
);

CREATE TABLE endereco(
    id_endereco int not null,
    id_pessoa int not null,
    cep int,
    numero int,
    logradouro varchar(30),
    tipo_logradouro varchar(30),
    PRIMARY KEY (id_endereco ),
    FOREIGN KEY(id_pessoa) REFERENCES pessoa(id_pessoa)
);

CREATE TABLE paciente(
    id_paciente int not null,
    id_pessoa int not null,
    PRIMARY KEY (id_paciente),
    FOREIGN KEY(id_pessoa) REFERENCES pessoa(id_pessoa)
);

CREATE TABLE agenda(
    id_agendamento int not null,
    id_paciente int not null,
    id_exame int,
    data_exame date,
    PRIMARY KEY (id_agendamento),
    FOREIGN KEY(id_paciente) REFERENCES paciente(id_paciente)
);

CREATE TABLE funcionario(
    id_funcionario int not null,
    id_pessoa int not null,
    carga_horaria varchar(50),
    tipo_funcionario varchar(30),
    PRIMARY KEY (id_funcionario),
    FOREIGN KEY(id_pessoa) REFERENCES pessoa(id_pessoa)
);

CREATE TABLE exame(
    id_exame int not null,
    id_funcionario int not null,
    id_agendamento int not null,
    tipo_exame varchar(30),
    status varchar(30),
    PRIMARY KEY (id_exame),
    FOREIGN KEY(id_funcionario ) REFERENCES funcionario(id_funcionario ),
    FOREIGN KEY(id_agendamento ) REFERENCES agenda(id_agendamento )
);

CREATE TABLE resultado(
    id_resultado int not null,
    id_exame int not null,
    resultado varchar(30),
    hora_resultado date,
    PRIMARY KEY (id_resultado ),
    FOREIGN KEY(id_exame ) REFERENCES exame(id_exame )
);

ALTER TABLE pessoa ADD CONSTRAINT id_telefone FOREIGN KEY (id_telefone) REFERENCES contato(id_telefone );  
ALTER TABLE pessoa ADD CONSTRAINT id_endereco FOREIGN KEY (id_endereco ) REFERENCES endereco(id_endereco);
ALTER TABLE agenda ADD CONSTRAINT id_exame  FOREIGN KEY (id_exame) REFERENCES exame(id_exame );
```
     
### 8	INSERT APLICADO NAS TABELAS DO BANCO DE DADOS<br>
        a) inclusão das instruções de inserção dos dados nas tabelas criadas pelo script de modelo físico
        (Drop para exclusão de tabelas + create definição de para tabelas e estruturas de dados + insert para dados a serem inseridos)
        b) Criar um novo banco de dados para testar a restauracao 
        (em caso de falha na restauração o grupo não pontuará neste quesito)
        c) formato .SQL


### 9	TABELAS E PRINCIPAIS CONSULTAS<br>
    OBS: Incluir para cada tópico as instruções SQL + imagens (print da tela) mostrando os resultados.<br>
#### 9.1	CONSULTAS DAS TABELAS COM TODOS OS DADOS INSERIDOS (Todas) <br>

># Marco de Entrega 01: Do item 1 até o item 9.1<br>

#### 9.2	CONSULTAS DAS TABELAS COM FILTROS WHERE (Mínimo 4)<br>
#### 9.3	CONSULTAS QUE USAM OPERADORES LÓGICOS, ARITMÉTICOS E TABELAS OU CAMPOS RENOMEADOS (Mínimo 11)
    a) Criar 5 consultas que envolvam os operadores lógicos AND, OR e Not
    b) Criar no mínimo 3 consultas com operadores aritméticos 
    c) Criar no mínimo 3 consultas com operação de renomear nomes de campos ou tabelas

#### 9.4	CONSULTAS QUE USAM OPERADORES LIKE E DATAS (Mínimo 12) <br>
    a) Criar outras 5 consultas que envolvam like ou ilike
    b) Criar uma consulta para cada tipo de função data apresentada.

#### 9.5	INSTRUÇÕES APLICANDO ATUALIZAÇÃO E EXCLUSÃO DE DADOS (Mínimo 6)<br>
    a) Criar minimo 3 de exclusão
    b) Criar minimo 3 de atualização

#### 9.6	CONSULTAS COM INNER JOIN E ORDER BY (Mínimo 6)<br>
    a) Uma junção que envolva todas as tabelas possuindo no mínimo 2 registros no resultado
    b) Outras junções que o grupo considere como sendo as de principal importância para o trabalho

#### 9.7	CONSULTAS COM GROUP BY E FUNÇÕES DE AGRUPAMENTO (Mínimo 6)<br>
    a) Criar minimo 2 envolvendo algum tipo de junção

#### 9.8	CONSULTAS COM LEFT, RIGHT E FULL JOIN (Mínimo 4)<br>
    a) Criar minimo 1 de cada tipo

#### 9.9	CONSULTAS COM SELF JOIN E VIEW (Mínimo 6)<br>
        a) Uma junção que envolva Self Join (caso não ocorra na base justificar e substituir por uma view)
        b) Outras junções com views que o grupo considere como sendo de relevante importância para o trabalho

#### 9.10	SUBCONSULTAS (Mínimo 4)<br>
     a) Criar minimo 1 envolvendo GROUP BY
     b) Criar minimo 1 envolvendo algum tipo de junção

># Marco de Entrega 02: Do item 9.2 até o ítem 9.10<br>

### 10 RELATÓRIOS E GRÁFICOS

#### a) análises e resultados provenientes do banco de dados desenvolvido (usar modelo disponível)
#### b) link com exemplo de relatórios será disponiblizado pelo professor no AVA
#### OBS: Esta é uma atividade de grande relevância no contexto do trabalho. Mantenha o foco nos 5 principais relatórios/resultados visando obter o melhor resultado possível.

    

### 11	AJUSTES DA DOCUMENTAÇÃO, CRIAÇÃO DOS SLIDES E VÍDEO PARA APRESENTAÇAO FINAL <br>

#### a) Modelo (pecha kucha)<br>
#### b) Tempo de apresentação 6:40 

># Marco de Entrega 03: Itens 10 e 11<br>
<br>
<br>
<br> 



### 12 FORMATACAO NO GIT:<br> 
https://help.github.com/articles/basic-writing-and-formatting-syntax/
<comentario no git>
    
##### About Formatting
    https://help.github.com/articles/about-writing-and-formatting-on-github/
    
##### Basic Formatting in Git
    
    https://help.github.com/articles/basic-writing-and-formatting-syntax/#referencing-issues-and-pull-requests
    
    
##### Working with advanced formatting
    https://help.github.com/articles/working-with-advanced-formatting/
#### Mastering Markdown
    https://guides.github.com/features/mastering-markdown/

    
### OBSERVAÇÕES IMPORTANTES

#### Todos os arquivos que fazem parte do projeto (Imagens, pdfs, arquivos fonte, etc..), devem estar presentes no GIT. Os arquivos do projeto vigente não devem ser armazenados em quaisquer outras plataformas.
1. <strong>Caso existam arquivos com conteúdos sigilosos<strong>, comunicar o professor que definirá em conjunto com o grupo a melhor forma de armazenamento do arquivo.

#### Todos os grupos deverão fazer Fork deste repositório e dar permissões administrativas ao usuário do git "profmoisesomena", para acompanhamento do trabalho.

#### Os usuários criados no GIT devem possuir o nome de identificação do aluno (não serão aceitos nomes como Eu123, meuprojeto, pro456, etc). Em caso de dúvida comunicar o professor.


Link para BrModelo:<br>
http://www.sis4.com/brModelo/download.html
<br>


Link para curso de GIT<br>
![https://www.youtube.com/curso_git](https://www.youtube.com/playlist?list=PLo7sFyCeiGUdIyEmHdfbuD2eR4XPDqnN2?raw=true "Title")


