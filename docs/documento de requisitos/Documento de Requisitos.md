# Documento de Requisitos
# 1. Introdução

## 1.1 Propósito do documento de requisitos

O propósito deste Documento de Requisito (DR) é especificar e descrever de maneira completa, formal e não ambígua todos os requisitos funcionais e não-funcionais do Sistema de Gerenciamento para Escola de Línguas (SGEL). Serve como referência para a entender o escopo do sistema, facilitando sua implementação e o trabalho harmonioso entre a equipe.

Este documento é destinado à equipe de desenvolvimento de software, aos gerentes do projeto, analistas e projetistas, engenheiros de teste e garantia de qualidade (SQA), e demais partes interessadas no desenvolvimento do sistema.

## 1.2 Escopo do produto

O produto consiste em um sistema desktop desenvolvido para facilitar o gerenciamento acadêmico e comercial de uma escola de línguas. O sistema será utilizado internamente por funcionários e professores da instituição, não havendo interação direta através do sistema com os alunos.

Para o uso do sistema, os usuários deverão realizar uma autenticação baseada em login e senha, tendo acesso às funcionalidades relativas ao seu nível de permissão. O gerenciamento de contas de acesso e permissões administrativas será reservado aos administradores.

O sistema permitirá o cadastro e controle de cursos, idiomas, níveis de proficiência, turmas, salas e professores, oferecendo suporte à alocação de horários e prevenção de conflitos de agenda. Também será oferecido suporte ao controle de matrículas, lista de espera para turmas com vagas esgotadas e registro de notas de testes de nivelamento realizados previamente.

Na parte acadêmica, o sistema permitirá aos professores o registro de frequência e notas das turmas atribuídas, bem como o acompanhamento da aprovação dos alunos. Na parte comercial e financeira, o sistema permitirá a definição de planos de cursos, controle de mensalidades, aplicação de políticas de descontos e apuração do repasse financeiro aos professores.

A finalidade do sistema é centralizar as informações e rotinas operacionais necessárias para o funcionamento diário da escola, organizando os processos acadêmicos e financeiros em uma única ferramenta, não incluindo acesso ou autoatendimento aos alunos, aplicação de provas ou testes de nivelamento online, transmissão de aulas ou integração com instituições bancárias para processamento automático de pagamentos.

## 1.3 Definições, acrônimos e abreviações

| **Termo** | **Descrição**               |
| --------- | --------------------------- |
| CPF       | Cadastro de Pessoas Físicas |
| DR        | Documento de Requisitos     |
| RF        | Requisito Funcional         |
| RNF       | Requisito Não Funcional     |

## 1.4 Referências

"IEEE Recommended Practice for Software Requirements Specifications," in IEEE Std 830-1998 , vol., no., pp.1-40, 20 Oct. 1998, doi: 10.1109/IEEESTD.1998.88286. URL: [https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=720574&isnumber=15571](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=720574&isnumber=15571)

## 1.5 Visão geral

A Seção 2 apresenta uma descrição geral do produto, contextualizando-o dentro do ambiente em que será utilizado, suas principais funcionalidades, os perfis de usuário esperados e as restrições e suposições consideradas. A seção 3 detalha os requisitos funcionais e não funcionais específicos do sistema, organizados por módulo e por ator. As seções finais trazem apêndices e o índice do documento.

# 2. Descrição Geral

## 2.1 Perspectiva do produto

O sistema é uma aplicação desktop independente, não fazendo parte de nenhum sistema ou plataforma maior já existente. Não há integração com sistemas de terceiros, serviços web externos ou hardware especializado; o sistema requer apenas um computador convencional com teclado, mouse e monitor para sua operação. A comunicação com o banco de dados ocorrerá localmente ou em rede interna da instituição, sem dependência de conexão com a internet.

A interação com o sistema se dará por meio de uma interface gráfica de janelas, navegada majoritariamente via mouse e teclado. Cada usuário terá sua própria sessão autenticada, e o sistema apresentará apenas as telas e funcionalidades correspondentes ao seu perfil de acesso.

## 2.2 Funcionalidades do produto

O sistema deverá oferecer as seguintes funcionalidades principais:
- Realizar a autenticação e o controle de acesso de usuários;
- Permitir o cadastro, alteração e consulta de funcionários, professores e alunos;
- Permitir o gerenciamento de idiomas, níveis de proficiência, cursos oferecidos e salas;
- Permitir a criação e organização de turmas, com definição de horários e alocação de salas;
- Validar a disponibilidade de salas e professores, impedindo choques de horários;
- Registrar matrículas e transferências de alunos;
- Manter listas de espera para turmas com vagas esgotadas;
- Disponibilizar um diário de classe para registro de frequência e notas;
- Calcular automaticamente a situação final dos alunos (aprovação ou reprovação) com base em critérios acadêmicos;
- Gerenciar planos de pagamento, mensalidades e taxas de matrícula;
- Registrar pagamentos e permitir o acompanhamento da inadimplência;
- Aplicar políticas de descontos em mensalidades;
- Calcular o pagamento aos professores com base nas aulas ministradas ou remuneração fixa.

## 2.3 Características do usuário

O sistema possuirá três tipos principais de usuários: administradores, financeiro e professores.

- **Administradores**: profissionais com nível de escolaridade superior e ampla experiência na gestão pedagógica e financeira de instituições de ensino. Possuem habilidades técnicas intermediárias em informática e rotinas de escritório, necessitando de acesso irrestrito e relatórios consolidados para tomada de decisão.
- **Financeiro**: profissionais com nível de escolaridade médio ou superior, com experiência em atendimento ao público e rotinas administrativas básicas. Possuem conhecimentos básicos de informática. Por executarem tarefas repetitivas e com risco de erros em dados sensíveis (como valores e matrículas), demandam interfaces intuitivas, validações automáticas de entrada e mensagens de confirmação para ações críticas.
- **Professores**: profissionais com formação de nível superior e experiência no ensino de idiomas, mas com habilidades técnicas focadas apenas no uso básico de computadores e internet. Por utilizarem o sistema de forma pontual e rápida entre as aulas, necessitam de telas diretas e simplificadas para chamada e lançamento de notas.

