## Escolha o idioma / Choose the language
- [Português (BR)](README.md)
- [English](README_EN.md)


## Implementação de esteira CI/CD (Integração contínua/Entrega contínua)
<p align="justify"> CI/CD é um termo abrangente que cobre várias fases do DevOps. CI (integração contínua) é a prática de integrar alterações de código em um repositório várias vezes ao dia. CD tem dois significados: a entrega contínua automatiza as integrações de código, enquanto a implementação contínua libera automaticamente as compilações finais para os usuários finais. Os testes frequentes de CI/CD reduzem erros e defeitos de código, tornando-os essenciais para todo fluxo de trabalho de fluxo de trabalho.</p>

## Conteúdos do documento
  * Autores
  * Visão Geral
  * Pré-requisitos
  * Configuração
  * Uso
  * Licença

## Autores:
Vinícius Peters<br>


## Visão Geral
<p align="justify">A implementação do pipeline CI/CD é necessária para agilizar e padronizar a estrutura do seu ambiente, garantindo a qualidade do código desde o ambiente de desenvolvimento até a sua implementação no ambiente de produção, o que é feito automaticamente após a aprovação dos artefatos. Este documento contém o procedimento para implementar essa estrutura de CI/CD usando o Github Actions e o ambiente Azure.</p>

## Pré-requisitos:
* Ter um usuário de serviço com permissão de acesso ao Synapse.
* Conta no GitHub com um repositório criado.
* Permissão de LEITOR no grupo de recursos.
* Permissão de CONTRIBUIDOR no Synapse-Production.
* Conceder permissão do Service Principal.
* Ter um ambiente Synapse de Desenvolvimento (DEV) e Produção (PROD).

## Configuração
### Arquivo readme.yml
<p align="justify">Em seu repositório Github na aba Code, clique em <strong>creating a new file</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/1.%20Creating%20New%20File.png">
</kbd>
<br><br><br>
<p align="justify">No caminho de pastas, crie um arquivo chamado <strong>readme.yml</strong> na seguinte estrutura <strong> ".github/workflows/readme.yml"</strong>. Após feito isso, clique em <strong>Commit Changes...</strong></p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/2.Readme.yml.png">
</kbd>
<br><br><br>

### Vincular o Synapse com o Github
<p align="justify">Abra o Synapse DEV e nos ícones à esquerda selecione <strong>Manage</strong> e em seguida, clique em  <strong>Git configuration</strong>. Feito isso, no meio da tela, selecione a opção de <strong>Configure</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/3.%20Git%20Configuration.png">
</kbd>
<br><br><br>
<p align="justify">Em <strong>Repository Type</strong>, selecione o GitHub e em <strong>Github repository owner</strong> coloque o nome do proprietário da conta.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/4.%20Configurar%20Reposit%C3%B3rio%20github%201.png">
</kbd>
<br><br><br>
<p align="justify"> Em <strong>Repository name</strong>, selecione o repositório desejado. Para os demais campos, deixe como está e em seguida clique em <strong>Apply</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/5.%20Configurar%20Reposit%C3%B3rio%20github%202.png">
</kbd>
<br><br><br>

### Criando uma Branch
<p align="justify">No canto superior esquerdo, clique em <strong>New Branch[Alt+N]</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/6.%20Criando%20Nova%20Branch.png">
</kbd>
<br><br><br>

<p align="justify">Coloque um nome para sua branch e crie baseada na main conforme o exemplo abaixo. Em seguida, clique em <strong>Create</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/7.%20Criando%20Nova%20Branch%202.png">
</kbd>
<br><br><br>

### Workspace_publish
<p align="justify">A branch workspace_publish será criada automaticamente após ser feito uma publicação no Synapse DEV. Para isso, vamos fazer uma publicação na mesma branch que você acabou de criar! Abra uma pipeline com uma atividade <strong>Set variable</strong> e crie uma variável. Após criado, clique em <strong>Commit all</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/8.%20Vari%C3%A1vel%20para%20Publica%C3%A7%C3%A3o.png">
</kbd>
<br><br><br>

clique em <strong>OK</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/9.%20Confirmando%20Publica%C3%A7%C3%A3o.png">
</kbd>
<br><br><br>
<p align="justify">Feito isso, precisará ser criado um <strong>Pull Request</strong>. Para isso, clique no nome da sua branch no canto superior esquerdo e procure por <strong>Create pull request[Alt+P]</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/10.%20Criar%20Solicita%C3%A7%C3%A3o%20de%20Pull.png">
</kbd>
<br><br><br>
<strong>OBS: Nos passos a seguir, só é possível aprovar um pull request caso você seja o aprovador. Caso contrário, faça uma requisição para o aprovador.</strong>
<br><br>
<p align="justify">Abra seu repositório Github, clique em <strong>Create pull request</strong> ou <strong>Compare & pull request</strong> como mostra a imagem abaixo.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/11.%20Criar%20Solicita%C3%A7%C3%A3o%20de%20Pull%202.png">
</kbd>
<br><br><br>

