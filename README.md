# Login ReactJS
- Projeto de exemplo de tela de login em reactJS

## Comandos
- Criar projeto
    - npx create-react-app login --template typescript
- Iniciar projeto
    - npm start

## Bibliotecas utilizadas
- React Router DOM
    - npm install react-router-dom
- Axios
    - npm install axios

## Como criar um sistema de login

### Para validar o acesso
- Saber se tem um usuário logado
- Se tiver, eu tenho que VALIDAR este usuário
- Se for valido, libera o acesso

### Para logar
- Recebe os dados de login
- Envia uma requisição para o BACKEND validar estes dados no banco de dados
- Estando correto, salva-se alguma referência do usuário no browser
- Se estiver errado, avisa que está errado

### Para deslogar
- Apaga a referência que existir no browser
- Atualiza a página

## Referências
- B7Daily #6 - Sistema de Login com React (ContextAPI, Router, Token e Persistência)
    - https://www.youtube.com/watch?v=iD94avNeoXM
- NPM
    - npmjs.com

32:14