## 2.4 Restrições gerais

O desenvolvimento e a utilização do sistema estão sujeitos às seguintes restrições:
- O sistema deverá estar em conformidade com a Lei Geral de Proteção de Dados (LGPD - Lei nº 13.709/2018), garantindo o sigilo, a privacidade e o controle de acesso às informações pessoais e financeiras de alunos, responsáveis, professores e colaboradores.
- O sistema deverá respeitar a exigência legal brasileira referente a menores de 18 anos (Código Civil e ECA), tornando obrigatório o vínculo e o registro dos dados do responsável legal em cadastros, matrículas e movimentações financeiras de estudantes menores.
- O sistema deverá ser desenvolvido obrigatoriamente na linguagem de programação Java.
- O sistema deverá possuir interface gráfica para desktop.
- O acesso a qualquer funcionalidade do sistema exigirá autenticação prévia de cada usuário por meio de login e senha individuais e únicos.
- Os campos de identificação obrigatórios deverão seguir regras estritas de validação de formato (como CPF, telefone e e-mail).

## 2.5 Suposições e dependências

Suposições:
- Os dados cadastrais, financeiros e acadêmicos informados pelos usuários serão considerados verídicos e autênticos.
- Os testes de nivelamento aplicados fora do sistema serão considerados válidos para a classificação e matrícula do aluno no nível correspondente.
- Os funcionários e professores serão responsáveis pelo registro regular e consistente das informações no sistema, visto que os cálculos de aprovação, médias e relatórios financeiros dependem da atualização desses registros.

Dependências:
- O funcionamento do sistema depende da instalação prévia de um ambiente Java (JRE) em versão compatível no computador do usuário.
- A realização de matrículas e alocação de turmas depende do prévio cadastro de idiomas, níveis, salas e professores no sistema.
- A apuração correta do repasse financeiro a professores horistas depende do registro prévio das aulas ministradas no período de apuração.

# 3. Requisitos Específicos

## 3.1 Requisitos Funcionais

### 3.1.1 Módulo de Usuários e Acesso

- **RF-01 — Autenticação de usuário:** O sistema deve permitir que o usuário realize a autenticação por meio de nome de usuário e senha.
 - **RF-01.1 — Credenciais de acesso obrigatórias:** O sistema deve solicitar o preenchimento do nome de usuário e da senha, sendo ambos os campos de preenchimento obrigatório.
  - **RF-01.2 — Bloqueio sem sessão:** O sistema deve bloquear o acesso a todas as funcionalidades enquanto não houver sessão autenticada.
  - **RF-01.3 — Falha na autenticação:** O sistema deve exibir a mensagem "Usuário ou senha incorretos" quando o nome de usuário não estiver cadastrado, estiver inativo ou quando a senha não corresponder à cadastrada, sem indicar qual das credenciais foi validada incorretamente.

- **RF-02 — Sessão de uso:** O sistema deve encerrar a sessão do usuário, mediante confirmação e retorno à tela de acesso, a qualquer momento em que o usuário solicite ou ao fechar a aplicação, exigindo nova autenticação para qualquer acesso posterior.

- **RF-03 — Cadastro de dados de acesso:** O sistema deve permitir que o Administrador registre, junto ao cadastro de funcionário, o nome de usuário, a senha e o perfil de acesso, sendo todos os campos de preenchimento obrigatório.
  - **RF-03.1 — Perfis de acesso:** O sistema deve disponibilizar exclusivamente os perfis de acesso **Administrador**, **Financeiro** e **Professor**, conforme a Seção 2.3.
  - **RF-03.2 — Formato do nome de usuário:** O sistema deve validar que o nome de usuário possui de 4 (quatro) a 20 (vinte) caracteres e é formado apenas por letras, números, ponto (.) ou sublinhado (\_).
  - **RF-03.3 — Formato da senha:** O sistema deve validar que a senha possui de 8 (oito) a 20 (vinte) caracteres e não contém espaços.
  - **RF-03.4 — Unicidade do nome de usuário:** O sistema deve exibir a mensagem "Nome de usuário já cadastrado" e interromper o cadastro quando o nome de usuário informado já pertencer a uma conta cadastrada.

- **RF-04 — Permissões por perfil:** O sistema deve restringir o acesso às funcionalidades conforme o perfil do usuário autenticado, disponibilizando ao Administrador o acesso integral, ao Financeiro o acesso aos módulos de Usuários e Acesso, de Cadastros em modo de consulta e de Financeiro, e ao Professor o acesso aos módulos de Usuários e Acesso, de Turmas e de Diário de Classe e Progresso, estes dois últimos restritos às turmas que lhe são atribuídas.

- **RF-05 — Alteração de senha:** O sistema deve permitir que o usuário autenticado altere a própria senha, informando a senha atual e a nova senha, e exibir a mensagem "Senha atual incorreta" quando o valor informado não corresponder à senha cadastrada.

- **RF-06 — Administração de contas:** O sistema deve permitir que o Administrador liste as contas cadastradas e inative uma conta de acesso, mediante confirmação, sendo que a conta do Administrador autenticado não pode ser inativada.
  - **RF-06.1 — Conta administrativa inicial:** O sistema deve ser inicializado com uma conta de acesso de perfil Administrador, com nome de usuário e senha "admin", garantindo o primeiro acesso ao sistema, e deve exigir a definição de uma nova senha no primeiro acesso realizado com essa conta.

### 3.1.2 Módulo de Cadastros