<p align="justify">Vai abrir uma aba Open a pull request. Clique em <strong>Create pull request</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/12.%20Cria%20Solicita%C3%A7%C3%A3o%20de%20Pull%203.png">
</kbd>
<br><br><br>

<strong>Merge pull request</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/13.%20Merge%20Pull%20Request.png">
</kbd>
<br><br><br>
<strong>Confirm Merge</strong>.
<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/14.%20Confirmar%20Merge.png">
</kbd>
<br><br><br>

<strong>Publish</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/15.%20Publicar%20Main.png">
</kbd>
<br><br><br>

### Localizando Arquivo syn-deploy-yml 

<p align="justify"> O conteúdo do arquivo <strong>syn-deploy.yml</strong> será usado para as atividades abaixo.</p>
<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/16.%20Caminho%20de%20Pasta%20do%20Arquivo%20syn-deploy.yml.png">
</kbd>
<br><br>

### Configurações Repositório Github

<p align="justify">Dentro do seu repositório do GitHub, selecione a aba <strong>Code</strong> e procure o arquivo syn-deploy.yml nas pastas ao lado, copie todo código e cole no arquivo que você acabou de criar seguindo o caminho mostrado na imagem acima.</strong></p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/17.%20Arquivo%20syn-deploy.yml.png">
</kbd>
<br><br><br>
<p align="justify"> E no final deve ser colocado o arquivo com os parâmetros de ambiente, no caso o arquivo <strong>syn-deploy.yml</strong> deve ser posto seguindo o path da imagem mostrada acima.</p>


