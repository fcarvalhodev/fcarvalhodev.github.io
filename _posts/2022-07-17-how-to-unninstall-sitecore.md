---
layout: post
title: Como desinstalar o Sitecore
subtitle: Aprenda a remover o Sitecore complemtamente de seu computador.
cover-img: /assets/img/path.jpg
thumbnail-img: /assets/img/pngwing.com.png
share-img: /assets/img/path.jpg
tags: [development, sitecore, tutorial, fcarvalhodev]
comments: true
---

Fala pessoal! Tudo bem ? Hoje vamos ensinar como remover a instalação do Sitecore, os passos que faremos aqui servem tanto para o Sitecore XP quanto para o Sitecore XC. Se vocês já tentaram instalar o Sitecore alguma vez e enfrentaram algum problema, é bem provável que ao tentar desinstalar, vocês acabaram encontrando mais problemas ainda, correto ?

Isso acontece porque o desinstalador do Sitecore não remove completamente a instalação, ficando boa parte para ser feita na mão.

Então, neste tutorial, ao invés de usarmos o desinstalador, vamos aprender da maneira correta como remover completamente o Sitecore do nosso computador. 

1 - Primeiro vamos parar o nosso IIS, para isso eu recomendo o uso do CMD ao invés de abrir o IIS em si.

2 - Então abra o prompt de comando como administrador, e em seguida execute o comando
~~~ 
iisreset /stop 
~~~ 
para parar todas as instâncias do IIS.

3 - Em seguida abra os serviços do windows, você pode fazer isso digitando serviços na barra de pesquisa, ou através do atalho **WIN+R** e digitando **services.msc**.

4 - Vamos parar o serviço referente ao Solr.

5 - Em seguida, abra o gerenciador de tarefas do windows, e finalize os seguintes serviços, **Sitecore.MAEngine**, **Sitecore.ProcessingEngine** e **Sitecore.XConnectSearchIndexer**.

6 - Pronto! Agora finalmente podemos começar a excluir a nossa instância do Sitecore, vamos começar então pelos registros do windows que o Sitecore cria durante sua instalação.

7 - Para isso, aperte novamente os atalhos **WIN+R** e digite regedit.

8 - No editor de registro do Windows, acesse o seguinte caminho **HKEY_LOCAL_MACHINE/SYSTEM/ControlSet001/Services**.

9 - O primeiro serviço que vamos excluir é o que o Solr cria, então pesquise pela pasta do Solr e efetue a exclusão do mesmo.

10 - Em seguida, procure pelos registros do site que você instalou, os registros deverão estar com o nome do site. Por exemplo, **meusite.sc.dev.local**. Remova todas as referências ao seu site.

11 - Após remover as referências do seu site, feche o regedit e abra o seu servidor de banco de dados.

12 - Durante a instalação do Sitecore, o mesmo cria várias tabelas que são usadas pela plataforma.

13 - Remova todas as tabelas que estão com o nome do seu site, e foram criadas pelo Sitecore.

14 - Após remover todas as tabelas, em sua unidade C:, remova a pasta de instalação do Solr _(normalmente o padrão desta pasta é C:/Solr)_.

15 - Por último, remova todas as referências dos seus sites no seu IIS local, e também delete as pastas que correspondem aos sites em **c:/inetup/wwwroot/...**.

16 - Pronto! Agora basta reiniciar o seu computador, e você estará completamente livre da instalação do Sitecore, pronto para iniciar uma nova, ou não!

Quase todo conteúdo do Sitecore tanto para uso quanto para aprender é pago, então se você gostou deste tutorial não deixe de compartilhar, e talvez dar uma estrelinha nesse repositório ?

[Tutorial com imagens](https://fcarvalhodev.medium.com/como-instalar-o-sitecore-xp-sia-f03b036ff019)

[Repositório deste blog](https://github.com/fcarvalhodev/fcarvalhodev.github.io)  

Muito obrigado, até a próxima!