- **RF-07 — Cadastro de funcionário:** O sistema deve permitir que o Administrador cadastre um funcionário: administrador, financeiro ou professor.
  - **RF-07.1 — Dados de cadastro:** O sistema deve solicitar nome, CPF, data de nascimento, e-mail, telefone, endereço e cargo, sendo todos os campos de preenchimento obrigatório. O cargo deve corresponder a um dos perfis de acesso do requisito RF-03.2.
  - **RF-07.2 — Dados adicionais do professor:** O sistema deve solicitar, quando o cargo informado for Professor, os idiomas que o funcionário pode lecionar e a modalidade de remuneração, podendo ser hora/aula ou valor fixo mensal.

- **RF-08 — Cadastro de aluno:** O sistema deve permitir que o Administrador cadastre um aluno.
  - **RF-08.1 — Dados de cadastro:** O sistema deve solicitar nome, CPF, data de nascimento, e-mail, telefone e endereço, sendo todos os campos de preenchimento obrigatório.
  - **RF-08.2 — Responsável legal:** O sistema deve solicitar o cadastro de um responsável legal sempre que o aluno cadastrado tiver menos de 18 anos.

- **RF-09 — Cadastro de idiomas:** O sistema deve permitir que o Administrador cadastre os idiomas oferecidos pela escola, sendo válidos os níveis de proficiência A1, A2, B1, B2, C1 e C2 para todos os idiomas.

- **RF-10 — Cadastro de cursos:** O sistema deve permitir que o Administrador cadastre os cursos oferecidos, indicando o idioma, o nível e a carga horária.

- **RF-11 — Cadastro de salas:** O sistema deve permitir que o Administrador cadastre as salas disponíveis, indicando sua identificação e sua capacidade máxima de alunos.

- **RF-12 — Validação de formato:** O sistema deve validar, antes de concluir o cadastro de funcionário ou aluno, o CPF informado, o e-mail informado e o telefone informado, exibindo mensagem indicando o campo e a regra não atendida em caso de falha.

- **RF-36 — Alteração de funcionário:** O sistema deve permitir que o Administrador altere os dados de um funcionário cadastrado, exceto o CPF, revalidando os campos conforme o requisito RF-12.

- **RF-37 — Alteração de aluno:** O sistema deve permitir que o Administrador altere os dados de um aluno cadastrado, exceto o CPF, revalidando os campos conforme o requisito RF-12.

- **RF-38 — Alteração de idioma:** O sistema deve permitir que o Administrador altere os dados de um idioma cadastrado.

- **RF-39 — Alteração de curso:** O sistema deve permitir que o Administrador altere os dados de um curso cadastrado.

- **RF-40 — Alteração de sala:** O sistema deve permitir que o Administrador altere os dados de uma sala cadastrada.

- **RF-41 — Consulta de funcionário:** O sistema deve permitir que o Administrador localize um funcionário cadastrado, pelo nome ou pelo nome de usuário, e visualize seus dados cadastrais.

- **RF-42 — Consulta de aluno:** O sistema deve permitir que o Administrador localize um aluno cadastrado, pelo nome ou pelo CPF, e visualize seus dados cadastrais.

- **RF-43 — Consulta de idioma:** O sistema deve permitir que o Administrador localize um idioma cadastrado, pelo nome do idioma, e visualize seus níveis.

- **RF-44 — Consulta de curso:** O sistema deve permitir que o Administrador localize um curso cadastrado, pelo nome do curso ou pelo idioma, e visualize seus dados cadastrais.

- **RF-45 — Consulta de sala:** O sistema deve permitir que o Administrador localize uma sala cadastrada, pela sua identificação, e visualize seus dados cadastrais.

### 3.1.3 Módulo de Turmas e Matrícula

- **RF-13 — Cadastro de turma:** O sistema deve permitir que o Administrador cadastre uma turma em determinado período, indicando o idioma, o nível, a modalidade de ensino, o professor e a sala.
  - **RF-13.1 — Modalidade de ensino:** O sistema deve permitir que a modalidade informada seja Presencial, Online ou Híbrido.
  - **RF-13.2 — Capacidade da turma:** O sistema deve solicitar, no cadastro da turma, o número de vagas, o qual não pode ser superior à capacidade da sala informada.

- **RF-14 — Horários da turma:** O sistema deve permitir que o Administrador registre os dias e os horários em que a turma terá aula.

- **RF-15 — Conflito de sala:** O sistema deve impedir a confirmação de uma turma cujo horário coincida com o de outra turma que utilize a mesma sala.

- **RF-16 — Conflito de professor:** O sistema deve impedir a confirmação de uma turma cujo horário coincida com o de outra turma que utilize o mesmo professor.

- **RF-17 — Cadastro de teste de nivelamento:** O sistema deve permitir que o Administrador registre o resultado do teste de nivelamento de um aluno, incluindo o idioma, o nível e a nota obtida.

- **RF-18 — Matrícula do aluno:** O sistema deve permitir que o Administrador matricule um aluno em uma turma.
  - **RF-18.1 — Existência de vaga:** O sistema deve verificar, antes de concluir a matrícula, se a turma possui vaga disponível.
  - **RF-18.2 — Nível do aluno:** O sistema deve verificar, antes de concluir a matrícula, se o nível do aluno no idioma da turma é igual ou superior ao nível da turma, exibindo mensagem e interrompendo a operação em caso negativo.

- **RF-19 — Transferência de turma:** O sistema deve permitir que o Administrador transfira um aluno matriculado de uma turma para outra, reutilizando as mesmas validações do requisito RF-18.

- **RF-20 — Cancelamento de matrícula:** O sistema deve permitir que o Administrador cancele a matrícula de um aluno, liberando a vaga da turma.

- **RF-21 — Lista de espera:** O sistema deve permitir que o Administrador insira o aluno em lista de espera de uma turma que não possui vaga disponível, respeitando a ordem de inserção.

### 3.1.4 Módulo de Diário de Classe e Progresso

- **RF-22 — Registro de frequência:** O sistema deve permitir que o Professor registre a presença ou a ausência de cada aluno matriculado em sua turma.

