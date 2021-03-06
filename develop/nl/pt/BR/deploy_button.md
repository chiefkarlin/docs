---

copyright:
  years: 2015, 2017
lastupdated: "2017-4-24"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}


#Criando um botão Implementar no {{site.data.keyword.Bluemix_notm}} {: #deploy-button} 

O botão Implementar no {{site.data.keyword.Bluemix}} é uma maneira eficiente de compartilhar seu app público de origem Git para que outras pessoas possam experimentar com o código e implementá-lo no IBM {{site.data.keyword.Bluemix_notm}}. O botão requer configuração mínima e é possível inseri-lo em qualquer lugar que suporte marcação. Qualquer pessoa que clicar no botão cria uma cópia clonada do código em um novo repositório Git de modo que seu app original permaneça não afetado. 
{: shortdesc} 

**Dica:** se a marca da empresa for importante, será possível [integrar um fluxo
Implementar no iFrame do {{site.data.keyword.Bluemix_notm}}](/docs/develop/deploy_button_embed.html) em seu conteúdo, em vez de inserir um botão. Quando as pessoas criam uma cópia clonada de seu app público de origem Git, elas permanecem em seu conteúdo em vez de serem redirecionadas ao website bluemix.net. 

**Nota**: o recurso de cadeias de ferramentas agora está disponível. Qualquer pessoa que clicar no botão Implementar no
{{site.data.keyword.Bluemix_notm}} poderá clicar no link no banner para tentar implementar o seu aplicativo usando uma cadeia de ferramentas.

Quando alguém clica em seu botão, ocorrem estas ações: 

1. Se a pessoa não tiver uma conta {{site.data.keyword.Bluemix_notm}} ativa, uma conta para teste deve ser criada. 

2. A pessoa pode selecionar uma região, uma organização, um espaço e um nome de app. O nome do app sugerido é construído a partir do nome anterior do app, do nome do usuário da pessoa e do horário. 

3. A ramificação principal do repositório Git público original é clonada em um projeto {{site.data.keyword.jazzhub_title}} novo e privado com um novo repositório Git. 

4. Se o app requer um arquivo de construção, o arquivo de construção é detectado automaticamente e o app é construído. 

5. Se um pipeline for configurado para o processo de construção e implementação, um arquivo `pipeline.yml` será usado para implementar o app.

6. Se o app requer um contêiner, um `pipeline.yml` que define o serviço **IBM Containers** e um Dockerfile que define uma imagem serão usados para implementar o app em um contêiner do {{site.data.keyword.Bluemix_notm}}. 

7. O app é implementado na organização do {{site.data.keyword.Bluemix_notm}} da pessoa. 

##Exemplos do botão {: #button-examples} 

Veja um exemplo do botão de app para um repositório {{site.data.keyword.jazzhub_short}} público:

<p>
<a class="xref" href="https://bluemix.net/deploy?repository=https://hub.jazz.net/git/idsorg/sample-java-cloudant" target="_blank" title="(Abre em uma nova guia ou janela)"><img class="image" src="images/deploy_buttonx2.png" alt="Implementar no Bluemix" /></a>
</p> 

Veja um exemplo do botão de app para um repositório GitHub público: 

<p>
<a class="xref" href="https://bluemix.net/deploy?repository=https://github.com/ibmjstart/bluemix-node-mysql-uploader" target="_blank" title="(Abre em uma nova guia ou janela)"><img class="image" src="images/deploy_buttonx2.png" alt="Implementar no Bluemix" /></a>
</p> 

Veja um exemplo de botão para um app que é implementado em um contêiner do {{site.data.keyword.Bluemix_notm}}: 

<p>
<a class="xref" href="https://bluemix.net/deploy?repository=https://github.com/Puquios/hello-containers" target="_blank" title="(Abre em uma nova guia ou janela)"><img class="image" src="images/deploy_buttonx2.png" alt="Implementar no Bluemix" /></a>
</p> 

##Criando um botão {: #create-button}

Para criar um botão Implementar no {{site.data.keyword.Bluemix_notm}}: 

