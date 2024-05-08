//Eduardo Vasconcellos - 202021975

Funcionamento da API!

A API é construída usando Node.js e Express. Ela se conecta a um banco de dados MongoDB e fornece endpoints para criar, recuperar, atualizar e excluir usuários. Além disso, ela fornece um endpoint para autenticar usuários e gerar um token JWT.

Arquivos e Diretórios
src/: Este é o diretório principal que contém todo o código fonte.
src/server.js: Este é o ponto de entrada da aplicação. Ele inicia o servidor Express e define os middlewares e rotas.
src/controllers/: Este diretório contém os controladores para os endpoints da API.
src/middleware/: Este diretório contém os middlewares usados pela aplicação. O middleware VerififyToken é usado para verificar se um token JWT válido foi fornecido nas solicitações à API.
src/database/: Este diretório contém o código para conectar ao MongoDB.
src/models/: Este diretório contém os modelos de dados usados pela aplicação.
Endpoints
POST /register: Este endpoint é usado para registrar um novo usuário. Ele aceita um corpo de solicitação JSON com email e senha, cria um novo usuário no banco de dados e retorna um token JWT.
POST /login: Este endpoint é usado para autenticar um usuário. Ele aceita um corpo de solicitação JSON com email e senha, verifica se o usuário existe e se a senha está correta, e retorna um token JWT.
GET /: Este endpoint é usado para recuperar todos os usuários. Ele retorna uma lista de usuários.
DELETE /:id: Este endpoint é usado para deletar um usuário. Ele aceita um ID de usuário como parâmetro de rota e deleta o usuário correspondente.
PUT /:id: Este endpoint é usado para atualizar um usuário. Ele aceita um ID de usuário como parâmetro de rota e um corpo de solicitação JSON com email e senha, e atualiza o usuário correspondente.

O arquivo routes/index.js

GET /: Esta rota retorna uma resposta JSON com { ok: 'conected' } para confirmar que a API está funcionando corretamente.
GET /usuario: Esta rota retorna todos os usuários. Ela usa o middleware VerififyToken para verificar se o usuário está autenticado.
GET /login: Esta rota é usada para autenticar um usuário. Ela chama a função requestLogin do modelo de usuário.
POST /usuario: Esta rota é usada para criar um novo usuário. Ela usa o middleware VerififyToken para verificar se o usuário está autenticado e, em seguida, chama a função createUser do controlador de usuário.
DELETE /usuario/:id: Esta rota é usada para deletar um usuário. Ela usa o middleware VerififyToken para verificar se o usuário está autenticado e, em seguida, chama a função deleteUser do controlador de usuário.
PUT /usuario/:id: Esta rota é usada para atualizar um usuário. Ela usa o middleware VerififyToken para verificar se o usuário está autenticado e, em seguida, chama a função updateUser do controlador de usuário.
