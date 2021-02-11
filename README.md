# Funcionalidades a serem desenvolvidas:

## Recuperação de senha

**Requisitos Funcionais**

* Usuário pode recuperar sua senha informando seu e-mail;
* Usuário deve receber e-mail com instruções de recuperação de senha;
* Usuário pode redefinir sua senha;

**Requisitos Não Funcionais**

* Utilizar Mailtrap para testar envios em ambiente de desenvolvimento;
* Utilizar Amazon SES para envios em produção;
* O envio de e-mails deve acontecer em segundo plano (background job);

**Regras de Negócio**

* Link enviado por e-mail para redefinir senha, deve expirar em 2 horas;
* Usuário precisa confirmar nova senha ao redefinir sua senha;

## Atualização do perfil

**Requisitos Funcionais**

* Usuário pode atualizar seu nome, e-mail e senha;

**Regras de Negócio**

* Usuário não pode alterar seu e-mail para um já cadastrado no sistema;
* Para atualizar senha, usuário deve informar senha antiga;
* Para atualizar senha, usuário precisa confirmar senha;

## Painel do prestador

**Requisitos Funcionais**

* Prestador pode listar seus agendamentos em data específica;
* Prestador deve receber notificação sempre que houver um novo agendamento;
* Prestador pode visualizar notificações não lidas;

**Requisitos Não Funcionais**

* Agendamentos do prestador no dia devem ser armazenados em cache;
* Notificações de novo agendamento devem ser armazenadas no MongoDB;
* Notificações devem ser enviadas em tempo-real utilizando Socket.io;

**Regras de Negócio**

* Apresentar listagem de agendamentos a partir de data atual;
* Notificação deve possuir status se já foi lida;

## Agendamento de serviços

**Requisitos Funcionais**

* Usuário pode listar todos prestadores de serviço;
* Usuário pode visualizar calendário com pelo menos um dia disponível do prestador escolhido;
* Usuário pode listar horários disponíveis do prestador no dia específico escolhido;
* Usuário pode realizar um novo agendamento com um prestador;

**Requisitos Não Funcionais**

* Listagem de prestadores deve ser armazenada em cache;

**Regras de Negócio**

* Cada agendamento deve durar 1h exatamente;
* Os agendamentos devem estar disponíveis entre 7h às 21h (Primeiro ás 7h e último ás 20h);
* Usuário não pode agendar em horário já ocupado;
* Usuário não pode agendar em horário passado;
* Usuário não pode agendar serviço consigo mesmo;