- **RF-23 — Registro de notas:** O sistema deve permitir que o Professor registre as notas das avaliações das turmas que lhe são atribuídas.
  - **RF-23.1 — Cadastro de avaliação:** O sistema deve permitir que o Professor registre, para a turma que lhe é atribuída, a descrição, o peso e a data de cada avaliação.

- **RF-24 — Acesso restrito às próprias turmas:** O sistema deve permitir que o Professor registre a frequência, as avaliações e as notas somente nas turmas que lhe são atribuídas.

- **RF-25 — Critérios de aprovação:** O sistema deve considerar, para cálculo da situação final do aluno, a nota mínima de aprovação igual a 5,0 (cinco) e a frequência mínima de 70% (setenta por cento), sendo as notas registradas na faixa de 0 (zero) a 10 (dez).

- **RF-26 — Situação final do aluno:** O sistema deve calcular a situação final do aluno ao final da turma como Aprovado ou Reprovado, conforme a nota média e a frequência mínima definidas no requisito RF-25.
  - **RF-26.1 — Cálculo da nota média:** O sistema deve calcular a nota média do aluno como a média ponderada das notas das avaliações, sendo considerado aprovado o aluno cuja nota média for igual ou superior à nota mínima definida.
  - **RF-26.2 — Cálculo da frequência:** O sistema deve calcular a frequência do aluno como o percentual de presenças sobre o total de aulas registradas, sendo considerado aprovado o aluno cuja frequência for igual ou superior à frequência mínima definida.

- **RF-27 — Histórico do aluno:** O sistema deve permitir que o Administrador consulte o histórico do aluno, contendo as turmas em que foi matriculado, as notas, as faltas e a situação final de cada turma.

### 3.1.5 Módulo de Financeiro

- **RF-28 — Plano de pagamento:** O sistema deve permitir que o Financeiro cadastre o plano de pagamento de um curso, indicando o número de parcelas, o valor de cada parcela e a taxa de matrícula.

- **RF-29 — Geração das parcelas:** O sistema deve gerar, no ato da matrícula do aluno, as parcelas do plano de pagamento do curso, conforme o requisito RF-28.
  - **RF-29.1 — Valor total:** O sistema deve calcular o valor total devido pelo aluno como o produto do número de parcelas pelo valor de cada parcela, acrescido da taxa de matrícula.
  - **RF-29.2 — Data de vencimento:** O sistema deve atribuir às parcelas vencimentos mensais consecutivos a partir da data da matrícula.

- **RF-30 — Registro de pagamento:** O sistema deve permitir que o Financeiro registre o pagamento de uma parcela, informando a data de pagamento e o valor pago.
  - **RF-30.1 — Situação da parcela:** O sistema deve manter a parcela como Aberta até o registro do pagamento e como Paga após o registro.
  - **RF-30.2 — Parcela vencida:** O sistema deve alterar a situação da parcela para Vencida quando a data atual for posterior à data de vencimento e o pagamento não tiver sido registrado.
  - **RF-30.3 — Confirmação do pagamento:** O sistema deve solicitar confirmação do Financeiro antes de concluir o registro do pagamento.

- **RF-31 — Descontos:** O sistema deve permitir que o Financeiro aplique à parcela um desconto de pontualidade, de parentesco ou de convênio, informando o tipo e o percentual aplicáveis.

- **RF-32 — Inadimplência:** O sistema deve permitir que o Financeiro consulte os alunos que possuem parcelas em situação Vencida, conforme o requisito RF-30.2.

- **RF-33 — Repasse ao professor:** O sistema deve calcular o valor a repassar ao professor no período apurado, conforme a modalidade de remuneração informada no cadastro do professor.
  - **RF-33.1 — Repasse por hora/aula:** O sistema deve calcular o valor a repassar como o produto da quantidade de aulas ministradas pelo professor no período pelo valor da hora/aula informado em seu cadastro.
  - **RF-33.2 — Repasse por valor fixo:** O sistema deve calcular o valor a repassar como o valor fixo mensal informado em seu cadastro.

- **RF-34 — Extrato do professor:** O sistema deve permitir que o Professor consulte o próprio extrato, contendo as aulas ministradas, os valores e os repasses do período.

- **RF-35 — Relatórios:** O sistema deve permitir que o Financeiro gere o relatório de receitas, o relatório de despesas com professores e o relatório de evasão de alunos, por período.

## 3.2 Requisitos Não Funcionais

### 3.2.1 Segurança e LGPD

- **RNF-01 — Proteção das senhas:** O sistema não deve armazenar as senhas de acesso em texto que possa ser lido, nem permitir que sejam exibidas ou consultadas, inclusive pelo Administrador.

- **RNF-02 — Confidencialidade dos dados sensíveis:** O sistema deve restringir o acesso aos dados pessoais, acadêmicos e financeiros dos alunos, responsáveis legais, professores e funcionários aos perfis de acesso autorizados, conforme o requisito RF-04.

- **RNF-03 — Conformidade com a LGPD:** O sistema deve coletar e utilizar os dados pessoais exclusivamente para as finalidades descritas na Seção 1.2, sem realizar qualquer tratamento para fins distintos daqueles.

- **RNF-04 — Dados de menores de idade:** O sistema deve exigir o registro do responsável legal de aluno menor de 18 anos, conforme o requisito RF-08.2, e não deve permitir o acesso aos dados de tal aluno por responsável legal que não esteja cadastrado como seu.

### 3.2.2 Usabilidade

- **RNF-05 — Clareza da interface:** O sistema deve apresentar as funcionalidades em linguagem compreensível aos usuários, sem uso de termos técnicos na interface.

- **RNF-06 — Identificação de campos obrigatórios:** O sistema deve identificar visualmente os campos de preenchimento obrigatório dos formulários e impedir o envio enquanto houver campo obrigatório não preenchido.

- **RNF-07 — Mensagens de erro:** O sistema deve apresentar as mensagens de erro de forma destacada, informando a causa do erro e a ação necessária para corrigi-lo.

