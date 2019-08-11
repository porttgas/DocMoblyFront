# Manual Front Moblys
## Observações iniciais:
Esse arquivo pode estar meio incompleto pois foi feito somente após a revogação ao meu acesso ao Bob e poderá ir sendo atualizado conforme as necessidades.

## Bob
Todas essas instruções são feitas acessando, no menu do topo, o item **Content** 
### Campanha principal (Desktop)
 No icone da lupa, localizado na barra superior direita, buscar pelo bloco **Home-linha-1**. Esse bloco é dividido em dois campos geralmente: o **text** e **dynamic css**. No text, pegar o HTML e fazer as alterações, colocando os nomes certos para as imagens e os links. Os links estão na planilha, na coluna  *link homepage (desktop)* (No caso das campanhas principais)<br>
*PS:* Para campanhas principais, usar só o link do allproducts no banner<br>
### Apostas
No mesmo bloco da campanha principal, há o html das apostas. Ambos ficam no slider e elas aparecem, normalmente, depois das campanhas. Para facilitar, um código foi implementado no cronograma. Nas últimas colunas há blocos HTML e, ao lado, o nome da imagem que está sendo usada naquele bloco como background. <br>
**Passos**: colocar as imagens no servidor via filezilla (Mais sobre sua funcionalidade mais tarde), copiar  o nome dos arquivos (incluindo a extenão (jpg, png, etc)), colar na coluna ao lado da que gera o HTML na aba de apostas, copiar esse código produzido e colar na parte indicada no código para as apostas
### Subcampanhas:
Seguem mais ou menos o mesmo principio das apostas. Um código já está aplicado no cronograma que pode gerar o html da mesma forma.<br>
**Passos**: Colocar imagens no servidor via filezilla, copiar o nome do arquivo, colar o nome na coluna da aba e subcampanhas indicada para desktop, copiar o código gerado na planilha na parte e colar na parte indicada no bloco **home-linha-2** (Encontrado no mesmo processo da home-linha-1: buscar o nome na caixa de texto e acessá-las). Verificar se está na ordem certa.
### Campanha principal e Apostas (mobile):
Na aba de apostas da planilha, na coluna indicada para imagens mobile, colocar o nome dos arquivos das imagens que irão aparecer nos blocos (Mesmo procedimento de jogar as imagens no servidor pelo filezilla). Colar o código gerado na coluna ao lado dessa na parte indicada dentro do código disponível no bloco **mobile-home**, também encontrado pela ferramenta de busca (Lupa na barra superior). <br>
Para a campanha principal, colocar as imagens do mobile no servidor, substituir o nome da imagem na parte indicada, ir no cronograma, pegar da coluna mobile home e colocar no bloco junto com a imagem certa. Por fim, adaptar o css 
<br>
*PS:* Nos blocos relacionados a desktop, a adaptação do css pode ser feita no bloco dynamic css. Já nos blocos mobile, o css **deve** ser colocado dentro do bloco de estilos (Que geralmente já está no topo do código HTML daquele bloco).
*PS²:* Os perenes ficam nesse mesmo bloco, com o código logo abaixo do das subs (Avisando para caso seja necessário tirar ou adicionar algum desses perenes).
### Subcampanhas (mobile):
Na aba de subcampanhas do cronograma, colocar o nome dos arquivos das imagens que serão usadas (e que foram colocadas no servidor via filezilla) na coluna indicada para imagens mobile. Ao lado dessa coluna será gerado o HTML que deverá ser inserido na parte de conteúdo do bloco **mobile-subcampanha** (ou **mobile-subcampanhas**)
### N1 (Lançamentos | Outlet):
Tanto o bloco de lançamentos (**newness**) quanto o de outlet (**promocoes-block**) já possuem o código para desktop e mobile. Geralmente sua estrutura não muda muito, então é só substituir o nome da imagem e o link (encontrado no cronograma, na aba de N1). 
### Landing Pages:
As páginas de campanhas (Landing pages) podem ser de dois "tipos": as com ou sem menus. Com menus estão associadas a campanha principal e possuem uma imagem maior no topo com o menu logo abaixo dela. Já as sem vão consistir de um título laranja acima do catálogo e são usadas em **Apostas**, **Subcampanhas**, **N1** e  **Newsletters que possuem landing própria** .<br>
**Criação de uma sem menu**: Iniciando pela mais simples: <br>
No lado superior esquerdo, clicar no dropdown e selecionar a opção **static-page**. Uma caixa de texto será aberta ao lado. Ir no cronograma de campanhas e copiar o link (No caso, esse link estará na coluna ao lado da coluna de hash (Ou bem próxima), tendo o formato **tipodecampanha-data-hash** (ex: campanha-20190813-ahskjs)). Colar nessa caixa de texto. Abrir um arquivo .js no editor de texto de sua preferência. Acessar o link do [Github do front](https://mobly-front.github.io/) e ir para a parte de scripts. Clicar na caixa indicada como **CMS com Script title**. Um código assim será copiado para sua área de transferência:
```Javascript
                    $("img[src$='/img/crystal/delete.png']").click();//Delete campos default

                    //Add campos
                    $('#add_items_select').val('1').trigger('change');//Page Title
                    $('#add_items_select').val('5').trigger('change');//Meta Robots
                    $('#add_items_select').val('30').trigger('change');//Hash
                    $('#add_items_select').val('43').trigger('change');//Dynamic JS

                    //DEFAULT
                    //Meta Robots
                    $('#folder-items-content').find('input.form_input').eq(1).val('noindex,follow');
                    //Banner 1
                    //Hash 1
                    var hashTracker = $('#main').children('h2').children('span').eq(1).html().split('-')[2];
                    $('#folder-items-content').find('input.form_input').eq(2).val(hashTracker);
                    //Dynamic JS
                    $('#folder-items-content').find('textarea.form_input').eq(0).val("try{ if(typeof MOBILE != 'undefined' &&MOBILE){ $('<div class=\"conteiner\"> <h1 class=\"mb-15 ml-10 default-title\">'+document.title.split(\"|\")[0]+'</h1> </div>').insertBefore('.catalog-mobile-content ul.catalog-filter'); }else{ $('<div class=\"conteiner\"> <h1 class=\"mt-20 mb-30 default-title\">'+document.title.split(\"|\")[0]+'</h1> </div>').insertBefore('.catalog-v3'); }}catch(e){}");

                    // !!!!!!!!!!!!! TITLE's CAMPO Cronograma de campanha: Front Robo Title !!!!!!!!!!!!!

                    /*Colocar o código para mudar o título da página, encontrado no cronograma*/

                    // !!!!!!!!!!!!! TITLE's CAMPO Cronograma de campanha: Front Robo Title !!!!!!!!!!!!!

                    $("#saveAsNewRevision").click();//Save CMS
```
Na parte indicada para colocar o código para mudar o título, ir no cronograma de campanhas e procurar pelo campo CMS title script ou algo parecido com isso. Copiar os códigos gerados lá e colar no lugar desse aviso. Depois disso, ir até a landing criada e apertar **F12**, **ctrl+shift+i** ou procurar alguma opção para abrir as ferramentas do desenvolvedor. Na aba de console, colar esse código. Ele irá automaticamente substituir o conteúdo daquela página pelo necessário para que ela funcione normalmente. <br>
**Criação de uma com menu**: O processo é basicamente o mesmo do anterior, mas o scrip que deverá ser pego no  [Github do front](https://mobly-front.github.io/) é diferente. No caso, o script é o **CMS com include-block**. O código copiado será o seguinte:
```Javascript
                    $("img[src$='/img/crystal/delete.png']").click();//Delete campos default
                    //Add campos
                    $('#add_items_select').val('1').trigger('change');//Page Title
                    $('#add_items_select').val('5').trigger('change');//Meta Robots
                    $('#add_items_select').val('31').trigger('change');//Banner 1
                    $('#add_items_select').val('30').trigger('change');//Hash
                    $('#add_items_select').val('41').trigger('change');//Mobile Banner


                    $('#folder-items-content').find('textarea.form_input').eq(0).val('**include-block:nome_do_block**');
                    //Mobile Block - !!!ambientes ou -
                    $('#folder-items-content').find('textarea.form_input').eq(1).val('**include-block:nome_do_block-mobile**');
                    //DEFAULT
                    //Meta Robots
                    $('#folder-items-content').find('input.form_input').eq(1).val('noindex,follow');
                    //Hash 1
                    var hashTracker = $('#main').children('h2').children('span').eq(1).html().split('-')[2];
                    $('#folder-items-content').find('input.form_input').eq(2).val(hashTracker);
                    // !!!!!!!!!!!!! ALTERAR !!!!!!!!!!!!!
                    //Mobile Block - !!!ambientes ou -

                    /*Colocar o código para mudar o título da página, encontrado no cronograma*/

                    $("#saveAsNewRevision").click();//Save CMS
                    // !!!!!!!!!!!!! ALTERAR !!!!!!!!!!!!!
```

Observe que dois campos extras foram adicionados:
```Javascript 
    $('#folder-items-content').find('textarea.form_input').eq(0).val('**include-block:nome_do_block**');
                    //Mobile Block - !!!ambientes ou -
    $('#folder-items-content').find('textarea.form_input').eq(1).val('**include-block:nome_do_block-mobile**');
```
Na parte indicada como "nome_do_block", substituir pelo nome seguindo o padrão **data-nomedacampanha** (ex: 20190813-semanam). Aí todas as páginas da campanha com essas informações puxarão um mesmo **static-block**
### Static-blocks:
Blocos que aparecem em mais de uma página, possibilitando uso de menus com mais facilidade. Geralmente usados em campanhas principais.<br>
**Passos:** no dropdown na lateral superior esquerda, selecionar a opção **static-block**. Na caixa ao lado, colocar o nome do bloco (definido naquele script anteriormente mostrado). Uma página com um único campo (*text*) será aberta. É possível reusar o código de blocos anteriores. Para encontrá-lo, procurar pelo link da campanha anterior (O miolo, com data-tipo-hash) que tenha algum bloco. Procurar por esse bloco no icone da busca no menu superior. Copiar seu código. Na versão desktop, substituir a imagem e os links (No cronograma de campanhas, (Considerando que se esteja criando uma campanha principal) na aba de campanhas principais, uma das últimas colunas é Menu com HL ou algo assim. Copiar esses códigos relacionados àquela campanha (ignorar só o allproducts) e colar no lugar do menu que já está no código).<br>
Na versão mobile, substituir o nome e o link da campanha allproducts no topo, copiar os links na coluna ao lado do menu com HL para desktop na planilha de cronograma, colar no lugar do que já estiver e salvar no bloco novo.
### Página de imprensa:
Para adicionar uma nova notícia na página de imprensa (Procurar no campo de busca por **imprensa**), adicionar ao vetor de noticias (Na parte de Dynamic JS) as informações sobre a nova, seguindo o padrão:
```Javascript
{
    data: "12 de julho de 2019", //Data da notícia
    titulo: "Entrevista Victor Noda", //Título da notícia
    imgUrl: "https://staticmobly.akamaized.net/cms/marketing/campanha/Noticias/correio-braziliense-entrevista-victor-destaque.png", //Imagem que irá aparecer como thumbnail (Pode ser o link da imagem presente no topo da própria notícia)
    noticiaUrl: "/correio-braziliense-entrevista-victor", //url (logo explico como criar essa url)
    autoria: "Correio Braziliense", //autor
    categoria: "institucional" //categoria (Falar com a responsável pela página para saber qual o tipo. É usado no filtro)
  }
```
Colocar essas informações entre colchetes com uma vírgula logo depois (Pois o código mais recente deve ser colocado acima dos outros). 

```Javascript
//Sempre essa estrutura
{
    data: "12 de julho de 2019",
    titulo: "Entrevista Victor Noda",
    imgUrl: "https://staticmobly.akamaized.net/cms/marketing/campanha/Noticias/correio-braziliense-entrevista-victor-destaque.png",
    noticiaUrl: "/correio-braziliense-entrevista-victor",
    autoria: "Correio Braziliense",
    categoria: "institucional"
  },{
    data: "17 de julho de 2019",
    titulo: "E-commerce Mobly abre<br> sua primeira loja física em São Paulo",
    imgUrl: "https://abrilmdemulher.files.wordpress.com/2019/07/img_0092.png?quality=90&strip=info&crop=388px%2C88px%2C2222px%2C1511px&resize=680,453",
    noticiaUrl: "/mdemulher-loja-fisica",
    autoria: "M de Mulher",
    categoria: "institucional"
  },...
```

### Página das notícias
As notícias são colocadas em nosso site via prints (por questões judiciais). Para tirar print da tela inteira da notícia, acessá-la, usar algum dos comandos ditos anteriormente para acessar as ferramentas de desenvolvedor, usar o comando **ctrl+shift+p** para abrir uma caixa de texto, digitar **screenshot** e selecionar a opção **full-size screenshot** ou algo do tipo (no chrome). Um print da tela inteira será tirado e salvo no computador. Editar a imagem para que apareça só a notícia na tela (Pedir ajuda aos pintores para casos de emergência). Jogar no filezilla (no caso, em uma pasta diferente, que irei explicar depois). Criar uma static-page com o nome **igual ao nome do arquivo que foi jogado no filezilla** e colocar o campo de text dessa página criada o código 
```
    **include-block:noticia** (ou **include-block:noticias**, agora esqueci)
```
Esse bloco possui um código que pega o link da imagem e gera no meio da página uma imagem com o src necessário para que ela apareça, facilitando a criação.


### Agendamentos | Inserção de novos campos nas static-pages e blocks
Para inserir novos campos nas static-pages | static-blocks, clicar no dropdown dentro dessa page|block no canto inferior esquerdo e selecionar a opção desejada. Uma das mais usadas é a **scheduled-date**, que vai servir para o agendamento das campanhas e alteração de id nos blocos. 
#### Datas:
Aproveitando o assunto de agendamentos, segue as datas em que há trocas de campanhas 

|Tipo|Datas (Definidas até o momento em que esse documento está sendo redigido)|
|:---:|:----:|
|Campanha principal | Toda terça|
|Apostas | Toda terça, junto com a campanha|
|Subcampanhas | Terça (junto com a campanha), sexta e domingo|
|N1 | Toda sexta, sendo uma semana a de lançamentos e a outra a de outlet (Troca quinzenalmente)|
|Área de imprensa | Uma vez por mês, provavelmente no comecinho|

### Testes
Para testar nossas campanhas, temos algumas páginas de teste: **home_main_content_teste**, **home_main_content_teste_t**, **home_main_content_teste_w**. Colocar os códigos a serem implementados nas campanhas em alguma dessas páginas (Elas seguem a mesma estrutura da home e de outras páginas, então para testar o slider da home, colocar o código na **home-linha-1-teste-t**, etc). Quando esse documento foi feito, o teste_t estava servindo como testes para a página principal, a teste estava para N1 e a teste_w estava para testar outras páginas.

### Alterações na estrutura da home:
Pesquisar home_main_content. Acessar o resultado com esse nome. Lá dentro estarão os blocos que aparecem na home (Desktop e mobile). Se um dia for necessário, poderá ser tirado algum(ns) desse(s) bloco(s) da home e eles deixarão de aparecer.

### Gerar hashs:
Entrar em qualquer uma das páginas (Não é necessário nem pesquisar, pode ser qualquer uma mesmo). Ir no dropdown no canto inferior esquerdo e adicionar o item **hash** *se na página já não tiver o campo*. Ir na página de scripts do [git do front](https://mobly-front.github.io/) e clicar na caixa preta do campo **Gerador de Hashs**. Ir até a página selecionada, usar algum dos comandos anteriormente ditos para abrir as ferramentas do desenvolvedor e, na aba de console, colar esse código. No console mesmo aparecerão 20 hashs que podem ser copiadas e coladas na planilha (Aba de hashs disponívels)
```Javascript
var quantidade = 20/*Por default, deixamos a quantidade como 20, mas pode se colocar mais ou menos dependendo da necessidade. É só substituir esse valor pelo desejado */;var hashs = "";for(i=0; i < quantidade; i++){ $("#generateHash").click(); hashs += $(".form_input.hashInput").val()+"\n";}console.log(hashs);
```

### Header do site (Menu)
Pesquisar o bloco **cms_menu_subs** (Ou, na parte da lupa para pesquisa, mas no segundo campo de texto, procurar pelo html de algum dos itens do menu) para encontrar o bloco onde ficam os links e imagens do menu. Em n1 trocamos a imagem que aparece no mouseover da página, então pelo menos uma vez por semana há agendamento desse bloco. Se precisar adicionar ou remover algum dos itens do menu é só deletar toda a <code>li</code> com o conteúdo

## Filezilla
Usamos o filezilla para inserir arquivos no servidor. É necessário o FTP e a senha para poder acessar. Quando se acessa, logo na pasta raiz já tem a pasta **campanha**. Acessá-la. Acessando a pasta 2019 (no caso do ano que foi feito a documentação), se encontram todas as imagens usadas nesse ano. É nessa pasta que devem ser colocadas as imagens que serão usadas em campanhas. <br>
No html, os códigos possuem um caminho com o nome da imagem. Substituir o nome pelo arquivo desejado
```
data-bg="[MEDIA_BASE]/cms/marketing/campanha/2019/INSERIR_NOME_DA_IMG.jpg"
```
Para imagens relacionadas a imprensa, adicionar a pasta **Notícias** ao invés da 2019. A estrutura no código irá ser mais ou menos assim na página da notícia:
```
/cms/marketing/campanha/Noticias/NOME_DA_IMAGEM.jps
```

*PS:* Se acontecer de uma imagem estiver com uma informação errada e for necessário substituí-la, alterar o nome dela e jogar no filezilla. Evitar deletar a anterior e colocar a nova ou só substituir a versão antiga pela nova no servidor pois pode acontecer de a imagem nunca <small>talvez seja exagero e eu só não tenha reparado que trocou mas demorou bastante, fui no outro dia trabalhar e ainda não tinha alterado pra versão nova da imagem</small> atualizar pra versão nova (É sério isso já aconteceu)

## Chaordic
O serviço para app que está para morrer (Provavelmente já morreu). 
**Passos**: Acessar a página da chaordic (Disponível no dropdown de acesso rápido do [git do front](https://mobly-front.github.io/) com o nome *neemu*), clicar no card search, depois em mobile banner. Seguir a estrutura do que está ativo no momento para criar um novo (O primeiro bloco conterá a campanha principal e apostas, sendo selecionado TV no dropdown e a quantidade de campos variada. O bloco da esquerda conterá o link, localizado no cronograma na aba app e o bloco da direita conterá o link da imagem, que segue o mesmo processo de qualquer outra imagem já descrita aqui com exceção das da imprensa. Depois, adicionar mais 6 blocos, para os ambientes. O link também estará no cronograma e a imagem pode ser reaproveitada da campanha anterior.)

## Heroku
O novo serviço para o app. É bem mais intuitivo do que o da chaordic.
**Passos**: Após acessar o app, ir em histórico. Clicar na última home que existe lá. Apertar no botão, localizado a direita, escrito *clonar essa home*. Clicar no bloco do topo e no botão *editar* que irá aparecer. Uma modal irá aparecer com os itens que aparecem no slider. Trocar links das imagens e, se for uma campanha ou uma aposta que não irá para a PDP, deixar o dropdown na opção *campanha* e na caixa de texto abaixo colocar a hash da campanha (a mesma encontrada no cronograma de campanhas), se for um produto, deixá-lo na opção *produto* e colocar na caixa de texto abaixo do dropdown o sku do item, e se for uma página externa, deixar como *webpage*. O mesmo vai servir para os demais blocos.

## Salesforce
Todas as instruções para a salesforce são feitas acessando a parte **Content Builder**, que aparece quando se coloca o mouse por cima do **Content Builder** o menu do topo
### E-mail marketing
Clicar com o botão direito em cima do mês que aquele e-mail será enviado. Clicar na opção *create folder*. Uma modal aparecerá, pedindo pelo nome daquela nova pasta. Seguir o padrão *data_geral-ou-exclusiva*, sendo que a informação de se o e-mail é geral ou exclusivo estará no briefing. Subir as imagens na salesforce (Dessa vez não no filezilla. Arrastar as imagens para a salesforce e depois clicar no botão *Sort uploaded content*). Para manter organizado, deixamos as imagens em uma pasta *Imagens* dentro da pasta onde deixará o e-mail salvo. 
<br>
Clicar na imagem, copiar o link clicando no botão azul na lateral esquerda escrita *Copy link* e colar aquele link na parte do html indicada no layout previsto. Colocar os links disponíveis no briefing. Pode-se usar algum e-mail antigo com layout como base ou usar o código disponível na pasta **front template** na rede (CRM).
<br>
No topo, na pasta do email, clicar em *create email > template based*. Escolher o template de preferência (Até esse momento seria alguma das versões do *três blocos*). Clicar em next no canto superior direito. Colocar o nome do e-mail (que está no briefing) e os parâmetros onde indicado. Clicar em next no canto superior direito. Adicionar título e subtítulo (opcional) do email. Copiar o código entre a parte indicada como **end header** e **start footer** do email e inserir no bloco cinza dentro do template. Clicar em next. 


### E-mail apostas
Uma vez por semana, normalmente as quartas, <s>nós usamos rosa</s> enviam um arquivo excel com sku's e informações sobre produtos. Até o momento sempre são 3 e é possível seguir o template já definido. Copiar o email indicado como *data_apostas* para uma outra na data atual. Alterar o seu nome, deixando a data certa. Substituir os itens dentro do html (O nome, link, imagem e preço. Preços estão no briefing, assim como nome. Já imagem e link é necessário buscar pelo SKU na parte de busca do site da Mobly). 

### Colocar para aprovação:
Quando um email fica pronto, é necessário enviá-lo para aprovação. Isso acontece através do botão *Start aproval process*<s>(?)</s> no canto superior direito. Uma pequena modal irá abrir. Clicar no segundo dropdown, selecionando o grupo *Marketing aprove* e depois no botão no canto inferior dessa modal, enviando (Esqueci o texto desse botão, perdoe). Um icone como de avião de papel irá aparecer, indicando que deu tudo certo. 

### Testes:
Quando se faz um e-mail, uma prática é enviá-lo para um teste (Deixamos as informações dos e-mails de teste dentro da pasta do Front na rede do marketing). 
**Passos**: Assim que se clica no último next, depois que o e-mail já foi feito, uma versão renderizada irá aparecer com um erro por causa do Ampscript que não foi devidamente renderizado (O ampscript é uma linguagem que permite inserção de conteúdo dinâmico no e-mail além de conectá-lo as tabelas com informações dos clientes/produtos). No lado esquerdo haverão algumas opções que não lembro muito bem dos símbolos mas lembro das posições então vamos lá. 
No de cima, clicar no icone da pastinha, selecionar a opção data extension, escolher a que deve se conectar aquele email (No caso de e-mails marketing normais ou apostas, escolher a pasta *E-mail Marketing list* > *Engaged list*. Os demais costumam ter uma data extension própria então procurar por uma com o nome parecido). Depois, clicar no icone logo abaixo do selecionado no canto esquerdo (Se me lembro bem, é um icone de duas pessoas uma atrás da outra). Colocar lá as informações dos e-mails de teste e clicar no botão azul **Send test**. Aguardar alguns minutos para o e-mail aparecer na caixa deles. 

## Git
Para deixar todos as ferramentas usadas pelo front em um lugar mais acessível, foi criada a página do git, mencionada algumas vezes nesse manual. Provavelmente as que irão ser mais usadas são as de conferência e os scripts. A parte de script já teve algumas explicações acima então o foco aqui será na ferramenta de conferência

### Conferência
A [Ferramenta de Conferência](https://mobly-front.github.io/moblyFrontcontent/conferencia.html) foi feita para ajudar na conferência dos blocos, pois há um delay ao colocar o html dentro de uma das páginas de teste escritas anteriormente. Para deixar a verificação de links e imagens mais rápidas, desenvolvemos um script (O que está na caixa preta desse link) que, ao ser colado nas ferramentas do desenvolvedor na aba de console de algum desses blocos escritos na lateral inferior direita da página, copia os códigos de cada campo daquela página e copia para a área de transferência. Colando esse código copiado na caixa de texto da página da ferramenta, o html é renderizado. A versão mobile pode ter alguns bugs por conta de responsividade mas pelo menos dá para ter uma noção geral de como a página está.



