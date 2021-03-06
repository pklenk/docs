---

copyright:
  years: 2016 lastupdated:  "2016-10-14"
---

#	Usando o plano Professional Per Capacity
{: #using_mobilefoundation_p4}

<!--Last updated: 12 September 2016
{: .last-updated} -->

Com o plano Professional Per Capacity, os usuários podem criar qualquer número de aplicativos móveis com vários sistemas operacionais de dispositivos móveis.
Após criar a instância de serviço do {{site.data.keyword.mobilefoundation_short}}: Professional Per Capacity, leia o procedimento a seguir para iniciar o serviço.

## Pré-requisitos
{: #prerequisites_p4}

Considere o seguinte antes de configurar a instância de serviço do {{site.data.keyword.mobilefoundation_short}}: Professional Per Capacity.
* O {{site.data.keyword.mobilefoundation_short}}: Professional Per Capacity é suportado somente com os planos {{site.data.keyword.dashdbshort_notm}}: Enterprise Transactional (que suporta OLTP) {{site.data.keyword.Bluemix_notm}}.

* É necessário ter acesso às credenciais da instância de serviço {{site.data.keyword.dashdbshort_notm}} antes de poder definir
as configurações de sua instância de serviço {{site.data.keyword.mobilefoundation_short}}.

**Nota**: a instância de serviço {{site.data.keyword.dashdbshort_notm}} pode existir em qualquer `Espaço` dentro de sua{{site.data.keyword.Bluemix_notm}} `Organização` ou qualquer outra `Organização` à qual você tem acesso. Assegure-se de ter as permissões para acessar o `Espaço` na qual a instância de serviço
{{site.data.keyword.dashdbshort_notm}} existe.


## Incluindo a conexão com o banco de dados
{: #configure_dashdb_p4}

###  Primeiras etapas
{: #firststeps_p4}

Após criar a {{site.data.keyword.mobilefoundation_short}}: instância de serviço do Professional Per Capacity, siga o procedimento abaixo para iniciar.

### Configurando a conexão para a instância de serviço {{site.data.keyword.dashdbshort_notm}}
{: #connect_dashdb_p4}

Após a instância de serviço do {{site.data.keyword.mobilefoundation_short}}: Professional Per Capacity ser criada, você verá a página *Visão geral*, na qual precisará
especificar informações de conexão para a instância de serviço do {{site.data.keyword.dashdbshort_notm}}: Enterprise Transactional.

1. Selecione a {{site.data.keyword.Bluemix_notm}} `Organização` na qual a instância do serviço {{site.data.keyword.dashdbshort_notm}} existe.

+ Selecione o `Space` do
{{site.data.keyword.Bluemix_notm}}, no qual a instância de
serviço do {{site.data.keyword.dashdbshort_notm}} existe, na lista de espaços disponíveis na `Organization` atual.

**Nota:** se você não vir listados a `Organização` e o `Espaço` nos quais a instância de serviço {{site.data.keyword.dashdbshort_notm}} existe, então, verifique se você é um membro de tal `Organização` e `Espaço`.

+ Selecione o `Service Name` e as `Credentials` do {{site.data.keyword.dashdbshort_notm}} para se conectar à instância de serviço {{site.data.keyword.dashdbshort_notm}} existente.

+  Teste a conexão para a instância de serviço {{site.data.keyword.dashdbshort_notm}}: Enterprise Transactional especificada.

+  Clique em **Incluir**. Essa ação cria as tabelas necessárias na instância de serviço de banco de dados {{site.data.keyword.dashdbshort_notm}} configurada.

**Nota**: não é possível mudar a instância de serviço {{site.data.keyword.dashdbshort_notm}} que está configurada para ser usada por sua instância de serviço {{site.data.keyword.mobilefoundation_short}}. No entanto, é possível usar a mesma instância de serviço {{site.data.keyword.dashdbshort_notm}} em múltiplas instâncias de serviço {{site.data.keyword.mobilefoundation_short}}, uma vez que cada instância de serviço {{site.data.keyword.mobilefoundation_short}} cria seu próprio esquema na instância de serviço {{site.data.keyword.dashdbshort_notm}} selecionada.

* Em alguns segundos, é possível acessar a página `Overview` que fornece tutoriais e vídeos para ajudar a iniciar o serviço {{site.data.keyword.mobilefoundation_short}}.

## Iniciando o servidor {{site.data.keyword.mobilefirst}}
{: #start_mobilefoundation_p4}

* Para iniciar o {{site.data.keyword.mfserver_short_notm}}, com as configurações padrão, clique em **Iniciar servidor básico**.

* Esta seleção provisiona um {{site.data.keyword.mfserver_long_notm}} com as configurações a seguir:
    -  Dois nós com 1 GB de memória cada. Esse tamanho é bom para desenvolvimento, atividades de teste moderado e cargas de trabalho de produção em pequena escala.

    -	O `username` e a `password` são gerados automaticamente para você. Você tem acesso a eles quando o servidor está funcionando.

O processo de fornecimento do servidor inicia. Esse processo leva aproximadamente 10 minutos e uma
janela de mensagem indica o progresso dessa operação. Quando completo, um painel é exibido
no qual é possível ver:

  -	O status do servidor que está em execução (estado, tamanho).

  -	A rota do servidor é criada para você. Use esta rota em seu aplicativo móvel para se
conectar ao {{site.data.keyword.mfserver_short_notm}}.

  -	Seu `nome do usuário` e `senha` para acessar o {{site.data.keyword.mfp_oc_short_notm}}. A `password` fica oculta. Clique
no ícone **Mostrar senha** para visualizá-lo.

*	Clique em **Ativar console** para abrir o {{site.data.keyword.mfp_oc_short_notm}}.


<!--This console runs inside the container.--> Com o console, é possível gerenciar seus aplicativos móveis, adaptadores e dispositivos móveis, usar o servidor como um backend móvel, enviar notificações push e muito mais.

##  Incluindo o servidor Mobile Analytics
{: #adding_analytics_server_p4}

 Agora é possível monitorar o seu aplicativo móvel no servidor {{site.data.keyword.mobilefirst}} incluindo um servidor Mobile Analytics na instância de serviço do
{{site.data.keyword.mobilefoundation_short}}.

 O plano Professional cria o servidor Mobile Analytics em um grupo de contêiner. O usuário pode customizar a configuração selecionando o número de nós do contêiner no grupo de contêiner.

 Os usuários podem anexar volumes nos contêineres para persistir dados. O volume, uma vez selecionado, não pode ser mudado. 20 GB é o espaço de compartilhamento de arquivo padrão disponível para o
usuário. Se o usuário precisar de espaço de armazenamento adicional para persistir dados de analítica, ele precisará comprar compartilhamento de arquivo adicional e criar um volume usando esse
compartilhamento de arquivo. Ele poderá, então, selecionar esse novo volume enquanto implementa o servidor analítico.

 Para obter mais informações sobre a inclusão de volumes no {{site.data.keyword.containerlong}}, consulte
[Armazenando
dados persistentes em um volume usando o Painel do {{site.data.keyword.Bluemix_notm}} ](https://new-console.ng.bluemix.net/docs/containers/container_volumes_ui.html){: new_window}.

* Clique em **Incluir Analytics** para incluir o servidor Mobile Analytics na instância de serviço do {{site.data.keyword.mobilefoundation_short}}.

* É possível escolher a configuração do servidor Mobile Analytics. A configuração mínima suportada para o servidor Analytics é dois nós com 1 GB de memória cada. É possível escolher criar um servidor Analytics com uma configuração máxima de 32 nós com 16 GB de memória cada.

O processo de fornecimento inicia. Esse processo leva aproximadamente 10 minutos e uma
janela de mensagem indica o progresso dessa operação.  

* Ative o Console do MobileFirst Analytics a partir do {{site.data.keyword.mfp_oc_short_notm}}.

* A conexão única é ativada entre o {{site.data.keyword.mfserver_short_notm}} e o servidor Mobile Analytics. O servidor Mobile Analytics é configurado com as mesmas chaves de LTPA e
credenciais do usuário que o servidor {{site.data.keyword.mfserver_short_notm}}. É possível usar o mesmo `username` e `password` para efetuar login no console do Mobile Analytics que aqueles usados para efetuar login no {{site.data.keyword.mfp_oc_short_notm}}.

Para obter mais informações sobre o MobileFirst Analytics, é possível consultar o [MobileFirst Foundation Operational Analytics](https://mobilefirstplatform.ibmcloud.com/tutorials/en/foundation/8.0/analytics/).

**Nota:** o servidor Mobile Analytics é removido quando você exclui a instância de serviço do {{site.data.keyword.mobilefoundation_short}} ou quando você tenta recriar o
{{site.data.keyword.mfserver_short_notm}}.

## Recriando o servidor {{site.data.keyword.mobilefirst}}
{: #recreate_mobilefoundation_p4}

*	Clique em **Recriar** para recriar o servidor.

* Esta ação para o servidor existente e exclui os dados. Uma nova instância do servidor é criada com uma versão atualizada, se disponível. Esta ação
demora alguns minutos para ser concluída.

**Nota**: todos os dados de sua instância de servidor anterior,
incluindo informações sobre os aplicativos e adaptadores, são persistidos na instância
de serviço {{site.data.keyword.dashdbshort_notm}} configurada, esses dados são
usados para recriar seu servidor.

##	Definindo a configuração avançada
{: #using_mfs_advanced_p4}

Use **Iniciar servidor com a configuração avançada** na página `Visão geral` para criar o servidor com configurações avançadas ou customizadas. Também é possível
atualizar as definições do servidor para customizar a configuração do servidor clicando na
guia **Configuração**. O {{site.data.keyword.mobilefoundation_short}} fornece acesso a algumas configurações avançadas.

*	Na guia **Topologia**, é possível selecionar o tamanho do servidor
e o número de instâncias do servidor com base em sua necessidade. O servidor padrão de 1 GB é suficiente para teste de desenvolvimento e leve.
  - Selecione o tamanho correto para seu servidor com base em sua necessidade.

  - **Nós** exibe o número de nós que são criados.

      - O server farm do {{site.data.keyword.mobilefirst}} pode ser criado configurando o número de nós aqui. A configuração mínima suportada é dois nós com 1 GB de memória cada, e a configuração máxima suportada é 32 nós com 16 GB de memória cada.

Consulte a
documentação
do [{{site.data.keyword.mobilefoundation_long}}](https://www.ibm.com/support/knowledgecenter/SSHS8R_8.0.0/wl_welcome.html){: new_window}, para obter mais detalhes.
