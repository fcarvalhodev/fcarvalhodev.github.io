---
layout: post
title: Instalando Sitecore XP - SIA
subtitle: Passo a passo de como instalar o Sitecore Experience Plataform
cover-img: /assets/img/path.jpg
thumbnail-img: /assets/img/pngwing.com.png
share-img: /assets/img/path.jpg
tags: [development, sitecore, tutorial]
comments: true
---

Fala pessoal, tudo bem ? Por estar trabalhando recentemente com Sitecore, eu tenho visto que um dos passos mais dolorosos da plataforma, é a sua instalação!

Apesar do alto investimento e de todo o processo contratual que envolve adquirir a plataforma, o seu uso também não é tão simples a princípio, com isso em mente, vamos então abordar a seguir o passo a passo para a instalação do Sitecore Customer Experience, ou como melhor conhecido, Sitecore XP.

Então vamos lá!

Instalação Sitecore XP (SIA).

1 - Primeiro vamos acessar o seguinte link [Sitecore download page](https://dev.sitecore.net/) 

2 - Vamos agora criar uma pasta em nossa unidade **C:** chamada _“Sitecore Installs”_, essa pasta é uma boa prática recomendada pelo próprio Sitecore para efetuarmos a instalação.

3 - Com o site anterior aberto, clique em **download** na versão do Sitecore Experience Plataform. 

4 - Neste tutorial iremos usar a versão do Sitecore XP 10.2 de exemplo.

5 - Você será redirecionado para a página de Downloads do Sitecore.

6 - Na sessão de **On Premises**, efetue o download do recurso gráfico de setup do Sitecore (Graphical setup package for XP single). 


7 - Após efetuar o download, descompacte o arquivo baixado em nossa pasta recentemente criada (C:/Sitecore Installs).

8 - Agora, vamos configurar o nosso setup antes de iniciarmos a instalação. Para isso, abra o arquivo _setup.exe.config_ e altere os seguintes parâmetros.

~~~
<parameter name="SqlServer" type="text" groupName="Sql" value="MEUSERVIDOR" />
<parameter name="SqlAdminUser" type="text" groupName="Sql" value="USUARIOADMIN" />
<parameter name="SqlAdminPassword" type="password" groupName="SENHA" />
~~~

9 - Altere as informações correspondentes ao servidor de banco de dados.

10 - Salve o arquivo.

11 - Agora execute o arquivo Setup.exe como Administrador.

12 - Na primeira tela do nosso assistente, vamos efetuar a instalação dos pré-requisitos do Sitecore. Para isso, clique em Install.

_Aguarde até que a instalação seja concluída, e clique em Next._

13 - Na próxima etapa, iremos instalar o Solr server, mantenha a porta default que está configurada nesta etapa, e preencha o campo path prefix com solr, e por último informe o local de instalação. Por default, o Solr deve ser instalado em **C:/Solr**. Com tudo configurado, clique em “Install”.

14 - Na próxima etapa, informe o nome do seu Site, e defina uma senha para o usuário administrador, normalmente o Sitecore usa apenas _“b”_ como senha padrão, clique em _Next_ para avançar.

15 - Confirme as informações referente ao seu banco de dados.

16 - Por último, confirme na etapa de validação se todos os “checks” estão como verdes, se algo estiver incorreto, a instalação não poderá prosseguir.

17 - Na última etapa, confirme e efetue a instalação.

{: .box-note}
**Note:** (Opcional) Você também pode alterar o prefixo da instância da sua aplicação no arquivo setup.exe.config. Basta alterar os parâmetros: SitecoreSiteName, XConnectSiteName e IdentityServerCertificateName.

Com isso, chegamos ao final da instalação do Sitecore XP! Este processo pelo assistente é bastante fácil, mas ainda há as possibilidades de instalação via SIF e também via DOCKER, mas estes tutoriais ficam para o futuro. :)

Quase todo conteúdo do Sitecore tanto para uso quanto para aprender é pago, então se você gostou deste tutorial não deixe de compartilhar, e talvez dar uma estrelinha nesse repositório ? 

Muito obrigado, até a próxima!