- **RNF-08 — Confirmação de operações:** O sistema deve solicitar confirmação do usuário antes de concluir operações que alterem ou excluam dados.

- **RNF-09 — Uso sem treinamento formal:** O sistema deve permitir que um usuário sem experiência prévia realize o lançamento de frequência e de notas em suas turmas após treinamento de até 1 (uma) hora, sem apoio externo.

### 3.2.3 Desempenho

- **RNF-10 — Tempo de resposta das consultas:** O sistema deve apresentar o resultado das consultas e das verificações de conflito de sala e de professor em até 2 (dois) segundos após a solicitação, para uma base de até 500 (quinhentos) alunos, 100 (cem) turmas e 5.000 (cinco mil) parcelas.

- **RNF-11 — Tempo de geração dos relatórios:** O sistema deve gerar os relatórios de receitas, de despesas com professores e de evasão de alunos em até 5 (cinco) segundos, para a base de dados definida no requisito RNF-10.

### 3.2.4 Confiabilidade e integridade

- **RNF-12 — Atomicidade das operações:** O sistema deve concluir uma operação de cadastro, alteração ou exclusão somente após que todos os dados necessários tenham sido armazenados, não deixando registros incompletos.

- **RNF-13 — Prevenção de conflitos de agenda:** O sistema deve garantir que uma sala e um professor não sejam alocados a duas turmas com horário coincidente, conforme os requisitos RF-15 e RF-16.

- **RNF-14 — Precisão dos valores financeiros:** O sistema deve realizar os cálculos de parcelas, descontos e repasses com precisão de duas casas decimais, arredondando o valor obtido: se a terceira casa decimal for menor que 5, o valor é truncado; se for igual ou superior a 5, o valor é acrescido de um centésimo.

- **RNF-15 — Integridade referencial:** O sistema deve impedir a exclusão de um registro que possua outros registros vinculados a ele, informando o usuário quais são esses vínculos.

### 3.2.5 Manutenibilidade

- **RNF-16 — Modularidade:** O sistema deve ser organizado em módulos independentes, correspondentes às seções da Seção 3.1, permitindo a alteração de um módulo sem afetar o funcionamento dos demais.

### 3.2.6 Portabilidade e ambiente de execução

- **RNF-17 — Plataforma de execução:** O sistema deve ser desenvolvido na linguagem Java e possuir interface gráfica para desktop.

- **RNF-18 — Autonomia de execução:** O sistema deve executar todas as suas funcionalidades sem depender de conexão com a internet ou com sistemas externos.

- **RNF-19 — Resolução mínima:** O sistema deve ser utilizável em monitores com resolução mínima de 1280x720, sem corte de conteúdo ou de funcionalidades da interface.

- **RNF-20 — Persistência dos dados:** O sistema deve manter os dados cadastrados disponíveis após o encerramento da aplicação.

### 3.2.7 Tratamento de erros

- **RNF-21 — Robustez a entradas inválidas:** O sistema não deve encerrar de forma inesperada ao receber entrada inválida, devendo apresentar mensagem informando a natureza do erro.

- **RNF-22 — Mensagens de erro de operação:** O sistema deve informar o usuário, em caso de falha na execução de uma operação, a causa do erro e a ação que pode ser tomada.

- **RNF-23 — Preservação dos dados em falha:** O sistema deve manter inalterados os dados anteriores quando uma operação não for concluída, conforme o requisito RNF-12.

## 3.3 Requisitos de Interface

### 3.3.1 Autenticação

| **ID** | **Campo**            | **Descrição**                                          | **Origem** | **Obrigatório** | **Formato e faixa válida**                                                           | **Mensagem de erro**       |
| ------ | -------------------- | ------------------------------------------------------ | ---------- | --------------- | ------------------------------------------------------------------------------------ | -------------------------- |
| RI-01  | Nome de usuário      | Identifica o usuário no sistema                        | Digitado   | Sim             | 4 a 20 caracteres, sem espaços, apenas letras, números, ponto (.) ou sublinhado (\_) | "Nome de usuário inválido" |
| RI-02  | Senha                | Credencial de acesso do usuário                        | Digitado   | Sim             | 8 a 20 caracteres, sem espaços                                                       | "Senha inválida"           |
| RI-03  | Senha atual          | Confirma a identidade do usuário na alteração de senha | Digitado   | Sim             | Conforme RI-02                                                                       | "Senha atual incorreta"    |
| RI-04  | Confirmação de senha | Confirma a nova senha informada                        | Digitado   | Sim             | Idêntica ao valor de RI-02                                                           | "As senhas não conferem"   |

### 3.3.2 Cadastro de funcionário e aluno

| **ID** | **Campo**                 | **Descrição**                               | **Origem**       | **Obrigatório** | **Formato e faixa válida**                        | **Mensagem de erro**                                          |
| ------ | ------------------------- | ------------------------------------------- | ---------------- | --------------- | ------------------------------------------------- | ------------------------------------------------------------- |
| RI-05  | Nome                      | Nome completo da pessoa                     | Digitado         | Sim             | Apenas letras e espaços                           | "Nome inválido"                                               |
| RI-06  | CPF                       | Identificação da pessoa                     | Digitado         | Sim             | 11 dígitos, máscara `000.000.000-00`              | "CPF inválido"                                                |
| RI-07  | Data de nascimento        | Data de nascimento da pessoa                | Digitado         | Sim             | `dd/mm/aaaa`, não pode ser posterior à data atual | "Data de nascimento inválida"                                 |
| RI-08  | E-mail                    | Endereço eletrônico da pessoa               | Digitado         | Sim             | Deve conter `@` e ao menos um `.` após o `@`      | "E-mail inválido"                                             |
| RI-09  | Telefone                  | Telefone de contato da pessoa               | Digitado         | Sim             | 11 dígitos, máscara `00 00000-0000`               | "Telefone inválido"                                           |
| RI-10  | Endereço                  | Endereço residencial da pessoa              | Digitado         | Sim             | Texto livre                                       | "Endereço inválido"                                           |
| RI-11  | Cargo                     | Perfil de acesso da pessoa                  | Seleção de lista | Sim             | Administrador, Financeiro ou Professor            | —                                                             |
| RI-12  | Responsável legal         | Responsável legal do aluno menor de 18 anos | Digitado         | Condicional     | Campos de RI-05 a RI-10                           | "Responsável legal é obrigatório para aluno menor de 18 anos" |
| RI-13  | Idiomas que pode lecionar | Idiomas que o professor leciona             | Seleção de lista | Condicional     | Idiomas cadastrados conforme RF-09                | "Informe ao menos um idioma"                                  |
| RI-14  | Modalidade de remuneração | Forma de pagamento do professor             | Seleção de lista | Condicional     | Hora/aula ou valor fixo mensal                    | —                                                             |
| RI-15  | Valor da hora/aula        | Valor da aula do professor                  | Digitado         | Condicional     | Até 2 decimais, exibido com `R$`                  | "Valor inválido"                                              |
| RI-16  | Valor fixo mensal         | Remuneração mensal do professor             | Digitado         | Condicional     | Até 2 decimais, exibido com `R$`                  | "Valor inválido"                                              |

