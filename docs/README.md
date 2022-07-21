#  **Challenge VtexIo**

Este Repositório hospeda os seguintes items 

  * [Loja Vtex](https://github.com/HamiltonLopes/travellog-group1-store): Usa componente de pontuação para premiar e gamificar a 
    experiência do usuário ao fazer uma compra. A loja é feita com store blocks usando JSON para compor os blocos e a  UI. 
  * [Api Rewards](https://github.com/HamiltonLopes/rewards-API-travellog-group1): API Hospedada na aws com Ec2, Route53 e com dominio
    próprio, essa api acessa um documento no MasterData da VTEX e armazena os dados de id, pontuação e gera um pequeno histórico do
    cliente com seus pontos, com ela pode-se consultar os pontos, e, com ajuda da configuração do OrderHook, creditar as compras do cliente,
    retirando o valor do *frete*. 
  * [Api DebitRewards](https://github.com/HamiltonLopes/vtex-service-get-rewards-points): Api que debita os pontos do usuário, podendo
    ser utilizada com a config do OrderHook para pedidos com status: "canceled", ou por requisição passando uma ordem de debito, o id
    do cliente e o valor a ser debitado dos pontos.
  * [Vtex BackEndService getRewards](https://github.com/HamiltonLopes/vtex-service-get-rewards-points): Serviço interno da vtex que
    escuta a sessão do cliente, consulta sua pontuação na RewardsAPI na aws e escreve a informação na sessão interna VTEX. Gerando também
    um endpoint interno para consulta por clientId. Proporcionando uma segurança para o endpoint, fazendo com que sua url fique escondida.
  * [Vtex-Myaccount-Extension](https://github.com/HamiltonLopes/Vtex-Myaccount-Extension): Extensão do myAccount para adicionar uma aba de
    pontos, informando os pontos do cliente, informação importante para estar junto dos outros dados do mesmo.
  * [VtexBlock PointsComponent](https://github.com/HamiltonLopes/newPointsComponent): Componente Vtex que mostra os pontos do usuário na NavBar
    consultando internamente na própria vtex.session a informação.

## Team 

  * [Hamilton Lopes](https://www.linkedin.com/in/hamilton-lopes/)
  * [Hamiceis Pereira](https://www.linkedin.com/in/hamiceis-pereira/)
  * [Jean Fraga](https://www.linkedin.com/in/jean-fraga/)
  * [Marco Antonio](https://www.linkedin.com/in/marco-antonio-pereira-esteves-005185113/)

## Organização
  * Foi feito a divisão das atividades em pequenas atividades utilizando a ferramenta [Trello](https://trello.com/)
  o nosso quadro de trabalho está disponível para visualização neste [link](https://trello.com/b/IJT1EnnZ/vtex-challenge-travellog-group1).
  
  ![trello](https://user-images.githubusercontent.com/9729963/180127801-2fc01011-b0e3-4c09-bdab-209959708d86.png)
  
## Vtex-Store

### Como rodar este projeto ?

* `git clone` com a url deste repositório 
* Assegure-se de ter seu ambiente configurado e o  Vtex-CLI instalado e configurado
  * [ambiente](https://developers.vtex.com/vtex-developer-docs/docs/vtex-io-documentation-1-basicsetup)  
  * [Vtex-cli](https://developers.vtex.com/vtex-developer-docs/docs/vtex-io-documentation-vtex-io-cli-installation-and-command-reference) 
* Dentro da pasta travellog-group1-store, execute   `vtex login  <yourAccount>`    
* Em seguida para criar um workspace execute `vtex use <dev>`
* Execute `vtex link`
* Log in to your store yourdomain.vtex.com


### Screenshots 
  ![imgstore](https://user-images.githubusercontent.com/9729963/180127132-e46ec500-2792-451a-b2c6-465d42258674.gif)
  
  ![travellog1](https://user-images.githubusercontent.com/9729963/180127291-7ea815ed-e532-43f6-8917-4118a55773b6.png)
  
  ![travellog2](https://user-images.githubusercontent.com/9729963/180127547-3de7d05f-be27-4863-ba67-7a450451059d.png)
  
  ![travellog3](https://user-images.githubusercontent.com/9729963/180127666-b6431a5f-f4d3-4264-bb36-79a7a141631a.png)
  
###  Principais Componentes
  ```"travellog.rewards": "1.x",```
  
  ```"travellog.rewards-extension": "1.x",```
  
  ```"travellog.show-points-service": "0.x"```

## Service  - Points  
  Escrevendo os pontos no mesmo local onde a VTEX escreve os dados de sessão do usuário:
  ![example api](https://user-images.githubusercontent.com/9729963/180129513-197653f6-c5aa-4be9-bf1f-be20db22ac58.png)

## Rotas importantes
  * `https://workspace.enviroment.com/api/sessions?items=*` - Acessa dados da sessão do usuário
  * `https://workspace.enviroment.com/_v/pvt/points/:clientId` - Acessa pontuação do usuário por id

## Documentação-Swagger
  Debit API:
  
  ![debitAPI](https://user-images.githubusercontent.com/9729963/180130339-8963c981-1a99-4665-b02b-0f035c295a49.jpg)
  
  Rewards API:
  
  ![rewardsapi](https://user-images.githubusercontent.com/9729963/180130510-0223a161-4899-49ad-af65-cc90127bcb3e.jpg)

  Antes de acessar a documentação online certifique-se de que as instruções de **Como rodar o projeto** foram executadas. 

## 🚀 Melhorias
As seguintes melhorias precisam ser feitas para aprimoramento do projeto

Principais Pontos de Melhoria:
 - Melhorias no layout em geral, front-end de loja
 - Utilizar mais ferramentas de performance
 - Disponibilizar histórico de pontos no MyAccount, funcionalidde já implementada no backend
 - Loja de pontos, onde o cliente pode utilizar seus pontos para comprar algum item da loja
 - Usar pontos como desconto
 - Plano de upgrade de pontos, onde o cliente pode assinar para ganhar o dobro de pontos nas compras

## Tecnologias utilizadas

#### Principais tecnologias utilizadas no código

💻 [Node.js](https://nodejs.org/)

🛠 [JavaScript](https://www.javascript.com/)

🛠 [TypeScript](https://www.typescriptlang.org/)

🛠 [ReactJS](https://pt-br.reactjs.org/)

💻 [AWS](https://aws.amazon.com/pt/)

#### Vtex Techs|Apis

🛠 [VtexIO](https://vtex.com/pt-br/blog/vtex-book/vtexbook-vtex-io/)

🗄️ [Vtex-MasterData](https://developers.vtex.com/vtex-rest-api/reference/master-data-api-v2-overview)

⚓[Vtex-Hook](https://developers.vtex.com/vtex-rest-api/docs/orders-feed)
