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

## Context API
- Criando as classes AuthContext e AuthProvider
- AuthContext
    - Seria como uma interface onde definimos o que vamos precisar
- AuthProvider
    - Seria a implementação do que foi definido no AuthContext
- Criou a pasta hooks para requisições dentro do projeto
    - Todos os métodos que fazem requisição na API podem ser colocados dentro de hooks
- Criou o arquivo RequireAuth.tsx
    - Esse arquivo verifica se o usuário está logado ou não
    - Se estiver logado ele mostra o children que é a página que queremos acessar
    - Caso contrário ele exibe a página de login
    - O arquivo RequireAuth foi utilizado na classe de rotas App.tsx
    - Foi utilizado dessa forma `<Route path="/private" element={<RequireAuth><Private /></RequireAuth>} />`
- Criou a pasta Login com o arquivo de login
    - Esse arquivo tem os campos email e senha
    - Tem um botão para realizar o login
    - Tem a utilização do método handleLogin para executar o login
    - Se as informações estiverem corretas redireciona para a página inicial
    - Se estiverem erradas retorna um alerta dizendo que não deu certo
- O AuthProvider foi utilizado no index.tsx raiz do projeto
    - Com isso conseguimos colocar uma parte de autenticação nas páginas do projeto
- Foi adicionado um botão para fazer logout
    - Código do botão para aparecer somente quando estiver logado `{auth.user && <a href="javascript:;">Sair</a>}`
- Foi adicinado na página privada o nome do usuário que está logado
    - Código para mostrar nome `Olá {auth.user?.name}, tudo bem?`
- Foi adicionado persistência para salvar o token no navegador
    - Código para recuperar token `localStorage.getItem('authToken')`
- Dentro do AuthProvider foi colocado um useEffect
    - Quando a página carregar se o token estiver no localStorage, ele vai dar um setUser com as informações do usuário
    - Utiliza o método validateToken para pegar as informações do usuário

## Referências
- B7Daily #6 - Sistema de Login com React (ContextAPI, Router, Token e Persistência)
    - https://www.youtube.com/watch?v=iD94avNeoXM
- NPM
    - npmjs.com

32:14