<ol>
<li> Copie e modifique um dos modelos de fragmento a seguir e inclua um repositório Git público.
<p></p>
<p>
<strong>Dica</strong>: é possível especificar qual ramificação usar incluindo um parâmetro de ramificação na URL do Git. Se você não especificar uma ramificação, a ramificação principal será usada por padrão.
</p>
<ul>
<li>HTML:
<p>
Ramificação principal padrão:
</p>
<pre class="codeblock">
<code class="hljs">
&lt;a href="https://bluemix.net/deploy?repository=&lt;git_repository_URL>" # [required]&gt;&lt;img src="https://bluemix.net/deploy/button.png" alt="Deploy to Bluemix"&gt;&lt;/a&gt;
</code>
</pre>
<p>
Ramificação Git especificada:
</p>
<pre class="codeblock">
<code class="hljs">
&lt;a href="https://bluemix.net/deploy?repository=&lt;git_repository_URL&gt;&branch=&lt;git_branch>" # [required]&gt;&lt;img src="https://bluemix.net/deploy/button.png" alt="Deploy to Bluemix"&gt;&lt;/a&gt;
</code>
</pre>
</li>
<li>Redução de preço:
<p>
Ramificação principal padrão:
</p>
<pre class="codeblock">
<code class="hljs">
[&excl;[Deploy to Bluemix]&lpar;https://bluemix.net/deploy/button.png&rpar;]&lpar;https://bluemix.net/deploy?repository=&lt;git_repository_URL> # [required]&rpar;
</code>
</pre>
<p>Ramificação Git especificada:
</p>
<pre class="codeblock">
<code class="hljs"
[&excl;[Deploy to Bluemix]&lpar;https://bluemix.net/deploy/button.png&rpar;]&lpar;https://bluemix.net/deploy?repository=&lt;git_repository_URL> &branch=&lt;git_branch&gt; # [required]&rpar;
</code>
</pre>
</li>
</ul>
</li>
<li>Insira o fragmento nos blogs, artigos, wikis, arquivos leia-me ou em qualquer lugar em que deseja promover seu app. 
</li>
</ol>

##Considerações de fragmento para o botão {: #button-snippet}

Revise estas considerações quando estiver customizando o fragmento para o botão Implementar no Bluemix. 

* Ambos os modelos usam um caminho padrão para uma imagem de botão externo em formato PNG e em inglês. 

    * Se você preferir usar uma imagem SVG para o botão em vez de um PNG, existe uma versão SVG disponível. É possível alterar o caminho para a imagem de botão externa que é usada no fragmento para `https://bluemix.net/deploy/button.svg`.
	
	* Se preferir usar uma imagem maior para o botão, há uma imagem PNG disponível que tem o dobro do tamanho da original. É possível alterar o caminho da imagem de botão externa que é usada no fragmento para `https://bluemix.net/deploy/button_x2.png`. 
	
	* Se você preferir armazenar a imagem localmente, será possível fazer download da imagem e armazená-la no repositório Git. Ajuste o caminho para usar o local relativo da imagem. 
	
	* Se você desejar usar uma versão traduzida do botão, será possível referenciá-la remotamente ou fazer download em [ftp://public.dhe.ibm.com/cloud/bluemix/deploy_button![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo")](ftp://public.dhe.ibm.com/cloud/bluemix/deploy_button){:new_window}. 
	
##Considerações de repositório para o botão {: #button-repo} 

Revise estas considerações para o repositório do projeto que você usará no botão Implementar no Bluemix. 

<ul>
<li>Um <code>manifest.yml</code> não precisa estar em seu repositório. No entanto, se seu app precisar que outros serviços sejam executados, deve fornecer um arquivo manifest que declare esses serviços.  

Com o arquivo manifest, é possível especificar: 
    <ul>
    <li>Um nome de app exclusivo.</li>  
    <li>Serviços declarados: Uma extensão manifest, que cria ou procura por serviços obrigatórios ou opcionais que devem ser configurados antes que o app seja implementado, como um serviço de cache de dados. É possível localizar uma lista de serviços, rótulos e planos elegíveis do {{site.data.keyword.Bluemix_notm}} usando o <a class="xref" href="https://github.com/cloudfoundry/cli/releases" target="_blank" title="(Abre em uma nova guia ou janela)">CF Command Line Interface<img class="image" src="../icons/launch-glyph.svg" alt="Ícone de link externo"/></a> para executar o comando <code>cf marketplace</code> ou procurando o <a class="xref" href="https://console.ng.bluemix.net/?ssoLogout=true&cm_mmc=developerWorks-_-dWdevcenter-_-devops-services-_-lp#/store" target="_blank" title="(Abre em uma nova guia ou janela)"> catálogo do {{site.data.keyword.Bluemix_notm}}<img class="image" src="../icons/launch-glyph.svg" alt="Ícone de link externo"/></a>. 
    
        
    <strong>Nota:</strong> serviços declarados são uma extensão IBM do formato de manifest padrão do Cloud Foundry. Essa extensão pode ser revisada em uma liberação futura conforme o recurso evolui e melhora.
	
	<a class="xref" href="http://docs.cloudfoundry.org/devguide/deploy-apps/manifest.html#minimal-manifest" target="_blank" title="(Abre em uma nova guia ou janela)">Aprender a criar um arquivo <code>manifest.yml</code><img class="image" src="../icons/launch-glyph.svg" alt="Ícone de link externo"/></a>.  
<pre class="codeblock">
	---
    #Modelo de manifest.yml

  declared-services:
    &lt;`arbitrary_service_instance_name`&gt;:  # [required]
      label: &lt;`actual_service_name`&gt; # [required] The actual service name from market place
      plan: Shared # [optional] If provided, used to fetch the declared service. Otherwise, defaults to 'Free' or 'free'.
  aplicativos:
  - serviços
    - &lt;`arbitrary_service_instance_name`&gt;
    name: &lt;`appname`&gt;
    host: &lt;`apphostname`&gt;
</pre>

<pre class="codeblock">
	---
    #Exemplo de manifest.yml

  declared-services: 
      sample-java-cloudant-cloudantNoSQLDB: 
        label: cloudantNoSQLDB 
        plan: Shared 
  applications:
  - serviços
    - sample-java-cloudant-cloudantNoSQLDB
    name: My app
    host: myapp
</pre>
   </li>
   </ul>
	<li> Se o app deve ser construído antes de poder ser implementado, deve-se incluir um arquivo de construção em seu repositório. Se um arquivo do script de
construção for detectado no diretório-raiz do repositório, uma construção automatizada do código será acionada antes da implementação. 
	
	Construtores suportados: 
	    <ul>
		<li> <a class="xref" href="http://ant.apache.org/manual/using.html" target="_blank" title="(Abre em uma nova guia ou janela)">Ant:<img class="image" src="../icons/launch-glyph.svg" alt="Ícone de link externo"/></a> /<code>build.xml</code>, que constrói a saída para a pasta <code>./output/</code> </li>
		<li> <a class="xref" href="http://docs.cloudfoundry.org/buildpacks/java/build-tool-int.html#gradle" target="_blank" title="(Abre em uma nova guia ou janela)">Gradle:<img class="image" src="../icons/launch-glyph.svg" alt="Ícone de link externo"/></a> <code>/build.gradle</code>, que constrói a saída para a pasta <code>. </code> </li>
		<li> <a class="xref" href="http://gruntjs.com/getting-started#the-gruntfile" target="_blank" title="(Abre em uma nova guia ou janela)">Grunt:<img class="image" src="../icons/launch-glyph.svg" alt="Ícone de link externo"/></a> <code>/Gruntfile.js</code>, que constrói a saída para a pasta <code>. </code> </li>
		<li> <a class="xref" href="http://docs.cloudfoundry.org/buildpacks/java/build-tool-int.html#maven" target="_blank" title="(Abre em uma nova guia ou janela)">Maven:<img class="image" src="../icons/launch-glyph.svg" alt="Ícone de link externo"/></a> <code>/pom.xml</code>, que constrói a saída para a pasta <code>./target/</code></li>
	   </ul>
	</li>	
	<li>Para configurar o pipeline para o projeto em um diretório <code>.bluemix</code>, inclua um arquivo <code>pipeline.yml</code>. É possível criar um arquivo <code>pipeline.yml</code> manualmente ou gerar um a partir de um projeto existente do DevOps Services. Para criar um arquivo pipeline.yml a partir de um projeto do {{site.data.keyword.jazzhub_short}} e incluí-lo em seu repositório, conclua estas etapas. 
<ol>
<li>Abra seu projeto DevOps Services em um navegador e clique em <b>Construir e implementar</b>.</li>
<li>Configure seu pipeline com tarefas de construção e implementação.</li>
<li>Em seu navegador, inclua <code>/yaml</code> na URL de pipeline do projeto e pressione Enter. 
<br>Exemplo: <code>https://hub.jazz.net/pipeline/<owner>/<project_name>/yaml</code></li>
<li>Salve o arquivo <code>pipeline.yml</code> resultante.</li>
<li>No diretório-raiz de seu projeto, crie um diretório <code>.bluemix</code>.</li>
<li>Faça upload do arquivo <code>pipeline.yml</code> para o repositório <code>.bluemix</code>.</li>
</ol> </li>
	<li>Para implementar um app em um contêiner usando o <strong>IBM Containers</strong>, deve-se incluir o Dockerfile no diretório-raiz do repositório e, em um
diretório <code>.bluemix</code>, incluir um arquivo <code>pipeline.yml</code>. 
	<ul>
	    <li>O Dockerfile age como uma espécie de script de construção para o app. Se um Dockerfile for detectado no repositório, o app será construído automaticamente em
uma imagem antes que seja implementado em um contêiner. Se o próprio app precisar ser construído antes do app ser construído em uma imagem, inclua um script de construção
para o app, assim como um Dockerfile, conforme descrito anteriormente.</li>
	    <li> Para aprender mais sobre a criação de Dockerfiles, <a class="xref" href="https://docs.docker.com/reference/builder/" target="_blank" title="(Abre em uma nova guia ou janela)">veja a documentação do Docker<img class="image" src="../icons/launch-glyph.svg" alt="Ícone de link externo"/></a>. </li>
	    <li>É possível criar um arquivo <code>pipeline.yml</code> manualmente ou gerar um a partir de um projeto existente do DevOps Services. Para criar um <code>pipeline.yml</code> manualmente que seja especificamente para contêineres, <a class="xref" href="https://github.com/Puquios/" target="_blank" title="(Abre em uma nova guia ou janela)">veja os exemplos em GitHub<img class="image" src="../icons/launch-glyph.svg" alt="Ícone de link externo"/></a>. </li>
        </ul>

 </li>
 </ul>
</ul>

Para obter ajuda com resolução de problemas, consulte [O botão Implementar no Bluemix não implementa um app](/docs/troubleshoot/ts_apps.html#ts_deploybutton){:new_window}.	
