Resumo certificação:


Exame: Solution architect associate - SAA - CCO2


O que a AWS me proporciona:  AWS nos possibilita criar softwares sofisticados e escaláveis sem nos preocuparmos com o gerenciamento do recurso físico.

Isso é válido para qualquer tipo de indústria

Infraestrutura Global:  A infra da AWS se baseia em alguns artefatos, como: regiões, az`s, pontos de presença:
Uma região é um cluster de datacenters, onde o mesmo se encontra em uma determinada área geográfica.
Um az é um ou mais data centers que formam o meu cluster.

Como escolher uma região: Isso vai depender de alguns fatores:

Latência
Custo
Conformidade
Serviços disponíveis

Todas as regiões tem muitas zonas de disponibilidade para forma o cluster:

Usually: 3
Min: 2
Max: 6

As AZ`S são formadas por um ou mais data centers com redundância, poder computacional, rede e conectividade. As AZ`s são separadas por conta de desastres naturais.

Edge Locations: São chamadas de pontos de presença que tem por objetivo entregar conteúdo mais rápido através da rede evitando, ou diminuindo, a latência.

Tipos de instâncias:

Para cada tipo de instância existem algumas famílias relacionadas.


Convenção de nome:

Exemplo:  M5.2xlarge 

M:  Instance class
5: Generation of instance ( Geração da instância, a AWS modifica isso a todo o tempo, por exemplo, em um aprimoramento dessa instância a próxima geração seria a 6.

2xlarge: The size of instânce


Categoria de instâncias: 


General Purpose:  Essa instância é boa para cargas de trabalho diversificadas, como um Web Server ou um repositório de configuração. Ela também tem um balanceamento entre Networking, computer and  memory.

Computer Optimized: Esse tipo de instância é boa para cargas de trabalho que necessitam de um processamento intensivo de computação, onde a performance dos processadores precisa ser muito boa, como por exemplo: Servidores de jogos processos de batch, machine learning.

Memory Optimized: Esse tipo de instância é boa para cargas de trabalho que necessitam processar um leque muito grande de dados em memória, como por exemplo: Banco de dados, BI, aplicações que processam uma grande quantidade de dados não estruturados em tempo real.

Storage Optimized: Esse tipo de instância é muito boa quando necessitamos acessar uma grande quantidade de dados locais, por exemplo: cache para banco de dados em memória (redis).


VPC:  É uma rede isolada na nuvem, onde podemos criar sessões isoladas, blocos de ips subjacentes, que agrupam recursos conforme às nossas necessidades. Podemos usar esses blocos como privados sem acesso a internet e públicos com acesso a internet.


CIRD: É um método para repartir os endereços IP e para rotear.


Route Table: Controla as Rotas das Subnets que não necessariamente estão atreladas a outras Route Tables.


EPIS: São IPS efêmeros, ou seja, mesmo que a instância cair o IP não muda. Também posso alocar esse IP a recursos diferentes. Esses IPs podem ser anexados a uma Instância EC2 ou a uma interface de rede.
São IPV4 
Eles só serão deslocados da minha conta se eu fizer o release, caso contrato se eu não fizer o release e o mesmo não estiver anexado a um recursos, terei um custo pequeno por hora.
É possível mascarar uma falha de uma instância ou software realocando esse IP a uma outra instância.


O que é largura de banda:

Está relacionado com medir a capacidade de transmissão, de uma conexão ou rede.
Qual a capacidade de transmissão de uma rede?

A largura de banda vai determinar a velocidade com que os dados trafegam através de uma determinada rede.


Se você tem uma largura de banda pequena, sua velocidade vai ser menor.
Se você tem um largura de banda grande, sua velocidade vai ser maior. ( Ela sendo maior ou mais larga, irá passar mais dados por ela ao mesmo tempo.

https://www.youtube.com/watch?v=_aQNVd64PZU







Cloud Watch:


Metrics:  As métricas são um conceito fundamental no CloudWatch. Uma métrica é como uma variável de monitoramento, seus valores são representados por "data points"
pontos de dados. Um data points é o valor dessa variável de métrica durante um período de tempo. 


Exemplo: Eu tenho uma aplicação, onde eu tenho uma variável de métrica, e essa variável assume valores que chamamos de "data points" que são os valores que aquela métrica assume em um determinado período de tempo.


Tempo de métrica:
Uma métrica ela nunca pode ser deletada, porém se não surgirem novas métricas dentro do período de 15 meses as mesmas atingem o seu período de vida.
Todo valor de uma métrica tem um tempo associado.



Interface de rede: é quem controla o tráfego da rede, podemos anexar ou desanexar essa interface das instâncias.


CodeCommit:

É um sistema de versionamento alocado na cloud onde podemos gerenciar os nossos ativos, como documentos, código ou binários.

O objetivo central dele é gerenciar repositórios git.
Uma das coisas importantes é que o codeCommit tem a sua criptografia em pouso em em trânsito.

Não tem um limite do tamanho do arquivo ou repositório que vocês estão gerenciado.
Quando estamos trabalhando com o codecommit podemos integrá-lo com outros serviços AWS.

Codecommit suporta comando git e também suas chamadas API via CLI.








Private IP  and Public IP:

Quando estamos falando de IP temos que entender que existem dois tipos: o IPV4 e IPV6 o qual veio para suprir a alta demanda da internet nos últimos tempos.

Falando um pouco sobre rede, existem dois tipos de redes privadas como o de uma empresa, ou seja, essa empresa tem seu próprio range específico de IP, e a rede pública que é a da WWW.

Em uma rede privada de uma empresa os hosts conseguem se comunicar entre si, pois estão dentro da mesma rede, porém os mesmo não tem acesso a rede externa. A partir do momento que adicionamos um gateway (proxy), por exemplo um Internet gateway, os computadores passam a ter a visibilidade dos servidores públicos.

Considerações sobre o Public IP: 

O host pode ser identificado a partir da Internet 
Deve ser único em toda rede mundial
Você pode visualizar pela geolocalização

Considerações sobre o Private IP:

Quer dizer que os host podem apenas ser identificados pela rede privada
Deve ser único dentro da rede privada, porém duas empresas podem ter o mesmo IP privado.
Host dentro de uma rede privada podem acessar a internet através de um NAT ou um Internet gateway

EIPS:  Quando executamos uma ação de Stop and Start em uma instância EC2 o IP público muda, caso seja necessário um IP estático, então utilizaremos de um EIP.
 O EIP é um IPV4 que é alocado na nossa conta e só é devolvido para AWS quando não queremos mais utilizá-lo. Podemos anexar um EIP a uma instância ou a um internet gateway.  Um exemplo bem bacana de como podemos utilizar do EIP é em um cenário onde queremos mascarar a falha de uma instância ou software redirecionando esse EIP para outra instância com uma saúde melhor.
   O limite de EIPS por conta é de 5, mas podemos solicitar para a AWS aumentar o limite, se assim for necessário.

Sugestão: Evite usar o EIP, pois geralmente refletem em decisões arquitetônicas ruins, ao invés disso use um IP aleatório e registre um DNS.

Elastic Network Interface:  É um componente lógico dentro de uma VPC que é responsável por dar a uma instância acesso a rede, podemos comparar com um dispositivo físico mesmo, um computador, tablet ou notebook todos esses dependem de um dispositivo de rede para ter comunicação com a internet. 

Uma EC2 pode ter uma ou mais interfaces de rede, sendo a default considerada como primária e as outras, por exemplo, como secundária.

Não podemos retirar a  rede primária de uma EC2 pois a mesma depende desse dispositivo virtual para ter conectividade.

Um exemplo bem bacana de como podemos utilizar uma ENI é criá-la de maneira independente e amarrá-la em voo ou movê-lo de uma EC2 para outra em caso de falha.

Podemos ter ENI diferente atachadas a mesma instâncias, as ENI estão na borda da subnet.

Uma instância sempre vai está associada a uma ENI, os atributos como security group, Public IP, private IP estão atachados a ENI, e consequentemente as EC2 se beneficiam disso para que mantenham a conectividade com a rede.

As ENI podem ser combinadas para aumentar a velocidade de IOPS, cada ENI tem seu próprio endereço único, o MAC Address.

O número de ENI varia de acordo com o tipo de instância.

EC2 - Hibernate:  De maneira simples, a ideia por trás do hibernate é que tenhamos um tempo de inicialização menor quando se trata de instâncias, tendo como uma dos seus principais atributos a preservação da memória RAM, ou seja uma vez que não precisamos carregar, por exemplo o SÓ para a memória, se torna muito mais rápido o workload em questão. O hibernates é utilizado quando não queremos também perder os nossos dados que estão em memória, uma vez que a memória RAM é volátil.
   Para executar essa Ação de Hibernate, todos os dados são salvos em um cache, no caso será o EBS root em um arquivo criptografado. Quando houver uma necessidade de inicialização dessa instância o processo de hibernate carregar esses dados ao estado original tornando o processo de inicialização muito mais rápido e ainda sim preservando o estados das informações.

Use cases: Podemos usar esse tipo de processo em workloads onde salvar o estado da máquina é importante, serviços que demoram muito tempo para inicialização.

Um ponto importante é que o tamanho das informações contidas na memória RAM deve ser no total de 150GB, e também a instância não pode hibernar por mais de 60 dias.


Conceitos importantes no ambiente AWS:  

EC2 - Nitro: 
É uma tecnologia de virtualização nova, com ela podemos ter uma conectividade melhor de rede como também segurança. Quando não estamos utilizando a EC2-Nitro podemos chegar em apenas 32,000 IOPS em um EBS, e quando estamos utilizando 64,000 IOPS. Resumindo, se for necessário ter mais velocidade no EBS é necessário utilizar o EC2-Nitro.

VCPU: Múltiplas threads podem ser executadas a partir de um único core e todas as threads na AWS são representadas como VCPU.


Por exemplo: 

Core1 : 2 threads
Core2 : 2 threads
Core3 : 2 threads
Core4 : 2 threads VCPU

Nesse exemplo temos 4 cores e 8 VCPU, ou seja 8 threads, duas por cores.
Na AWS podemos mudar a quantidade de cores ou threads indo de acordo com o seu Workload.

Capacity Reservation: é uma forma de garantirmos que vamos ter a capacidade necessária quando formos executar as nossas instâncias, ou seja, reservamos uma capacidade que será utilizada em algum momento, essa reserva não tem um termo de comprometimento longo.



IAM:  É um serviço global responsável por gerenciar os acessos na AWS.

Pontos importantes a serem sempre lembrados no ambiente AWS:


Um usuário representa uma pessoa na sua organização, então não podemos ter vários usuários compartilhando do mesmo acesso.
Usuários podem ser agrupados para tornar mais fácil as aplicações de políticas.
Todas as políticas de um grupo são inerentes aos usuários que ali estão.
Grupos não podem conter outros grupos.
Não é uma boa prática deixar um usuário sem um grupo.
Um usuário pode pertencer a vários grupos.
Policies: Políticas são escritas em documentos JSON que definem as permissões de usuários em grupos. 
De o mínimo de permissão para que o usuário consiga executar a atividade em questão.

Políticas inerentes  são relacionadas aos grupos.
As políticas (inline) são relacionadas diretamente ao usuário.

Estrutura de uma política:

Principal: Consiste em qual conta, usuário ou role será aplicada aquela política.
Action: Quais APIS entraram dentro dessa política.
Resources: Em quais recursos as ações poderão ser aplicadas.


MFA: Segundo fator de autenticação, é uma combinação do seu password + uma credencial de segurança através de um dispositivo virtual/físico.

Como eu posso acessar a AWS:

Web Interface 
CLI
SDK


AcessKey = usuário (pode procurar no IAM que ele vai me devolver meu usuário)
SecrectKey = Password

IAM Roles:

Alguns serviços precisam executar algumas ações no ambiente AWS, por exemplo, um CodeBuild pode necessitar listar os objetos de S3, e para isso o mesmo precisa de permissão e isso se dá pelas Roles, Roles são usadas pelos serviços.

IAM security tools:

É uma ferramenta de segurança que nos permite gerar documentos relacionados aos usuários e os status das suas credenciais, por exemplo se teve algum tipo de alteração ou precisa por conta de alguma política.

IAM access Advisor:  Essa ferramenta de segurança nos permite visualizar as permissões que um determinado usuário tem e quais foram os últimos serviços acessados.
Essa ferramenta é bacana quando queremos aplicar o conceito de privilégio mínimo, com isso podemos ver quais permissões não estão sendo usadas e reduzir a mesma.


Melhores Práticas do IAM: 

Não use o usuário root com exceção do momento em que estiver configurando a sua conta, eu sempre devo criar um usuário admin com as permissões necessárias para executar as atividades do dia a dia, ou seja, sempre teremos duas contas.
Para ter um maior controle das permissões e se tornar um trabalho mais fácil de se gerenciar, sempre tente utilizar de grupos.
Crie sempre uma senha muito forte.
Reforce a sua autenticação utilizando o MFA para se proteger contra hackers.
Devemos criar Roles quando desejamos dar permissões a serviços da AWS.
Se for usar a AWS de forma programática ou usar o CLI/SDK será necessário gerar access keys, essas são muito secretas e não devem ser compartilhada.
Se quisermos auditar as permissões podemos usar o IAM credentials de uma forma geral ou IAM access analyzer.







EC2:

A EC2 é uma forma de trabalharmos com a infraestrutura como um serviço na cloud.
Uma EC2 não é apenas um serviço, ou máquina virtual, pois é composta por outros micro serviços como: Network interface, EIPS , Volumes …..

Podemos executar máquinas virtuais 
Podemos persistir dados em volumes
Podemos distribuir as cargas de trabalho através do ELB.
Podemos escalar os serviços através do auto-scaling.


Quais os tipos de sistemas eu posso selecionar em uma EC2:

Windows
Mac OS
Linux 

Bootstrapping: Esse termo significa que será executado comandos quando a sua instância estiver sendo inicializada.

Tarefas (task) utilizadas para automatizar na hora da inicialização da máquina, como updates, softwares, files from internet.
Obs: Quanto mais tarefas, a sua inicialização ficará muito mais custosa em termos de tempo.


Security groups e Classic Ports:

O security group é um firewall que fica na borda de uma instância, ele é um dos atributos da interface de rede que foi criada e que são consumidos pela instância associada na hora da sua criação. O security group define as regras de entrada e saída de uma instância, por padrão todas as regras de entradas são bloqueadas e todas as regras de saída são permitidas. O security group trabalha no padrão Stateful, ou seja, ele guarda o estado do pacote que está entrando na instância, isso significa que  não haverá uma segunda validação para aquele pacote em relação ou outbound.

Um security group pode referenciar outro security group.

Um security group pode estar associado a mais de uma instância.

É uma boa prática manter um security group apenas para porta ssh.

Alguns pontos importantes quando estamos falando de conectividade com uma instância:

Se a sua aplicação receber um timeout, possivelmente a sua aplicação não tem permissão de entrada no servidor, verificar as regras de Security Group.

Se a mensagem recebida pela aplicação for de conexão recusada, possivelmente a aplicação tem um erro ou não está executando.

Class ports to know:

22: ssh, log in to a remote instance or sftp upload a file using ssh.

21: ftp, upload a file into a file share.

80: http, access unsecured websites.

443: https, access secured websites.

3389: RDP, log in to a windows instance.


Ainda sobre EC2: Não é uma boa prática associar as suas credenciais a uma instância EC2 pois outras pessoas podem ter acesso e ver suas credenciais, ao invés disso criar uma Role e associar a essa instância.

Tipo de instâncias e suas formas de pagamentos:

Um ponto importante antes de falarmos sobre as instâncias é que, as instâncias do tipo Linux vocês pagam por segundo após o primeiro minuto, outros tipos de instâncias vocês pagam por hora.

EC2 On-demand: 

O primeiro ponto é que não temos termos de comprometimento, ou seja, podemos utilizar o quanto for necessário para o workload e se não mais, devolver para a AWS sem custos.
É recomendado utilizar por um tempo curto em workload que não podem ser interrompidos.
Esse tipo de instância se torna muito custosa quando se trata de muito tempo de utilização pois a AWS já oferece alguns tipos de instância baseada em termos de compromisso, por exemplo de 1 ou 3 anos com um desconto que pode chegar até 75% em relação a esse tipo(on-demand)

EC2 - Reserved Instances

Nesse tipo de instância podemos chegar em um desconto de até 75% em relação às instâncias On-demand.
Esse tipo de instância nos oferece um termo de comprometimento de 1 ou 3 anos, dependendo da escolha, por exemplo 3 anos, o desconto se torna maior.
Podemos também escolher as formas de pagamento:
Pagar sob demanda 
Pagar parcialmente 
Pagar tudo adiantado
Dependendo da opção o desconto é maior.

Podemos pensar nesse tipo de instância quando estamos falando de banco de dados.


Existem outras camadas das instâncias reservadas:

Convertible reserved instances:   Esse tipo de comprometimento permite modificarmos o tipo das nossas instâncias quando quisermos, isso nos dá um pouco menos de desconto pois podemos modificar o tipo de instância.

Scheduler reserved instances: Esse tipo de comprometimento permite o agendamento da utilização das instâncias, exemplo: queremos utilizar as instâncias apenas nos dias ímpares da semana após as 6 horas.

EC2 - Spot Instances:

Nesses tipos de instâncias podemos chegar a até 90% de desconto em relação ao On-demand.
Um ponto a se atentar é que podemos perder a instância Spot se o preço Spot for maior que o máximo que eu estiver pagando.
O preço Spot muda a todo momento.
Esse tipo de instâncias é recomendado para cargas de trabalhos que suportam falhas.
Esse tipo de instância não é recomendado quando estamos executando workloads criticos ou banco de dados.
Alguns tipos de workload para esses tipos de instâncias são:
Batch jobs. 
Data analysis.
Image processing.
Any distributed workloads.
Workloads with a flexible start and end time.

EC2 - Dedicated Hosts:

Um host dedicado apenas para a sua empresa, o host físico não será compartilhado com outros clientes. Isso lhe dá uma redução de custo quando se trata de licenças on-premises migrando para a cloud. Podemos alugar um host dedicado por 3 anos.

Esse tipo de instância é mais cara pois vamos ter um host completo reservado.
É bom para cenários:
Onde queremos trazer as licenças de software que são complicadas.
Quando a empresa tem um regulamento muito forte em questão de conformidades, por exemplo: Os dados não podem estar no mesmo hardware que um outro cliente X.
Nesse tipo de comprometimento pagamos pelo host.

EC2 - Dedicated Instances:

São instâncias que serão executadas em um hardware dedicado também, porém ao contrário do host dedicado não teremos acesso a algumas informações do hardware subjacente, um exemplo disso é que não podemos trazer as licenças on-premises pois não temos visibilidade dos sockets, cor ou hostID…..
Nesse tipo de  comprometimento pagamos pela instância.


Comparando os tipos de instâncias com um hotel:

On-Demand:  Você se hospeda no hotel, consome o que quiser quando quiser, e paga apenas pelo que consumir e  o tempo que você ficar dentro do hotel.

Reserved:  Você planeja ficar um bom tempo no hotel e reserva um quarto pois isso lhe dá 
um desconto maior.

Spot Instances: Alguns quartos do hotel estão vazios  e os donos do hotel estão dando um grande desconto para quem reservar aquele quarto pois eles querem ganhar mais, com os quartos parados não gera lucro. Um ponto importante é que quem reservar aquele quarto pode perdê-lo, porque  se outra pessoa ofertar mais por ele o dono vai ganhar mais.

Dedicated hosts: Você reserva o hotel todo, por exemplo você é gerente de uma empresa e quer levar a sua equipe toda para o hotel, porém você quer garantir que nenhuma pessoa de outra empresa X esteja no mesmo local pois existe um projeto confidencial que não pode ser divulgado. Comparando com o Dedicated Instance, nesse cenário, por exemplo, as pessoas dessa empresa poderiam ter acesso e utilização do hardware do hotel  para trabalhar.



Sobre as Spot instances:

São instâncias que se comparadas com o on-demand nós darão 90% de desconto.
Para trabalhar com essas instâncias temos que conhecer o Spot price.
Continuaremos com a instância se o preço do Spot price for menor do que estamos pagando, então o Spot price deve sempre ser menor do que você está pagando.
O preço do Spot varia de acordo  com a oferta e capacidade disponível pela AWS.
Esses recursos se tornam muito baratos pois são capacidades que a AWS não está utilizando.
Quando o Spot price for maior do que nós definimos podemos optar por dar um Stop ou Terminate, temos um período de 2 minutos para tomar essa decisão.
Escolha o Stop se precisar do workload da sua instância.
Escolha o Terminated se não precisar das informações da sua instância.


Spot Block:  Esse método é utilizado para quando não queremos que a AWS recolha a instância num período de tempo de 1 a 6 horas.
Nunca utilize Spot Instances em Workloads críticos ou Banco de dados.


Como terminar uma spot instance:

Precisamos entender como o Spot Request funciona.

Spot Request:  Quando estava criando uma Spot Instance utilizamos de um Spot request o qual pode ser definido alguns parâmetros.

Quantas instâncias desejamos.
Máximo preço a ser pago ( ser sempre maior que o Spot Price)
Tipo de request

Tipos de request de uma Spot Instance:

On-time request: A partir do momento que a gente preencher e selecionar esse tipo de pedido as instâncias irão começar a sua execução e o Spot request “Go Away”, não temos mais a visibilidade do spot request.

Persistent request: Nesse tipo de especificação nós queremos que o número de instância seja válido enquanto o Spot request estiver dentro do período especificado, ou seja, se a instância for interrompida pelo preço do Spot ou intermitência, o spot Request voltar para o início da jornada e quando tudo estiver ok ele deverá inicializar as configurações novamente.

Mesmo que a gente cancele uma Spot Request as suas instâncias ainda vão continuar no ambiente, pois é de sua responsabilidade para-lás.

Spot Fleets:

São um set de instâncias Spot + (opcional) instâncias on-demand.
O Spot Fleets vai tentar achar a melhor capacidade com algumas restrições.

Para utilizar o Spot Fleets devemos definir alguns tipos de instâncias, sistemas operacionais  e AZ, chamadas de launch pools.

Launch Pools:  é um conjunto de configurações onde podemos definir alguns tipos de instâncias, sistemas operacionais  e AZ e a partir disso o spot fleets tenta achar a melhor combinação.

O Fleets será responsável por escolher a melhor Launch Poll para você, ele também lhe permite definir alguns estratégias:
Lower Price: Escolha o Pool que tiver menor preço.
Diversified:  Distribuir através dos Pools.
Capacity Optimized:  Pool com ótima capacidade em relação aos números de instâncias.

Resumo:

Podemos usar o Spot Fleets para definir múltiplos launch Pools que são um conjunto de configurações onde podemos estipular o tipo de instância, sistema operacional e az, e com algumas regra do tipo, escolha o launch pool com menor preço, podemos utilizado do spot fleets da melhor forma.

Placement Groups:  é utilizado para aplicar estratégias nas nossas instâncias quando queremos ter controle de como as mesmas irão se comportar no ambiente AWS.
O que acontece é que nós geralmente não temos essa visão apenas utilizamos e a AWS orquestra por baixo, a ideia do placement Group é exatamente ter uma visibilidade de como essas instâncias vão se comportar e definir algumas estratégias.

Um ponto importante, é válido ressaltar que não vamos ter uma interação direta com o hardware, o que vai acontecer é que vamos deixar a AWS saber como nós gostaríamos que as nossas instâncias se comportassem em relação às outras.

Existem 3 tipos de estratégias para o placement Group:

Cluster: Suas instâncias vão permanecer em uma única zona de disponibilidade gerando uma baixa latência, isso nos dá uma performance muito alta e rede,  mas com um risco muito grande, pois se a zona de disponibilidade cair todas as instâncias consequentemente serão afetadas.

Prós:  Network muito boa, baixa latência.

Contra: Se o hardware falha, todas as instâncias falham ao mesmo tempo.

Use cases: Jobs que tem necessidade de ser muito rápido, aplicações que precisam de baixa latência e alto throughput.

Spread:  Significa que vocês desejam que suas instâncias sejam separadas em diferentes hardwares, no máximo 7 instâncias por azs, então cada az vai ter 7 instâncias mas separadas por hardware, se um hardware falhar o outro não será impactado. Muito boa estratégia para aplicações críticas, onde necessita de alta disponibilidade.

Prós:   Podemos usar múltiplas AZ reduzindo o risco de falha, pois se um AZ falha as outras não serão impactadas, e o mesmo se aplica às instâncias, pois mesmo numa mesma AZ e um hardware falha a outra não seria impactada.

Contra: Podemos ter apenas 7 instâncias por AZ.

Use cases: Aplicações que precisam aumentar a alta disponibilidade, Aplicações que precisam isolar as falhas das instâncias (aplicações críticas).

Partition:  São partições dentro de uma zona de disponibilidade que podem ser escaladas em até 100 instâncias, cada partição representa um hardware na AWS. Todas as instâncias em um partição não compartilham o hardware com outras partições. Uma falha em um partição pode afetar muitas instâncias mas não outras partições.

Use cases: Big data applications.




API Gateway:

É uma ferramenta de gerenciamento de APIS que fica entre o cliente e uma coleção de serviços de back-end, atuando como uma porta de entrada única para as APIS e os seus usuários.

Resumindo: É uma porta de entrada única para o consumo de APIS.

Suas principais funções são:

Autenticação.
Coletar métricas.
Transformação de resposta.
Limitação de conexões.
Logs de acesso.




EBS:  É um volume que pode ser anexado diretamente a uma instância enquanto ela ainda não está em execução.

Esse volume permite a persistência de dados, ou seja, se a instância for de alguma forma interrompida podemos anexar esse volume a outra instância e trabalhar com os dados persistidos.

Uma EBS deve estar na mesma Zona de Disponibilidade de uma instância.

Podemos mover os dados de um volume se fizermos um snapshot do mesmo e copiá-lo para outra zona de disponibilidade e a partir dessa cópia montar outro volume EBS.

Somos cobrados pela capacidade reservada.

Um EBS não pode ser anexado a duas instâncias ao mesmo tempo, mas uma instância pode ter mais que um EBS.

Por padrão o EBS root será sempre apagado se a instância não for mais utilizada.
Por padrão todos os outros volumes serão mantidos com suas persistências.


Snapshot: 
É um backup do volume.

Para fazer o backup de um volume não é necessário para a instância, mas é recomendado.
Podemos usar os Snapshot para transferir um volume de uma Zona de disponibilidade para a outra.


AIM:  É uma imagem customizada de uma instância.

Basicamente criamos uma imagem EC2 a partir das nossas próprias configurações, tornando mais rápido o boot pois todos os dados já estão previamente prontos, é só utilizar.

Conseguimos fazer a construção dessas imagens em uma região e copiá-la para outras.

Termos importantes:
Public AIM: São imagens disponibilizadas pela AWS.
Your own AIM: Suas imagens customizadas.
MarketPlace: Imagens de alguns provedores.

Qual a importância de se utilizar um AIM: A diminuição do bootstrapping, como todas as configurações padrões da sua empresa já estão definidas em uma única imagem, você pode criar suas aplicações a partir dela sem necessidade de instalar qualquer tipo de pré configuração (Em relação ao ambiente para a sua aplicação).
Resumindo, o boot da máquina se torna muito mais rápido uma vez que os softwares necessários já estão presentes no EC2.


EC2 Instance Store:  Um EBS tem uma performance um pouco limitada.

Quando estamos falando de uma performance muito alto, precisamos de um disco diretamente anexado a instância, quando se trata de I/O precisamos utlizar do Instance Store.

O problema desse tipo de armazenamento é porque ele é efêmero(passageiro).
Levando para um contexto mais técnico, se a instância for terminada por algum motivo os dados ali presente serão perdidos, não existe uma persistência.

Não devemos utilizar esse tipo de armazenamento em Workloads com um longo termo de compromisso. Você é o responsável por backup e replicação dos dados de acordo com as suas necessidades.