### 3.3.3 Cadastro de idiomas, cursos e salas

| **ID** | **Campo**              | **Descrição**                        | **Origem**       | **Obrigatório** | **Formato e faixa válida**    | **Mensagem de erro**     |
| ------ | ---------------------- | ------------------------------------ | ---------------- | --------------- | ----------------------------- | ------------------------ |
| RI-17  | Nome do idioma         | Nome do idioma oferecido             | Digitado         | Sim             | Apenas letras e espaços        | "Nome do idioma inválido" |
| RI-18  | Níveis                 | Níveis de proficiência do idioma     | Seleção de lista | Sim             | A1, A2, B1, B2, C1 ou C2        | —                         |
| RI-19  | Nome do curso          | Nome do curso oferecido               | Digitado         | Sim             | Letras, números e espaços       | "Nome do curso inválido"  |
| RI-20  | Idioma do curso        | Idioma ao qual o curso se refere      | Seleção de lista | Sim             | Idiomas cadastrados conforme RF-09 | —                       |
| RI-21  | Nível do curso         | Nível de proficiência do curso        | Seleção de lista | Sim             | A1, A2, B1, B2, C1 ou C2        | —                         |
| RI-22  | Carga horária          | Carga horária total do curso          | Digitado         | Sim             | Número                          | "Carga horária inválida"  |
| RI-23  | Identificação da sala  | Identificação da sala                 | Digitado         | Sim             | Texto livre                     | "Identificação inválida"  |
| RI-24  | Capacidade da sala     | Número máximo de alunos da sala       | Digitado         | Sim             | Número inteiro                  | "Capacidade inválida"     |

### 3.3.4 Cadastro de turma

| **ID** | **Campo**                    | **Descrição**                          | **Origem**       | **Obrigatório** | **Formato e faixa válida**           | **Mensagem de erro**           |
| ------ | ---------------------------- | -------------------------------------- | ---------------- | --------------- | ------------------------------------ | ------------------------------ |
| RI-25  | Período                      | Período letivo da turma                | Digitado         | Sim             | Texto livre                          | "Período inválido"             |
| RI-26  | Idioma da turma              | Idioma ensinado na turma               | Seleção de lista | Sim             | Idiomas cadastrados conforme RF-09   | —                              |
| RI-27  | Nível da turma               | Nível de proficiência da turma         | Seleção de lista | Sim             | A1, A2, B1, B2, C1 ou C2             | —                              |
| RI-28  | Modalidade                   | Modalidade de ensino da turma          | Seleção de lista | Sim             | Presencial, Online ou Híbrido        | —                              |
| RI-29  | Professor                    | Professor responsável pela turma       | Seleção de lista | Sim             | Funcionários com cargo Professor     | "Informe o professor da turma" |
| RI-30  | Sala                         | Sala utilizada pela turma              | Seleção de lista | Sim             | Salas cadastradas conforme RI-23     | "Informe a sala da turma"      |
| RI-31  | Número de vagas              | Quantidade de vagas oferecidas         | Digitado         | Sim             | Número inteiro                       | "Número de vagas inválido"     |
| RI-32  | Dias                         | Dias da semana em que há aula          | Seleção de lista | Sim             | Um ou mais dias da semana            | "Selecione ao menos um dia"    |
| RI-33  | Horários                     | Horário de início e de término da aula | Digitado         | Sim             | `hh:mm`, término posterior ao início | "Horário inválido"             |
| RI-34  | Nota do teste de nivelamento | Nota obtida no teste de nivelamento    | Digitado         | Não             | Número                               | "Nota inválida"                |

### 3.3.5 Avaliação e frequência

| **ID** | **Campo**         | **Descrição**                         | **Origem**       | **Obrigatório** | **Formato e faixa válida**               | **Mensagem de erro**             |
| ------ | ----------------- | ------------------------------------- | ---------------- | --------------- | ---------------------------------------- | -------------------------------- |
| RI-35  | Descrição         | Descrição da avaliação                | Digitado         | Sim             | Texto livre                              | "Descrição inválida"             |
| RI-36  | Peso da avaliação | Peso da avaliação no cálculo da média | Digitado         | Sim             | Número inteiro                           | "Peso inválido"                  |
| RI-37  | Data da avaliação | Data em que a avaliação foi aplicada  | Digitado         | Sim             | `dd/mm/aaaa`, não posterior à data atual | "Data inválida"                  |
| RI-38  | Nota              | Nota obtida pelo aluno na avaliação   | Digitado         | Sim             | De 0 a 10, com até 2 casas decimais      | "A nota deve estar entre 0 e 10" |
| RI-39  | Presença          | Registro de presença do aluno na aula | Seleção de lista | Sim             | Presente ou Ausente                      | —                                |

