# Caso de Uso: Plataforma de Login e Consulta de Repositórios GitHub

## Objetivo:
Desenvolver uma aplicação web simples que permita ao usuário criar uma conta ou fazer login – utilizando autenticação local ou via GitHub OAuth – e, após autenticado, exibir seus repositórios públicos do GitHub.

## Contexto e Cenário
Imagine que você faz parte de uma startup que deseja oferecer uma plataforma para desenvolvedores gerenciarem e visualizarem seus projetos. A ideia é facilitar o acesso à informação dos repositórios do GitHub, centralizando a experiência do usuário em um painel único. Seu desafio será implementar o fluxo de autenticação e a integração com a API do GitHub para a obtenção dos dados públicos dos repositórios.

# Requisitos Funcionais

## Autenticação e Cadastro:
- Cadastro Local: Permitir que o usuário crie uma conta utilizando e-mail e senha.
- Login Local: Permitir o acesso com as credenciais cadastradas.
- Autenticação via GitHub (OAuth): Oferecer a opção “Login com GitHub”, integrando com a API do GitHub para autenticação sem custos diretos.

## Integração com a API do GitHub:
- Após a autenticação, utilizar a API do GitHub para recuperar os repositórios públicos do usuário.
- Exibir os repositórios de forma organizada, mostrando informações básicas como nome do repositório, descrição e data da última atualização.

## Dashboard do Usuário:
- Página inicial após o login que exiba um painel com os repositórios e outras informações relevantes.
- Permitir logout para encerrar a sessão.

## Feedback e Validação:
- Exibir mensagens de erro amigáveis em casos de falha na autenticação ou problemas ao acessar a API.
- Realizar validação dos formulários de cadastro e login.

# Requisitos Não-Funcionais

## Performance:
- Respostas rápidas na autenticação e carregamento dos dados do GitHub.
- Cacheamento simples (quando aplicável) para evitar chamadas desnecessárias à API.

## Segurança:
- Armazenamento seguro de senhas (hashing e salt).
- Proteção contra ataques comuns, como injeção de SQL e XSS.

## Usabilidade:
- Interface responsiva e intuitiva.
- Feedback visual adequado durante carregamentos ou operações assíncronas.

## Escalabilidade:
- Projeto modular que permita a adição de novos provedores de autenticação futuramente.
- Consideração dos limites de requisições da API do GitHub, utilizando tokens autenticados para aumentar o limite para 5.000 requisições por hora.

# Tecnologias Sugeridas

## Front-end:

### Framework: React
- Empacotador: Vite (para desenvolvimento rápido e hot-reloading)
- Bibliotecas Adicionais:
    - React Router (para navegação entre páginas)
    - Axios ou Fetch API (para chamadas à API do GitHub)

## Back-end:

### Plataforma: Node.js
- Framework: Express (para criação de APIs REST)
- Autenticação:
    - Passport.js (para gerenciar estratégias de autenticação, incluindo OAuth com GitHub)
    - JSON Web Tokens (JWT) para controle de sessão

# Banco de Dados:
- Pode ser utilizado um banco de dados relacional (como PostgreSQL) ou NoSQL (como MongoDB) para armazenamento de usuários e suas credenciais.
- Em um cenário de prova de conceito, uma solução mais simples (como SQLite ou mesmo armazenamento em memória) pode ser considerada inicialmente.

## Integração com GitHub:
- Uso da API REST do GitHub para buscar dados dos repositórios públicos.
- Gerenciamento adequado dos tokens de acesso e tratamento dos limites de requisições.

## Ferramentas de Desenvolvimento:
- Git (controle de versão)
- Testes automatizados: Jest (para unit tests no back-end) e React Testing Library (para testes no front-end)

# Fluxo de Usuário
## Acesso à Página Inicial:
O usuário acessa a landing page e tem duas opções: "Cadastrar" ou "Entrar".

## Cadastro/Autenticação:
- Local: Preenche formulário de cadastro ou login.
- Via GitHub: Clica em “Entrar com GitHub”, é redirecionado para o OAuth do GitHub, autoriza a aplicação e retorna autenticado.

## Dashboard:
- Após a autenticação, o usuário é redirecionado para o painel, onde os repositórios públicos do GitHub são exibidos.
- Possibilidade de atualização dos dados mediante clique em “Atualizar” ou recarregar a página.

## Logout:
O usuário pode encerrar a sessão, retornando para a página inicial de login.

# Critérios de Aceitação

## Funcionalidade de Autenticação:
O usuário deve ser capaz de se cadastrar, logar e, se optar, utilizar o GitHub para autenticação sem erros.

## Integração com GitHub:
Após o login via GitHub, os repositórios públicos do usuário devem ser exibidos corretamente no painel.

## Interface:
A interface deve ser responsiva, com feedback visual para carregamentos e erros.

## Segurança:
Dados sensíveis (como senhas) devem ser devidamente protegidos e a comunicação criptografada.

## Código:
O código deve ser limpo, bem documentado e modular, facilitando futuras expansões e manutenção.

# Desafios Adicionais (para Diferenciais)

## Implementação de Testes Automatizados:
Cobertura mínima de 70% do código com testes unitários e de integração.

## Tratamento de Rate Limit:
Implementar lógica para lidar com os limites de requisição da API do GitHub, como cache de resultados ou mensagens de aviso ao usuário.

## Design e Acessibilidade:
Garantir que a aplicação seja acessível, atendendo a padrões de acessibilidade web.

# Considerações Finais
Este caso de uso visa avaliar não apenas a capacidade técnica do candidato em trabalhar com tecnologias modernas (React, Vite, Node.js, Express e integração com APIs externas), mas também sua habilidade em pensar em aspectos de segurança, performance e escalabilidade. O candidato deverá demonstrar clareza na organização do projeto, modularidade do código e atenção aos detalhes que garantem uma boa experiência de usuário. Essa abordagem prática e desafiadora permite que um desenvolvedor júnior mostre seu potencial e compreensão dos fluxos completos de desenvolvimento web.

> Observação: Esse desafio foi gerado pelo GPT, com minha orientações. Muitas das coisas solicitadas não faço a menor ideia de como fazer, mas será divertido.