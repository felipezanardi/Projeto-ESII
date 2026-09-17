# 1. Introdução

## 1.1 Propósito do documento de requisitos

O propósito deste Documento de Requisito (DR) é especificar e descrever de maneira completa, formal e não ambígua todos os requisitos funcionais e não-funcionais do Sistema de Gerenciamento para Escola de Línguas (SGEL), denominado ==(nome do sistema)==. Serve como referência para a entender o escopo do sistema, facilitando sua implementação e o trabalho harmonioso entre a equipe.

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
- Permitir o gerenciamento de idiomas, níveis de proficiência e cursos oferecidos;
- Permitir a criação e organização de turmas, com definição de horários e alocação de salas;
- Validar a disponibilidade de salas e professores, impedindo choques de horários;
- Registrar matrículas, rematrículas e transferências de alunos;
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
- **RF-01** - O sistema deve permitir o cadastro de alunos, contendo nome, documentos, idade, contato e, quando aplicável, dados do responsável legal.
- **RF-02** - O sistema deve permitir o cadastro de professores, incluindo idiomas que podem lecionar, dados pessoais e dados contratuais.
- **RF-03** - O sistema deve permitir o cadastro de funcionários administrativos e financeiros.
- **RF-04** - O sistema deve exigir o cadastro de um responsável legal para alunos menores de idade.
- **RF-05** - O sistema deve permitir o cadastro de idiomas e seus respectivos níveis (A1, A2, I1, I2, B1, B2).
- **RF-06** - O sistema deve permitir o registro de resultado de teste de nivelamento para alunos que desejam ingressar em nível diferente do inicial.
- **RF-07** - O sistema deve permitir a criação de turmas por período/semestre, definindo idioma, nível e modalidade (presencial, online ou híbrido).
- **RF-08** - O sistema deve permitir a alocação de sala a uma turma, verificando a capacidade máxima de alunos.
- **RF-09** - O sistema deve verificar conflitos de horário de sala e de professor antes de confirmar a alocação de uma turma.
- **RF-10** - O sistema deve inserir automaticamente o aluno em lista de espera quando a turma desejada atingir capacidade máxima.
- **RF-11** - O sistema deve notificar o próximo aluno da lista de espera quando surgir uma vaga.
- **RF-12** - O sistema deve permitir ao professor registrar frequência diária dos alunos.
- **RF-13** - O sistema deve permitir ao professor registrar notas e avaliações pedagógicas.
- **RF-14** - O sistema deve permitir ao professor disponibilizar atividades, avaliações e conteúdos pedagógicos.
- **RF-15** - O sistema deve permitir ao professor informar e atualizar sua disponibilidade de dias e horários.
- **RF-16** - O sistema deve manter o histórico acadêmico do aluno, incluindo turmas cursadas, notas, faltas e documentos emitidos.
- **RF-17** - O sistema deve aplicar critérios de aprovação (nota mínima e frequência mínima) definidos para cada turma/curso.
- **RF-18** - O sistema deve permitir a emissão de certificado de conclusão para alunos aprovados.
- **RF-19** - O sistema deve permitir o registro de matrícula de um aluno em uma turma, validando existência de vaga, idade mínima e resultado de nivelamento (quando aplicável).
- **RF-20** - O sistema deve permitir rematrícula do aluno para o período/semestre seguinte.
- **RF-21** - O sistema deve permitir a transferência de um aluno entre turmas, respeitando as mesmas validações da matrícula.
- **RF-22** - O sistema deve impedir nova matrícula de aluno inadimplente.
- **RF-23** - O sistema deve permitir ao Financeiro definir planos de pagamento, valores de mensalidade e taxas de matrícula.
- **RF-24** - O sistema deve permitir o controle de recebimentos, cobranças e identificação de inadimplência.
- **RF-25** - O sistema deve permitir a aplicação de descontos (pontualidade, convênios, parentesco entre alunos).
- **RF-26** - O sistema deve permitir a gestão da folha de pagamento/repasse a professores, por hora/aula ou valor fixo.
- **RF-27** - O sistema deve permitir o registro de venda de materiais didáticos e controle básico de estoque.
- **RF-28** - O sistema deve gerar relatórios de receita, despesas, conversão e evasão de alunos.
- **RF-29** - O sistema deve permitir consulta, por parte do professor, ao próprio extrato de horas/aulas e valores a receber.
## 3.2 Requisitos Não Funcionais
- **RNF-01 (Usabilidade)** - A interface deve ser utilizável por usuários sem conhecimento técnico avançado, especialmente nos perfis Administrador e Professor.
- **RNF-02 (Desempenho)** - Operações de consulta (ex.: verificação de conflito de horário) devem ser processadas em tempo aceitável, evitando bloqueios perceptíveis ao usuário.
- **RNF-03 (Confiabilidade)** - O Sistema não deve permitir inconsistências como duplo agendamento do mesmo professor ou sala no mesmo horário.
- **RNF-04 (Manutenibilidade)** - O Sistema deve ser estruturado de forma modular, permitindo evolução independente dos módulos acadêmicos e financeiro.
- **RNF-05 (Compatibilidade)** - O Sistema deve ser acessível para computadores que possuam JAVA XX.
# 4. Apêndices

# 5. Índice
[1 Introdução](#1-introdução)
[1.1 Propósito do documento de requisitos](#11-propósito-do-documento-de-requisitos)
[1.2 Escopo do produto](#12-escopo-do-produto)
[1.3 Definições, acrônimos e abreviações](#13-definições-acrônimos-e-abreviações)
[1.4 Referências](#14-refências)
[1.5 Visão geral do restante do documento](#15-visão-geral-do-restante-do-documento)
[2 Descrição Geral](#2-descrição-geral)
[2.1 Perspectiva do Produto](#21-perspectiva-do-produto)
[2.2 Funcionalidade do Produto](#22-funcionalidade-do-produto)
[2.3 Características do Usuário](#23-características-do-usuário)
[2.4 Restrições Gerais](#24-restrições-gerais)
[2.5 Suposições e Dependências](#25-suposições-e-dependências)
[3. Requisitos Específicos](#3-requisitos-específicos)
[4. Apêndices](#4-apêndices)
[5. Índice](#5-índice)