### 3.3.6 Registro de pagamento

| **ID** | **Campo**              | **Descrição**                        | **Origem**       | **Obrigatório** | **Formato e faixa válida**              | **Mensagem de erro** |
| ------ | ---------------------- | ------------------------------------ | ---------------- | --------------- | --------------------------------------- | -------------------- |
| RI-40  | Valor pago             | Valor recebido do aluno              | Digitado         | Sim             | Até 2 decimais, exibido com `R$`        | "Valor inválido"     |
| RI-41  | Data do pagamento      | Data em que o pagamento foi recebido | Digitado         | Sim             | `dd/mm/aaaa`, não posterior à data atual | "Data inválida"      |
| RI-42  | Tipo de desconto       | Desconto aplicado à parcela          | Seleção de lista | Não             | Pontualidade, Parentesco ou Convênio    | —                    |
| RI-43  | Percentual do desconto | Percentual do desconto aplicado      | Digitado         | Condicional     | Número                                  | "Percentual inválido" |

### 3.3.7 Plano de pagamento e parcela

| **ID** | **Campo**           | **Descrição**                    | **Origem**          | **Obrigatório** | **Formato e faixa válida**       | **Mensagem de erro**        |
| ------ | ------------------- | -------------------------------- | ------------------- | --------------- | -------------------------------- | --------------------------- |
| RI-53  | Número de parcelas | Quantidade de parcelas do plano  | Digitado            | Sim             | Número inteiro                   | "Número de parcelas inválido" |
| RI-54  | Valor da parcela   | Valor de cada parcela do plano   | Digitado            | Sim             | Até 2 decimais, exibido com `R$` | "Valor inválido"            |
| RI-55  | Taxa de matrícula  | Valor da taxa de matrícula       | Digitado            | Sim             | Até 2 decimais, exibido com `R$` | "Valor inválido"            |
| RI-56  | Data de vencimento | Data de vencimento da parcela    | Gerado pelo sistema | Sim             | `dd/mm/aaaa`, conforme RF-29.2   | —                           |
| RI-57  | Situação da parcela | Situação atual da parcela        | Gerado pelo sistema | Sim             | Aberta, Paga ou Vencida          | —                           |

### 3.3.8 Consultas e relatórios

| **ID** | **Consulta**            | **Critério de busca**   | **Dados exibidos**                                           |
| ------ | ----------------------- | ----------------------- | ------------------------------------------------------------ |
| RI-58  | Consulta de funcionário | Nome ou nome de usuário | Nome, cargo, dados de contato cadastrais                     |
| RI-59  | Consulta de aluno       | Nome ou CPF             | Nome, dados de contato, responsável legal, turmas e parcelas |
| RI-60  | Consulta de idioma      | Nome do idioma          | Nome e níveis de proficiência                                |
| RI-61  | Consulta de curso       | Nome do curso ou idioma | Nome, idioma, nível e carga horária                          |
| RI-62  | Consulta de sala        | Identificação da sala   | Identificação e capacidade                                   |

| **ID** | **Relatório**            | **Conteúdo**                                                    | **Destinatário** |
| ------ | ------------------------ | --------------------------------------------------------------- | ---------------- |
| RI-63  | Relatório de receitas    | Total recebido no período                                      | Financeiro       |
| RI-64  | Relatório de despesas    | Total repassado aos professores no período                     | Financeiro       |
| RI-65  | Relatório de evasão     | Quantidade de matrículas canceladas no período                  | Financeiro       |
| RI-66  | Extrato do professor     | Aulas ministradas, valores e repasses do período               | Professor        |


# 4. Apêndices

## 4.1 Fórmulas de cálculo

### 4.1.1 Nota média do aluno (RF-26.1)

Média ponderada das notas das avaliações, dividindo a soma do produto de cada nota pelo peso de sua avaliação pela soma dos pesos.

**Fórmula:**

```
nota_média = (nota₁ × peso₁ + nota₂ × peso₂ + ... + notaₙ × pesoₙ) ÷ (peso₁ + peso₂ + ... + pesoₙ)
```

**Exemplo:** duas avaliações.

| Avaliação  | Nota | Peso | Nota × Peso |
|---|---|---|---|
| Prova 1 | 8,0 | 3 | 24,0 |
| Prova 2 | 6,0 | 1 | 6,0 |
| **Total** | | **4** | **30,0** |

`nota_média = 30,0 ÷ 4 = 7,5` → **Aprovado** (7,5 ≥ 5,0).

### 4.1.2 Frequência do aluno (RF-26.2)

Percentual de presenças sobre o total de aulas registradas na turma.

**Fórmula:**

```
frequência = (presenças ÷ total de aulas) × 100
```

**Exemplo:** 20 aulas registradas e 3 faltas, ou seja, 17 presenças.

`frequência = (17 ÷ 20) × 100 = 85%` → **Aprovado** (85% ≥ 70%).

### 4.1.3 Situação final do aluno (RF-26)

O aluno é considerado **Aprovado** quando atende às duas condições abaixo simultaneamente. Se falhar em pelo menos uma, é **Reprovado**.

| Condição | Critério |
|---|---|
| Nota | nota_média ≥ 5,0 |
| Frequência | frequência ≥ 70% |

**Exemplo 1:** nota média 7,5 e frequência 85% → **Aprovado**.
**Exemplo 2:** nota média 7,5 e frequência 60% → **Reprovado** (cumpre a nota, não cumpre a frequência).
**Exemplo 3:** nota média 4,0 e frequência 90% → **Reprovado** (cumpre a frequência, não cumpre a nota).

### 4.1.4 Valor total da matrícula (RF-29.1)

**Fórmula:**

```
valor_total = (número de parcelas × valor da parcela) + taxa de matrícula
```

**Exemplo:** 6 parcelas de R$ 400,00 e taxa de matrícula de R$ 150,00.

`valor_total = (6 × 400,00) + 150,00 = R$ 2.550,00`