### Configurando arquivo syn-deploy.yml
<p align="justify">Dentro do arquivo <strong>syn-deploy.yml</strong>, você deve adequar as três linhas <strong>TemplateFile,ParametersFile e OverrideArmParameters</strong> com o nome do seu workspace, como mostra na imagem abaixo destacado em vermelho. Observe que, o arquivo contém linhas que serão valores herdados do Github Secrets(considere os que estão com "${{secrets.____}}). Esses serão os secrets que terão que ser atribuídos no Github.</p>

<kbd>
<img alt="image" srchttps://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/18.%20Arquivo%20syn-deploy%20secrets.png">
</kbd>
<br><br><br>
Esses serão os parâmetros que serão herdados no Github: 

* WORKSPACENAME
* RESOURCEGROUP
* CLIENTID
* CLIENTSECRET
* SUBSCRIPTIONID
* TENANTID

### Configurando Secrets Github

Vá em <strong>Settings</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/19.%20Settings.png">
</kbd>
<br><br><br>
<p align="justify">Ao lado esquerdo da tela, vá em <strong>Secrets and variables</strong> e <strong>Actions</strong>. Na aba <strong>Secrets</strong>, selecione <strong>New repository secret</strong>. Nesse repositório que será atribuído o valor das variáveis que serão herdadas no arquivo <strong>syn-deploy.yml</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/20.%20Secrets%20Github.png">
</kbd>
<br><br><br>
<strong>Vale ressaltar que todos esses parâmetros devem ser preenchidos com os dados do ambiente de Produção.</strong>

Atribua o nome do secret e o valor. Nesse caso, será atribuído para cada um desses:

* WORKSPACENAME
* RESOURCEGROUP
* CLIENTID
* CLIENTSECRET
* SUBSCRIPTIONID
* TENANTID

Exemplo:<br>
<strong>Name</strong> = WORKSPACENAME<br>
<strong>Secret</strong> = nome do seu workspace<br>

Em seguida, clique em <strong>Add secret</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/21.%20Adicionando%20Secret%20no%20Github.png">
</kbd>
<br><br><br>

### Como encontrar cada um dos parâmetros

Para os parâmetros:<br>
* <strong>WORKSPACENAME</strong><br>
* <strong>RESOURCEGROUP</strong><br>
* <strong>SUBSCRIPTIONID</strong><br>

<p align="justify">No portal Azure, procure pelo seu Synapse workspace de produção. Na aba da esquerda ao lado, vá em <strong>Overview</strong> e encontrará as informações dos três parâmetros listados acima.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/22.%20Parametros%20Workspace.png">
</kbd>
<br><br><br>
Para os parâmetros :

<strong>CLIENTID</strong><br>
<strong>CLIENTSECRET</strong><br>
<strong>TENANTID</strong><br>

<p align="justify">Deverá ser criado um Service Principal.Na barra de pesquisa digite <strong>App Registrations</strong> e selecione.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/23.%20App%20Registrations.png">
</kbd>
<br><br><br>
Feito isso, clique em <strong>+New registration</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/24.%20Novo%20Registro%20App%20Registrations.png">
</kbd>
<br><br><br>
Após isso, atribua um nome qualquer e clique em <strong>Register</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/25.%20Registrar%20Application.png">
</kbd>
<br><br><br>

<p align="justify">Após criado, você será levado para a página <strong>Overview</strong> do Service Principal. Aqui, você encontrará o <strong>CLIENTID</strong> e <strong>TENANTID</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/26.%20Clientid%20e%20Tenantid.png">
</kbd>
<br><br><br>
<p align="justify">Para o <strong>CLIENTSECRET</strong>, na barra de opções lateral esquerda selecione a opção <strong>Certificates & secrets</strong>. Após isso, clique em <strong>+ New client secret</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/27.%20ClientSecret%20.png">
</kbd>
<br><br><br>
<p align="justify">Em <strong>Description</strong> coloque uma descrição qualquer ou um nome. Em seguida, clique em <strong> Add </strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/28.%20ClientSecret%202.png">
</kbd>
<br><br><br>
<p align="justify">Após criado aparecerá na coluna <strong>Value</strong> o valor do <strong>CLIENTSECRET</strong>. Grave esse valor, pois ele <strong>só aparecerá uma vez e não será possível ver novamente!</strong></p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/30.%20Value%20Secret.png">
</kbd>
<br><br><br>

### Atribuindo permissões ao Service Principal

<p align="justify">Com todos os parâmetros preenchidos dos passos anteriores, entre no seu workspace do Synapse de <strong>Produção</strong> e vá nas opções de <strong>Access Control(IAM)</strong> e clique em <strong>Role assignment</strong>. Procure mais acima a opção <strong>+ Add</strong>. </p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/31.%20Add%20permiss%C3%A3o.png">
</kbd>
<br><br><br>
<p align="justify">Será atribuído a permissão de <strong>Reader</strong> do Service Principal ao resource group de produção. Para isso, selecione a primeira opção de Reader e em seguida em <strong>Next</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/32.%20Add%20Permissao%202.png">
</kbd>
<br><br><br>
<p align="justify">Na aba Members, clique na opção <strong>+ Select members</strong>. Utilize a barra de pesquisa ao lado para escolher o usuário e clique em <strong>Select</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/33.%20Add%20Permissao%203.png">
</kbd>
<br><br><br>
Feito isso, clique em <strong>Review + assign</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/34.%20Add%20Permissao%204.png">
</kbd>
<br><br><br>
<p align="justify">Dado a permissão de Reader, repita o passo anterior, mas agora dê a permissão de <strong>Contributor</strong> ao workspace de produção. Clique novamente em <strong>Role Assigment</strong> e depois em <strong>+Add</strong>. Selecione a aba Privileged Admnistrator roles, e clique em <strong>Contributor</strong>. Em seguida, clique em <strong>Next</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/35.%20Permissao%20Contributor.png">
</kbd>
<br><br><br>
<p align="justify"> Em Members, clique em em <strong>+Select members</strong> e selecione o usuário para aplicar a permissão de <strong>Contributor</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/36.%20Permissao%20Contributor%202.png">
</kbd>
<br><br><br>
Clique em <strong>Review + assign</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/37.%20%20Permissao%20Contributor%203.png">
</kbd>
<br><br><br>
Por fim, abra o Synpase Studio do Synapse de Produção.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/38.%20Open%20Synapse%20Studio.png">
</kbd>
<br><br><br>
<p align="justify">Vá até a opção <strong>Manage</strong> na lateral esquerda e <strong>Access control</strong>. Clique em <strong>+ Add</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/39.%20Permissao%20Synapse%20Artifact.png">
</kbd>
<br><br><br>
<p align="justify">Selecione a função <strong>Synapse Artifact Publisher</strong>. Na barra de baixo você deve selecionar o usuário Service Principal anteriormente criado e clicar em <strong>Apply</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/40.%20Permissao%20Synapse%20Artifact%202.png">
</kbd>
<br><br><br>

### Configurar Azure Key Vault

<strong>Deverá ser criado um Key vault para os dois ambientes DEV e PROD.</strong>

No portal Azure, vá até a barra de pesquisa e digite por <strong>Key Vaults</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/41.%20Key%20vaults.png">
</kbd>
<br><br><br>
Clique em <strong>+Create</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/42.%20Create%20Key%20Vault.png">
</kbd>
<br><br><br>
<p align="justify">Após isso, preencha as informações de criação do key vault atribuindo o resource group que foi criado no Synapse de Produção. Em seguida, vá até <strong>Review+Create</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/43.%20Create%20Key%20Vault%202.png">
</kbd>
<br><br><br>
<p align="justify">No Key Vault de produção, clique na lateral esquerda em <strong>Access Control(IAM)</strong>, clique em <strong>+Add</strong>e <strong>Add role assignment</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/44.%20Access%20Control%20Key%20Vault.png">
</kbd>
<br><br><br>
Em <strong>Role Assignments</strong> procure por <strong>Key Vault Secrets Officer</strong>. Em seguida, clique em <strong>Next</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/45.%20Key%20Vault%20Secrets%20Officer.png">
</kbd>
<br><br><br>
<p align="justify">Feito isso, vá em Members e na opção <strong>Assign access to</strong> selecione <strong>Managed identity</strong>. Depois de selecionado, clique em <strong>+Select Members</strong>.</p>

Em <strong>Managed Identity</strong> selecione Synapse workspace(). Depois disso, selecione seu ambiente Synapse de Produção.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/46.%20Key%20Vault%20.png">
</kbd>
<br><br><br>

### Configurar Linked Service

Em seu Workspace de DEV, vá até <strong>Manage<strong> e <strong>Linked services</strong>. Clique em <strong>+ New</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/47.%20Linked%20Service.png">
</kbd>
<br><br><br>
Na barra de pesquisa pesquise por <strong>Azure Key Vault</strong> e clique em <strong>Continue</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/48.%20Linked%20Service%202.png">
</kbd>
<br><br><br>
<strong>Nome:</strong> Atribua um nome para o Key Vault.<br>
<strong>Assinatura do Azure:</strong> Selecione sua assinatura.<br>
<strong>Nome do Azure Key Vault:</strong> Selecione o Key Vault criado do ambiente de produção.<br>

Para os demais, deixe padrão. Após isso, clique em <strong>Commit</strong>.

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/49.%20Linked%20Service%203.png">
</kbd>
<br><br><br>
<p align="justify"> O próximo passo você precisará publicar algo novamente em DEV com o Linked Service devidamente criado( repita o passo do tópico Workspace_publish).</p>


<p align="justify">Após isso você deverá entrar em seu arquivo <strong>TemplateWorkspace.json</strong> e buscar o nome do KV que foi gerado automaticamente como mostra abaixo:</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/50.%20TemplateforWorkspace.png">
</kbd>
<br><br><br>
<p align="justify"> Copie o "LS_KV_DEV_properties_typeProperties_baseUrl" e o <strong>defaultValue</strong>. Eles serão utilizados no próximo passo para a criação do arquivo <strong>ParameterPRD.json</strong>.

### Criando arquivo ParameterPRD.json

<p align="justify"> No seu repositório Github, crie um arquivo chamado <strong>ParameterPRD.json</strong> dentro da pasta do seu workspace de DEV e cole os parâmetros copiados anteriormente no seguinte formato:</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/51.%20ParameterPRD.png">
</kbd>
<br><br><br>
<p align="justify"> O nome do arquivo <strong>ParameterPRD.json</strong>, certifique-se de que o seja exatamente igual ao nome que está no arquivo <strong>syn-deploy.yml</strong> em <strong>OverrideArmParameters</strong>.</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/52.%20OverridearmParameters.png">
</kbd>
<br><br><br>

## Uso

<p align="justify"> Em sua branch no ambiente de Desenvolvimento caso haja mudanças, o processo para levar para <strong>produção</strong> irá seguir esses passos:</p>

<p align="justify"> Realize um <strong>commit</strong> com suas mudanças. No exemplo abaixo, iremos utilizar a "Pipeline 2" na branch produto:</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/53.%20Teste%20Pipeline%202.png">
</kbd>
<br><br><br>
<p align="justify"> Crie um <strong>Pull request</strong> para branch principal. No exemplo é a main branch</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/54.%20Pull%20Request%20Pipeline%20Teste.png">
</kbd>
<br><br><br>
<p align="justify"> Após ter seu <strong>Pull request aprovado</strong>, a main branch irá possuir todas as suas alterações. Portanto, o responsável pelo Pull Request, deverá clicar em Publish como mostra a imagem abaixo:</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/55.%20MainBranch%20Publish%20Teste.png">
</kbd>
<br><br><br>
<p align="justify"> Aguarde até que a mensagem de sucesso apareça em sua tela:</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/56.%20Generating%20templates.png">
</kbd>
<br><br><br>
<p align="justify"> Após isso, entre no ambiente de <strong>produção/<strong> e você verá suas alterações no ambiente de produção:</p>

<kbd>
<img alt="image" src="https://github.com/vini-azure22/Synapse_CiCd/blob/main/IMAGES-GIT/57.%20Altera%C3%A7%C3%B5es%20em%20Prod.png">
</kbd>
<br><br><br>
Esteira CI/CD finalizada!
