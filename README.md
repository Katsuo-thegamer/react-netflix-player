# ⚛🎞 React Netflix Player
##  A React Player based in Netflix Designer


ℹ Player de video com as funcionalidades existentes no atual player da Netflix Web.

<p align=center>
![shield1](https://img.shields.io/bundlephobia/min/react-netflix-player?style=for-the-badge)
![shield2](https://img.shields.io/github/repo-size/lucasmg37/react-netflix-player?style=for-the-badge)
![shield3](https://img.shields.io/npm/dw/react-netflix-player?style=for-the-badge)
![shield4](https://img.shields.io/github/issues/lucasmg37/react-netflix-player?style=for-the-badge)
![shield5](https://img.shields.io/npm/l/react-netflix-player?style=for-the-badge)
![shield6](https://img.shields.io/github/stars/lucasmg37/react-netflix-player?style=for-the-badge)
![shield7](https://img.shields.io/github/last-commit/lucasmg37/react-netflix-player?style=for-the-badge)
</p>

![Anime-List (1)](https://user-images.githubusercontent.com/25160385/80926822-dbfe8c00-8d6f-11ea-8e39-c24ffc6cfb1b.gif)

<p align=center>
[Recursos](https://github.com/Lucasmg37/react-netflix-player/tree/development-local#-recursos-implementados) | 
[Tecnologias](https://github.com/Lucasmg37/react-netflix-player/tree/development-local#-tecnologias) | 
[Como Utilizar](https://github.com/Lucasmg37/react-netflix-player/tree/development-local#-como-utilizar) | 
[Propriedades](https://github.com/Lucasmg37/react-netflix-player/tree/development-local#-propriedades) | 
[Eventos](https://github.com/Lucasmg37/react-netflix-player/tree/development-local#-eventos) | 
[Controles](https://github.com/Lucasmg37/react-netflix-player/tree/development-local#-modos) | 
[Como Desenvolver](https://github.com/Lucasmg37/react-netflix-player/tree/development-local#-ajude-me-a-desenvolver) | 
[Autor](https://github.com/Lucasmg37/react-netflix-player/tree/development-local#autor) 
</p>

### 📦 Recursos implementados

1. Reprodução de vídeos com Loading e Memória temporária;
2. Listagem de lista de reprodução com marcação do vídeo em atual;
3. Ação para prosseguir para o próximo item;
4. Ação definida ao fim do vídeo;
5. Recursos de Play/Pause, Avançar/Retroceder e FullScreen;
6. Suporte a múltiplos links de reprodução;
7. Informações da mídia em execução;
5. Sistema de ocultação dos controles mediante tempo de espera;
6. Customização de cor (Feature);
7. Tratamento de erros.

### 🧱 Tecnologias

No desenvolvimento desse projeto foi ultilizado
  
 - [React](https://pt-br.reactjs.org/)
 
 - [Sass](https://sass-lang.com/)
 
 - [Babel](https://babeljs.io/)

 - [Webpack](https://webpack.js.org/)

### ⚙ Como utilizar

Em seu projeto react, execute o comando ```npm install react-netflix-player``` para adicionar o react-netflix-player em seu projeto.

Após realize o _import_ do componente no arquivo que deseja adicionar o player

```import ReactNetflixPlayer from "react-netflix-player"```

Pronto, seu componente já está pronto para ser utililado, basta criá-lo em seu arquivo.

```<ReactNetflixPlayer/>```

## 📃 Propriedades

### src: string | vídeo

Parâmetro Obrigatório

Vídeo ou endereço do vídeo a ser reproduzido

Ao alterar esse parâmetro todo o estado do componente é restaurado para o inicial, como informações de posição, buffer e controles.

### title: string,

Texto ao ser exibido como título do vídeo em execução, este texto aparece quando o vídeo fica em situação PAUSADO por muito tempo.

Se essa informação não for informada, nenhuma informação será exibida na tela.

### subTitle: string

Texto auxiliar ao parâmetro de _title_, sua informação será exibida abaixo do título se informada.


### titleMedia: string

Texto localizado na barra de controles, seguindo o design da Netflix, este campo contém o Título da Produção em andamento, pode ser usado para inserir o nome da lista de reprodução.

Se não for enviado, nenhuma informação será apresentada na barra de controles

### extraInfoMedia: string

Texto auxiliar ao parâmetro de _titleMedia_, sua informação será exibida ao lado do título se informada.

### fullPlayer: true

Parâmetro informa se player deve ocupar toda a área da WebView, por padrão é setado como _true_

Observações: Esse parâmetro não se refere ao modo FullScreen do navegador. Se esse parâmetro for passado como _false_, o player ocupara a área disponível informada em seu componente pai.

### backButton: false

Informa se o botão de voltar ⬅ será visível quando os controles estiverem ativos, por padrão ele está desativado.

### autoPlay: false

Informa se o vídeo deverá iniciar automáticamente, por padrão o valor é _false_

### startPosition: 0

Informa em qual segundo a reprodução do vídeo deverá iniciar

### dataNext: {}

Objeto com os dados a serem redenizados na área de *Próximo Vídeo*, este parâmetro não é obrigatório para utilizar a funcionalidade. É possível enviar somente a função a ser executada.

```
    {
        title: 'Texto a ser exebido',
        description: 'Descrição'
    }
```
### reprodutionList: []

Array com itens que compõem a lista de reprodução, devem ser informados já ordenados

Os itens devem ser informados como objetos

```
    {
        id: int // Identificador, será enviado a função informada,
        playing: boolean // Utilizado para diferenciar o item que está em reprodução no momento
    }
```

### onCanPlay: function()

Função disparada no momento em que o vídeo se tornar pronto para reprodução.

Ela tem a mesma função do evento _onCanPlay()_ da tag <video/>, recebendo os mesmo parâmetros da função.

### onTimeUpdate: function()

Função disparada a cada alteração de frames do vídeo.

Ela tem a mesma função do evento _onTimeUpdate()_ da tag <video/>, recebendo os mesmo parâmetros da função.

### onEnded: function()

Função disparada ao término do vídeo

Ela tem a mesma função do evento _onEnded()_ da tag <video/>, recebendo os mesmo parâmetros da função.

### onErrorVideo:  function()

Função disparada quando um erro acontecer na reprodução/busca do vídeo.

Ela tem a mesma função do evento _onErrorVideo()_ da tag <video/>, recebendo os mesmo parâmetros da função.

### onNextClick: function()

Função disparada ao clicar no controle de Próximo Video, sem esse parâmetro o ícone não estará disponível

### onClickItemListReproduction: function()

Função disparada ao selecionar um ítem da lista de reprodução criada com o parâmetro *reprodutionList*, será enviada a função o _id_ relacionado ao item 

### onCrossClick: function()

Função disparada ao fechar o vídeo

Observações: O Fechar vídeo só estará disponível enquanto o vídeo não estiver pronto para reprodução.

Ele foi implementado como fulga do usuário caso o vídeo demore muito a iniciar. O parâmetro não é obrigatório e a sua ausência não remove o ícone de fechar, sendo aconselhável a sua implementação.

### qualities: [] (BETA)

Array com as qualidades da mídia em execução.

Não deve ser implemtado na atual versão do Player


## 🧨 Eventos

### Erro

Caso ocorra algum erro com o vídeo em execução, será renderizado a informação do erro, com a listagem de outros links, para que o usuário possa tentar reproduzir o vídeo em outra qualidade.

1. O botão de fechar é exibido

2. A função _onErrorVideo_ será disparada.

### Controles

Quando o mouse não se move por mais de 5 segundos, automáticamente os controlles são ocultados em tela, voltando a aparecer ao mover o cursor do mouse.

### StandBy

O standby, é uma tela visível quando o vídeo está pausado e não existe moviementos do cursor de mouse.

Ao mover o mouse, ou executar o play pelo *space* o modo é desativado

### Loading

Quando o vídeo está  buscando frames para reprodução e não existem frames suficientes o loading é ativado

## 🕹 Controles

### Double Click

Coloca player em modo de Tela Cheia ou Sai do modo de tela cheia

### Space

Dispara o evento _Pause/Play_

## 🔎 Modos

### Loading Inicial

![image](https://user-images.githubusercontent.com/25160385/80925819-4e1fa280-8d69-11ea-924f-9343af95c733.png)

Ao exibir o componente, ele inicia a busca dos dados do vídeo, até o vídeo estar pronto para reprodução.


### Controles

![image](https://user-images.githubusercontent.com/25160385/80925860-c0908280-8d69-11ea-821a-6dd569328d73.png)

Controles disponível com o vídeo em execução.

Observações: Player configurado com todas as propriedades aceitáveis, no modo FullScreen

### StandBy

![image](https://user-images.githubusercontent.com/25160385/80925937-2bda5480-8d6a-11ea-864b-496c1e52b714.png)

Player PAUSADO em estado de _standby_, as informações do título são renderizadas.

## 👩‍💻 Ajude-me a desenvolver

Para testar/desenvolver o projeto siga os seguintes passos.

### 📦 Requisitos
NodeJs [⬇ Baixe aqui.](https://nodejs.org/en/download/)

Git [⬇ Baixe aqui.](https://git-scm.com/)

Com o node instalado, faça o clone do projeto

```
    git clone https://github.com/Lucasmg37/react-netflix-player
```

Navegue até a pasta do projeto e instale  as dependências

```
    npm install
```

Terminado, você já pode começar a desenvolver

Na pasta *example* coontém a implementação do player para testes

Para rodar a aplicação, execute


```
    npm start
```

Um servidor local estará disponível para visualização

Geralmente o endereço será o _http://localhost:8080/_

Caso não seja, verifique o endereço listado em seu terminal após o comando anterior.

✔ O Player será renderizado com um vídeo de teste. Se este estiver indisponível, altere no arquivo *example/index.js* a propriedade _src_
do componente para um endereço válido.

Para fazer o build, execute

```
    npm build
```

O arquivo final estará disponível na pasta *dist*

## ✨ Melhorei o projeto, e agora?

Chegou a hora de virar um contribuidor! Siga estes passos.

1. Faça um **fork** do projeto.
2. Crie uma nova branch com as suas alterações: `git checkout -b my-feature`
3. Salve as alterações e crie uma mensagem de commit contando o que você fez: `git commit -m "feature: My new feature"`
4. Envie as suas alterações: `git push origin my-feature`

Em pouco tempo você será retornado.

> Caso tenha alguma dúvida confira este [guia de como contribuir no GitHub](https://github.com/firstcontributions/first-contributions)

## 📝 Licença

Este projeto esta sobe a licença MIT. Veja a [LICENÇA](license) para saber mais.

### Autor

| [<img width="120px" src="https://avatars0.githubusercontent.com/u/25160385?s=460&u=ebcea7d6d94724adaea5284286357b1fce500f02&v=4"><br><sub>@lucasmg37</sub>](https://github.com/lucasmg37)|
| :---: |

Feito com ❤ e ☕ por Lucas Dias. 👋🏽 [Entre em contato!](hhttps://www.linkedin.com/in/lucas-junior/)