### 4.1.5 Vencimentos das parcelas (RF-29.2)

As parcelas recebem vencimentos mensais consecutivos a partir da data da matrícula.

**Exemplo:** matrícula realizada em 10/03/2026.

| Parcela | Vencimento |
|---|---|
| 1ª | 10/04/2026 |
| 2ª | 10/05/2026 |
| 3ª | 10/06/2026 |
| 4ª | 10/07/2026 |
| 5ª | 10/08/2026 |
| 6ª | 10/09/2026 |

### 4.1.6 Repasse ao professor (RF-33.1 e RF-33.2)

O cálculo depende da modalidade de remuneração informada no cadastro do professor.

**Por hora/aula (RF-33.1):**

```
valor_repasse = quantidade de aulas ministradas no período × valor da hora/aula
```

**Exemplo:** 40 aulas ministradas e valor da hora/aula de R$ 60,00.

`valor_repasse = 40 × 60,00 = R$ 2.400,00`

**Por valor fixo mensal (RF-33.2):**

`valor_repasse = valor fixo mensal informado em seu cadastro`

**Exemplo:** valor fixo mensal de R$ 3.000,00 → **R$ 3.000,00**, independentemente da quantidade de aulas.

### 4.1.7 Arredondamento de valores — RNF-14

Todos os cálculos financeiros são realizados com precisão de duas casas decimais. O arredondamento é aplicado sobre o valor obtido:

| Terceira casa decimal | Ação | Exemplo |
|---|---|---|
| Menor que 5 | Trunca o valor | R$ 133,333 → **R$ 133,33** |
| Igual ou superior a 5 | Acrescenta um centésimo | R$ 133,335 → **R$ 133,34** |
| Menor que 5 | Trunca o valor | R$ 133,334 → **R$ 133,33** |

O critério de arredondamento incide sobre o **resultado final do cálculo**, e não sobre cada operação intermediária.

# 5. Índice

- [1. Introdução](#1-introdução)
	- [1.1 Propósito do documento de requisitos](#11-propósito-do-documento-de-requisitos)
	- [1.2 Escopo do produto](#12-escopo-do-produto)
	- [1.3 Definições, acrônimos e abreviações](#13-definições-acrônimos-e-abreviações)
	- [1.4 Referências](#14-referências)
	- [1.5 Visão geral](#15-visão-geral)
- [2. Descrição Geral](#2-descrição-geral)
	- [2.1 Perspectiva do produto](#21-perspectiva-do-produto)
	- [2.2 Funcionalidades do produto](#22-funcionalidades-do-produto)
	- [2.3 Características do usuário](#23-características-do-usuário)
	- [2.4 Restrições gerais](#24-restrições-gerais)
	- [2.5 Suposições e dependências](#25-suposições-e-dependências)
- [3. Requisitos Específicos](#3-requisitos-específicos)
	- [3.1 Requisitos Funcionais](#31-requisitos-funcionais)
		- [3.1.1 Módulo de Usuários e Acesso](#311-módulo-de-usuários-e-acesso)
		- [3.1.2 Módulo de Cadastros](#312-módulo-de-cadastros)
		- [3.1.3 Módulo de Turmas e Matrícula](#313-módulo-de-turmas-e-matrícula)
		- [3.1.4 Módulo de Diário de Classe e Progresso](#314-módulo-de-diário-de-classe-e-progresso)
		- [3.1.5 Módulo de Financeiro](#315-módulo-de-financeiro)
	- [3.2 Requisitos Não Funcionais](#32-requisitos-não-funcionais)
		- [3.2.1 Segurança e LGPD](#321-segurança-e-lgpd)
		- [3.2.2 Usabilidade](#322-usabilidade)
		- [3.2.3 Desempenho](#323-desempenho)
		- [3.2.4 Confiabilidade e integridade](#324-confiabilidade-e-integridade)
		- [3.2.5 Manutenibilidade](#325-manutenibilidade)
		- [3.2.6 Portabilidade e ambiente de execução](#326-portabilidade-e-ambiente-de-execução)
		- [3.2.7 Tratamento de erros](#327-tratamento-de-erros)
	- [3.3 Requisitos de Interface](#33-requisitos-de-interface)
		- [3.3.1 Autenticação](#331-autenticação)
		- [3.3.2 Cadastro de funcionário e aluno](#332-cadastro-de-funcionário-e-aluno)
		- [3.3.3 Cadastro de idiomas, cursos e salas](#333-cadastro-de-idiomas-cursos-e-salas)
		- [3.3.4 Cadastro de turma](#334-cadastro-de-turma)
		- [3.3.5 Avaliação e frequência](#335-avaliação-e-frequência)
		- [3.3.6 Registro de pagamento](#336-registro-de-pagamento)
		- [3.3.7 Plano de pagamento e parcela](#337-plano-de-pagamento-e-parcela)
		- [3.3.8 Consultas e relatórios](#338-consultas-e-relatórios)
- [4. Apêndices](#4-apêndices)
	- [4.1 Fórmulas de cálculo](#41-fórmulas-de-cálculo)
		- [4.1.1 Nota média do aluno — RF-26.1](#411-nota-média-do-aluno--rf-261)
		- [4.1.2 Frequência do aluno — RF-26.2](#412-frequência-do-aluno--rf-262)
		- [4.1.3 Situação final do aluno — RF-26](#413-situação-final-do-aluno--rf-26)
		- [4.1.4 Valor total da matrícula — RF-29.1](#414-valor-total-da-matrícula--rf-291)
		- [4.1.5 Vencimentos das parcelas — RF-29.2](#415-vencimentos-das-parcelas--rf-292)
		- [4.1.6 Repasse ao professor — RF-33.1 e RF-33.2](#416-repasse-ao-professor--rf-331-e-rf-332)
		- [4.1.7 Arredondamento de valores — RNF-14](#417-arredondamento-de-valores--rnf-14)
- [5. Índice](#5-índice)
