### Cloud Computing
**O que é Cloud Computing?** São serviços de computação disponibilizados pela web e não mais fisicamente. Rodar meus serviços e produtos em algum lugar, onde eu consiga fornecer como plataforma, escalar de uma forma legal, ter elasticidade.

**Principais características e vantagens de uma cloud computing:** Agilidade: Facilidade e rapidez na implantação de serviços em nuvem, como EC2, por exemplo. Manutenção: Eliminação da necessidade de manter a infraestrutura física, como ar condicionado e energia; esta responsabilidade é assumida pela provedora de serviços.

**Confiabilidade:** A cloud aumenta a confiabilidade da infraestrutura, pois há equipes dedicadas aos produtos, sendo estes os produtos da provedora.

**Segurança:** Não é necessário se preocupar completamente com a segurança, especialmente com a infraestrutura física, uma vez que na plataforma existem vários recursos de segurança para proteger nossos produtos.

**Performance:** É possível alcançar um alto nível de desempenho na nuvem, mas com um custo, pois você paga conforme a demanda.

**Escalabilidade:** Vantagem de conseguir escalar suas aplicações de uma maneira muito fácil. A cloud te dá a possibilidade de escalar seus serviços sob demanda.

**Custo e elasticidade:** Você consegue gerenciar melhor seus custos na AWS, pagando sob demanda. Por exemplo, se eu ligar uma máquina e usá-la apenas por 24 horas, vou pagar somente por essas 24 horas. Existe a elasticidade, mas não é infinita; às vezes, há um limite flexível, por exemplo, um limite de 30 EC2 por mês ou rodando ao mesmo tempo. Se desejar aumentar, é necessário solicitar à AWS. Existe também o limite de hardware, que é o que o datacenter pode oferecer.

**Vantagens em se utilizar Cloud Computing:**
- Velocidade para implantação e desenvolvimento de soluções.
- Atualizações realizadas pela AWS sem interromper o serviço.
- Custo mais baixo em comparação com servidores físicos, com planos de fidelidade que oferecem descontos.
- Segurança de dados: os serviços são vendidos com sistema de backup incorporado.
- Escalabilidade: é possível configurá-la para ser automática e, se feita manualmente, é realizada em segundos.

**Modelos de cloud:**
- **IaaS (Infraestrutura como serviço):** Utilização de serviços como EC2 e bancos de dados rodando como serviço, disponibilizados por alguém no mercado.
- **PaaS (Plataforma como serviço):** Não é necessário saber o que está rodando por trás na infraestrutura; apenas deseja-se rodar o produto (por exemplo, Heroku).
- **FaaS (Function as a Service):** É um produto mais granular, uma única função que realiza uma única tarefa. Um exemplo na AWS é a Lambda.

**Modelo de deploy na cloud:**
- **Private Cloud:** Um cloud dentro da empresa, sob controle direto da organização. Por exemplo, uso da VMware ou on-premise.

- **Public Cloud:** Qualquer pessoa pode utilizar, exemplos incluem AWS, Google Cloud e Azure.

- **Hybrid Cloud:** Combinação de infraestrutura privada e pública, onde uma parte da infraestrutura roda internamente na empresa e outra parte é hospedada em um provedor de serviços de nuvem pública, como AWS.

- **Multicloud:** Execução de serviços em múltiplas plataformas de nuvem, eliminando a dependência de um único provedor de serviços. Por exemplo, utilizar serviços tanto da AWS quanto do Google Cloud, entre outros.


**Community Cloud:** Empresas se unem para construir uma nuvem que pode ser compartilhada por mais de uma organização. Funciona como um cloud privado, mas com a ideia de compartilhamento semelhante ao modelo público.

**Well-Architected:** É um conjunto de boas práticas e um framework para construir arquiteturas de nuvem robustas, seguras, resilientes, eficientes e de alta performance.

O Well-Architected possui 6 pilares:

1. **Excelência Operacional:** Para alcançar a excelência operacional, é crucial monitorar o sistema continuamente.

2. **Segurança:** Proteger todos os dados, sistemas e atividades dentro da estrutura de nuvem, utilizando recursos como security groups, bastion hosts, ACLs, AWS Key Management System e enfocando o uso do AWS IAM.

3. **Confiabilidade:** Aumentar a confiabilidade da topologia de nuvem, mantendo tudo funcionando mesmo em caso de falhas, implementando redundância, por exemplo, usando EC2s em múltiplas AZs e o Route53 com failover.

4. **Eficiência de Desempenho:** Significa utilizar recursos apenas na medida do necessário, por exemplo, usando auto scaling nas instâncias EC2 para economizar recursos sem comprometer a disponibilidade das aplicações.

5. **Otimização de Custos:** É necessário otimizar os custos e evitar gastos desnecessários, por exemplo, usando Reserved Instances nas instâncias EC2 para obter descontos com contratos de 1 ou 3 anos.

6. **Sustentabilidade:** Foca em reduzir o impacto ambiental, incluindo estratégias para reduzir as cargas de trabalho das aplicações, como o uso eficiente de instâncias EC2 e bancos de dados para economizar energia. Outro exemplo é utilizar regiões da AWS que utilizam energia renovável.

**AWS Cloud Adoption Framework (CAF):** É um framework ou guia que oferece um blueprint para migrar uma empresa para a nuvem, abordando aspectos como segurança, disponibilidade, entre outros, com base em melhores práticas e lições aprendidas na AWS com outras empresas.

Os benefícios de seguir o CAF incluem a redução de riscos comerciais, melhoria na performance ambiental, social e de governança, aumento da receita e maior eficiência operacional.

**Amazon EcoSystem:** É um sistema criado pela AWS para auxiliar seus clientes, oferecendo documentos, suporte e outros recursos. Inclui, por exemplo, um blog da AWS, fóruns, whitepapers e soluções de parceiros (empresas terceirizadas que desenvolvem soluções e as disponibilizam para outros clientes).

**AWS IQ:** É um serviço que permite concluir projetos relacionados à AWS. Você pode solicitar ajuda a especialistas da AWS e pagar pelo suporte, semelhante a uma plataforma de freelancers, mas integrada à AWS.

**Organizations:** Dentro das organizações, podemos criar as OU (unidades organizacionais) e aplicar políticas de controle de serviços (service control policies), que são políticas aplicadas às contas e organizações em um nível mais alto. Essas políticas têm listas de permissões (Allow) e negações (Deny), determinando quais serviços podem ou não ser executados.

## IAM

**IAM (Identity and Access Management):** É um serviço serverless que garante privilégios dentro da AWS, permitindo a criação de usuários, grupos, e assim por diante. É um serviço global e não restrito por regiões. Na AWS, aplicamos o princípio "princípio do menor privilégio: não conceda mais permissões do que o usuário precisa". Ele é usado para gerenciar usuários, definindo regras sobre o que eles podem ou não podem fazer dentro da conta AWS. Na Amazon, essencialmente tudo tem um ARN (Amazon Resource Name), que é usado para identificar um recurso. Por exemplo, você pode conceder acesso somente leitura (readonly) para todos os usuários de um grupo no EC2, mas acesso completo (fullAccess) a uma instância específica com um ARN específico no EC2.

**Roles:** Você pode criar uma role para agrupar várias políticas (policies). Por exemplo, uma role de somente leitura (readonly) no EC2 e RDS, onde você adicionaria políticas de somente leitura do EC2 e RDS dentro dessa role. As roles são usadas para conceder permissões a serviços que precisam acessar outros serviços dentro da AWS.

**Password Policy:** Você pode definir políticas de senha, como exigir senhas fortes e especificar o número mínimo de caracteres, tipos de caracteres (letras maiúsculas e/ou minúsculas, números, caracteres não alfanuméricos), permitir ou não a alteração da senha, exigir alterações periódicas de senha e não permitir o uso de senhas anteriormente utilizadas.

**IAM Best Practices:**
1. Não utilize a conta root, a menos que seja absolutamente necessário, e apenas para configurar a sua conta da AWS.
2. Crie usuários individuais para cada pessoa ou aplicativo que necessitar de acesso à sua conta, e nunca compartilhe suas credenciais de usuário.
3. Organize seus usuários em grupos e atribua permissões aos grupos em vez de indivíduos.
4. Estabeleça políticas de senha fortes e exija o uso de Autenticação Multifator (MFA) para todos os usuários.
5. Utilize roles para conceder permissões a serviços da AWS sempre que possível, em vez de usar chaves de acesso.
6. Faça uso do IAM Credentials Report e IAM Access Advisor para monitorar e auditar as permissões dos usuários e as chaves de acesso.
7. Nunca compartilhe chaves de acesso de usuário e credenciais de acesso.

**Shared Responsibility Model for IAM:**
- A AWS é responsável pela infraestrutura, configuração e análises de vulnerabilidades dos serviços.
- Você é responsável por criar seus próprios usuários, grupos, roles, policies, MFA nas contas, redefinir chaves de acesso regularmente, aplicar as permissões corretas e analisar e revisar os acessos e permissões.

## EC2

**O que é EC2?** É um serviço de servidores virtualizados (instâncias virtuais) com opções de processadores, armazenamento, redes, sistemas operacionais e modelos de compras para atender às suas necessidades. É uma das soluções mais populares da AWS e é classificada como IaaS. Você pode armazenar dados em EBS, distribuir cargas com o ELB e utilizar auto-scaling com o ASG.Quando criamos uma instância EC2, a opção "Delete on termination" do volume EBS adicionado vem marcada por padrão.

**Tipos de instâncias:** Existem vários tipos de instâncias, incluindo instâncias de uso geral, otimizadas para computação, memória, armazenamento, computação acelerada, entre outras. A convenção de nomenclatura dos tipos de instância é a seguinte: m5.2xlarge (m - classe da instância, 5 - geração do hardware que pode ser incrementada pela AWS, 2xlarge - tamanho da instância dentro da classe, 2 vezes o tamanho large).

**Security Groups:** Eles controlam o tráfego de entrada e saída da sua instância e só possuem regras de "allow". Eles podem referenciar IPs ou outros Security Groups. Funcionam como um firewall que regula o acesso às portas, faixas de IP, entrada e saída de rede da máquina. Se você mudar de região, precisará criar novamente os Security Groups. Por padrão, todo o tráfego de entrada é bloqueado e o tráfego de saída é permitido.

**Vantagens do EC2:**
- Controle completo sobre a instância, possibilitando ajustes de memória, processamento, etc.
- Segurança, pois o acesso à instância é feito por meio de chaves e a configuração de firewall pode ser realizada automaticamente durante a criação da instância.
- Integração com outros serviços da AWS, permitindo trabalhar facilmente com todo o ecossistema de serviços da AWS.
- Baixo custo de manutenção da máquina, proporcionando uma solução econômica.
- Facilidade e simplicidade na criação de instâncias EC2.

**EC2 Purchasing Options:**
- **On-Demand:** Ideal para trabalhos curtos e pago por segundo.
- **Instâncias Reservadas:** Indicadas para cargas de trabalho de longa duração, com contrato de 1 a 3 anos.
- **Instâncias Reservadas Flexíveis:** Para cargas de trabalho de longa duração, porém com tipos de instâncias flexíveis.
- **Planos Reservados (Saving Plans):** Para cargas de trabalho de longa duração, com planos de 1 a 3 anos em contrato com a AWS, oferecendo descontos.
- **Spot Instâncias:** Para cargas de trabalho menores e funcionam de forma similar a leilões.
- **Dedicated Hosts:** Máquinas físicas dedicadas.
- **Dedicated Instances:** Onde nenhum outro cliente utilizará o hardware.
- **Capacity Reservations:** Permite reservar capacidade em uma região por determinado tempo.

**Shared Responsibility Model for EC2:**
- A AWS será responsável pelos data centers, isolamento do host físico, troca de hardware com defeitos e garantia de conformidade.
- O usuário/cliente é responsável pelos grupos de segurança, atualizações de sistemas operacionais e patches de atualização, softwares e utilitários instalados no EC2, bem como pelas IAM Roles, acesso de usuários e segurança dos dados na instância.

**EBS Volume (Elastic Block Storage):** É uma unidade de armazenamento em bloco que você pode anexar à sua instância para persistir dados, mesmo que a instância seja terminada. É possível criar outra instância com o volume e os dados permanecerão intactos. No Certified Cloud Practitioner, o EBS só pode ser montado uma vez e, quando criado, é vinculado a uma zona de disponibilidade. Quando criamos uma instância, o primeiro volume vem com a opção "Delete on Termination" marcada, enquanto o próximo volume anexado vem desmarcado. Portanto, por padrão, o volume raiz é deletado quando a instância é terminada.

**AMI (Amazon Machine Image):** É a Amazon Machine Image, uma personalização de uma instância EC2.

**EC2 Image Builder:** É usado para automatizar a criação de máquinas virtuais ou imagens de contêineres. Você pode automatizar a criação, manutenção, validação e teste de AMIs do EC2. O fluxo de criação envolve criar uma instância EC2, em seguida,

**Shared Responsibility Model for Storage:**
- A AWS será responsável pelos data centers, isolamento do host físico, troca de hardware com defeitos, replicação dos dados de volumes do EBS e drivers do EFS, e garantir que os funcionários não acessem os dados.
- A responsabilidade do cliente inclui garantir backup/snapshot, configuração de criptografia de dados e responsabilidade pelos seus dados nos dispositivos.

**NFS (Network File System):** É um sistema de arquivos elástico de rede gerenciado, que pode ser montado em centenas de instâncias EC2 simultaneamente. É um sistema de arquivos compartilhado que funciona apenas em instâncias Linux EC2 e pode ser usado em várias zonas de disponibilidade ao mesmo tempo (por exemplo, us-east-1a, us-east-1b e us-east-1c). Ele oferece alta disponibilidade, escalabilidade e expansibilidade.

**Amazon FSx (File System):** É um serviço de alta performance para sistemas de arquivos na AWS. Ele fornece armazenamento de arquivos totalmente gerenciado e altamente escalável para cargas de trabalho sensíveis ao desempenho. Com o Amazon FSx, os usuários podem implantar sistemas de arquivos compatíveis com o Windows ou o Lustre, de acordo com suas necessidades. Ele oferece desempenho consistente e baixa latência, além de recursos avançados, como snapshots automatizados, backups e integração com serviços da AWS, como IAM e CloudWatch. O Amazon FSx simplifica a implantação e a gestão de sistemas de arquivos, permitindo que os usuários se concentrem em suas aplicações, enquanto a AWS cuida da infraestrutura subjacente.

## S3

**AWS S3 (Amazon Simple Storage Service):** É um dos principais blocos de construção da AWS, anunciado como um bloco infinito de armazenamento. O S3 armazena dados em "buckets", que podem ser vistos como diretórios de alto nível, e os arquivos salvos nesses "buckets" são chamados de objetos. Os "buckets" criados precisam ter nomes globais únicos e são definidos em nível regional. Existe uma convenção para criação dos nomes: sem letras maiúsculas, sem underscores, de 3 a 63 caracteres, não pode ser um endereço IP e deve começar com um número ou letra minúscula.

**Casos de Uso do AWS S3 (Amazon Simple Storage Service):**
- Backup e armazenamento
- Recuperação de desastres
- Arquivamento
- Armazenamento em nuvem híbrida
- Hospedagem de aplicativos
- Armazenamento de mídia
- Data Lakes
- Entrega de software
- Sites estáticos

**Objetos do AWS S3 (Amazon Simple Storage Service):**
Cada objeto possui uma chave (key), que é o caminho completo do arquivo, por exemplo: `s3://my-bucket/my-file.txt` ou `s3://my-bucket/another_folder/my_file.txt`. O tamanho máximo de um objeto é 5TB (5000GB).

**Segurança do AWS S3 (Amazon Simple Storage Service):**
- A primeira parte é baseada em IAM Roles, especificando políticas para os usuários.
- A segunda parte é baseada em recursos, onde podem ser usadas políticas diretamente no bucket através das bucket policies, bem como o Controle de Acesso a Objetos (ACL) com granularidade mais fina e o Controle de Acesso ao Bucket (ACL).
- A terceira parte envolve o uso de criptografia.

**Bucket Policies:** São políticas baseadas em JSON.

**S3 Website Hosting:** O S3 pode ser utilizado para hospedar sites estáticos. A URL de acesso ao site hospedado no S3 segue o formato: `http://bucket-name.s3-website.aws-region.amazonaws.com`. Para indicar que o bucket vai hospedar um site estático, é necessário configurar as opções de hospedagem do site no próprio bucket.

**S3 Versioning:** É possível ativar o versionamento em seu bucket no S3, o que significa que sempre que um objeto for carregado, uma nova versão será criada. Qualquer arquivo existente antes da ativação do versionamento terá a versão "null".

**S3 Replication:** Na replicação, temos a CRR (Cross-Region Replication) para replicação entre regiões e a SRR (Same-Region Replication) para replicação dentro da mesma região.

**S3 Storage Classes:**
- **Amazon S3 Standard - General Purpose:** Usado quando os dados são acessados frequentemente, com baixa latência e altas taxas de transferência.
- **Amazon S3 Standard-Infrequent Access (IA):** Usado para dados que serão acessados com menos frequência, com custo menor que o Standard.
- **Amazon S3 One Zone-Infrequent Access:** Dados acessados com pouca frequência, mas armazenados em uma única zona.
- **Amazon S3 Glacier Instant Retrieval:** Destinado a backup e armazenamento de baixo custo, com cobrança por armazenamento e recuperação de dados. Permite acesso rápido aos dados.
- **Amazon S3 Glacier Flexible Retrieval:** Oferece flexibilidade na recuperação dos dados.
- **Amazon S3 Glacier Deep Archive:** Usado para guardar dados como backup, mas o tempo de recuperação dos dados é de 12 a 48 horas.
- **Amazon S3 Glacier Intelligent Tiering:** Permite mover os dados entre os tipos com base no acesso aos dados.

**S3 Encryption:** A primeira criptografia é a server-side (default), e existe a criptografia pelo cliente, mas é opcional, sendo feita antes do upload.

**S3 Transfer Acceleration:** É uma solução para transferir grandes volumes de dados por longas distâncias (para buckets S3 em locais distantes), maximizando a velocidade de transferência de dados para melhorar o desempenho e a eficiência.

**Shared Responsibility Model for S3:**
- A AWS será responsável por toda a infraestrutura, configurações, análise de vulnerabilidades e conformidade.
- O cliente será responsável pelas políticas no bucket, versionamento, configuração da replicação, logs e monitoramento, classes de armazenamento e, por fim, pela criptografia dos dados.

**AWS Snow Family:** Usado para migração de dados para dentro ou fora da AWS de maneira muito segura e portátil.

**Storage Gateway Overview:** Ele permite que você conecte sua infraestrutura on-premise com a nuvem, aumentando sua capacidade de armazenamento.

## Database

**AWS RDS:** O significado de RDS é Relational Database Service. No RDS, a proteção contra exclusão vem marcada por padrão, mas você pode desmarcá-la durante a criação. Você também tem a opção de instâncias reservadas no RDS.

**Elastic Cache:** É um sistema de cache que utiliza memória. Os datastores que ele pode usar são o Redis e o Memcached.

**Amazon Neptune:** É usado para dados com conexões (o diagrama é parecido com uma rede neural), sendo especialmente útil para redes sociais.

## Serverless

**AWS Lambda**: É um serviço que executa um trecho de código baseado em um evento configurado e gerencia automaticamente os recursos necessários para executar a função.

**AWS Lambda Pricing**: O modelo de cobrança é por requisições (a cada 1 milhão) e também por memória x tempo de execução.

**AWS API Gateway**: É uma tecnologia serverless que faz o proxy das chamadas HTTPS para serviços dentro da AWS. Você pode gerenciar sua API, criá-la, publicá-la e mantê-la. Caso deseje criar uma API serverless sem servidor, você pode usá-la em conjunto com o Lambda.

**AWS Batch**: É um serviço de processamento em lote. Você pode criar instâncias (EC2) em lote com horário de início e fim para executar trabalhos.

**Amazon Lightsail**: O Amazon Lightsail é um serviço ideal para quem está começando na computação em nuvem, oferecendo servidores virtuais privados (VPS), armazenamento, bancos de dados, redes e balanceamento de carga a um custo acessível, sendo ideal para pequenas empresas, desenvolvedores e estudantes.

**Amazon ECS**: É o serviço Elastic Container Service, usado para lançar containers Docker na AWS. Você pode provisionar e manter a infraestrutura.

**Fargate**: É usado para iniciar containers Docker na AWS sem a necessidade de provisionar a infraestrutura. Basicamente, é um serviço serverless para contêineres que permite executar suas aplicações sem ter que gerenciar a infraestrutura subjacente.

**ECR**: É o Elastic Container Registry, usado para armazenar imagens Docker, Open Container Initiative (OCI) e Helm na AWS, que são executados pelo ECS ou Fargate.

**EKS**: É o Elastic Kubernetes Service, oferecendo uma maneira poderosa, segura e escalável de executar aplicativos baseados em contêineres na AWS, utilizando as vantagens do Kubernetes para orquestração de contêineres.

**API Gateway**: É um serviço de criação, publicação, manutenção e monitoramento/proteção das APIs REST e Websocket.

## VPC


**IPS**: 192.168.1.0/24. No 255, temos um octeto (128, 64, 32, 16, 8, 4, 2, 1). Para transformar o 255 em binário, é só substituir os números por 1 se estiverem ativos ou não, sendo ativo se os valores que são somados resultarem em 255. Na soma de todos os ativos do 255, que é 0 ou 1, temos a soma do /24. No IP 10.0.0.0, o CIDR dele será /8, porque só a soma dos ativos resultará em 10, o restante é desativo, ou seja, igual a 0. Os bits ligados referem-se à rede, enquanto os bits desligados referem-se aos hosts. No 10.0.0.0/8, apenas o 10 é referente à rede, enquanto o restante é referente aos hosts, portanto, teremos 3 octetos para trabalhar com IPs, proporcionando mais opções de hosts. O broadcast da rede do IP 10.0.0.0 seria 10.255.255.255. 255.255.255.0 é uma máscara de rede.

**Amazon VPC (Virtual Private Cloud)**: É uma rede virtual totalmente dedicada para a sua conta. O VPC fica dentro de uma região (por exemplo, eu-central-1) e dentro do VPC temos subnets que podem ser criadas como públicas ou privadas. Para ter comunicação a partir da internet com as VPCs, precisamos ter um Internet Gateway. Temos uma rota gateway com a tabela de rotas para mapear os IPs para as subnets. A partir das tabelas de rotas, temos as ACLs para controlar se temos acessos ou não às nossas subnets. Você pode ter no máximo 5 VPCs por região e 200 subnets por VPC, além de 5 Elastic IPs por região.

**NAT**: Temos o NAT Gateway e o NAT Instance. O NAT Instance não é recomendado porque normalmente só temos uma única instância rodando, não há preocupação com alta disponibilidade, tamanho etc. O NAT Gateway, por outro lado, é um serviço com alta disponibilidade. Quando um usuário no sistema tenta acessar a internet, ele possui um IP privado, mas precisa de um IP público. Ele passa pelo gateway e é atribuído um IP público. Resumindo: quando temos uma máquina em uma rede privada, não temos acesso à internet. O NAT Gateway e o NAT Instance são utilizados para acessar a internet a partir de nossa rede privada, utilizando o IP fornecido pelo NAT.

**NACL (Network ACLs)**: É uma lista que permite tudo o que passa e na última linha bloqueia tudo. Funciona como um firewall para a sub-rede. Ela executa a lista de regras de cima para baixo e, quando há um match, para de ler as próximas regras.

**VPC Peering**: Quando temos duas VPCs e queremos que os recursos dentro se comuniquem com a outra VPC. Por padrão, isso não é permitido, mas podemos permitir ativando o VPC Peering.

**AWS VPC Endpoints**: Por exemplo, quando nosso EC2 faz um upload no bucket, ele sai da rede da AWS, passa pela internet e volta para o S3. Para corrigir isso, criamos os VPC Endpoints. Existem 2 tipos: gateway (usado para os serviços de S3 e DynamoDB) e interface (para outros serviços).

**VPC Flow Logs**: Você pode ativá-lo para ver os logs de fluxo em sua VPC, podendo configurar logs de entrada, saída e rejeitados, ou pode ativar todos os tipos.

**AWS PrivateLink**: Quando uma empresa quer vender um serviço para outras empresas, como um serviço que monitora as instâncias EC2, ela tem uma VPC com um Network Load Balancer e a aponta para uma Elastic Network Interface da empresa cliente. Você configura um AWS PrivateLink porque não precisa configurar Internet Gateway, Route Table, ACLs etc., porque você criará um link direto, seguro e escalável com a VPC do seu cliente.

**AWS Direct Connect**: É um link de conexão direto com a AWS.

**AWS Transit Gateway**: Por exemplo, se tivermos 3 a 4 VPCs, fica complexo conectar via Peering. O Transit Gateway é ideal para isso. É como se fosse um sistema central e, em vez de ficar conectando uma VPC com a outra via Peering, você conecta as VPCs ao Transit Gateway e configura para elas se conhecerem e se conectarem. É conhecido como uma arquitetura HUB-AND-SPOKE. Se você tiver um servidor on-premise, você pode conectá-lo ao Transit Gateway via Direct Connect ou Site-to-Site VPN.

**VPN**: É uma forma de conectar minha rede com a VPC da AWS. A Client-to-Site conecta do seu computador para a VPC e a Site-to-Site são duas redes que precisam ser conectadas. Customer Gateways é Site-to-Site.

## Auto Scaling and Load Balancing (ELB - Elastic Load Balancing)

**Load Balancing**: É basicamente um IP que redireciona as requisições para o meu pool de servidores. Temos 3 tipos de load balancer: Application Load Balancer (usado para protocolos HTTP e HTTPS, camada 7), Network Load Balancer (usado para conexões TCP e UDP, camada 4) e Gateway Load Balancer (usado para balanceamento de carga de dispositivos virtuais de terceiros). Um detalhe sobre o Network Load Balancer é que ele é usado em aplicações que precisam de alta performance e baixa latência.

**Escalabilidade**: Existem dois tipos (vertical e horizontal). A escalabilidade vertical envolve aumentar o tipo de instância, por exemplo, de uma EC2 t2.micro para t2.2xlarge, enquanto a escalabilidade horizontal envolve aumentar o número de instâncias.

**Elasticidade**: Elasticidade é a capacidade do sistema de se adaptar automaticamente às mudanças na carga. Por exemplo, se um servidor estiver sobrecarregado, o sistema redirecionará as requisições para outro servidor. Se todos estiverem sobrecarregados, ele criará um novo servidor para atender à demanda, e se não houver mais demanda, ele encerrará os servidores extras. Isso é semelhante à escalabilidade horizontal.

**Alta Disponibilidade**: Basicamente, os servidores devem estar sempre disponíveis. Isso pode ser alcançado usando várias zonas de disponibilidade, garantindo que, se uma cair, haverá outra zona para manter o serviço disponível.

**Auto Scaling**: O auto scaling aumenta ou diminui o número de instâncias de forma inteligente, com base em parâmetros como CPU, quantidade de requisições, rede (entrada e saída de bytes), etc. Geralmente, existem 2 tipos: scaling up/down, que adiciona ou remove recursos adicionais, como memória e espaço em disco, e scaling in/out, que adiciona ou remove instâncias adicionais, de acordo com a necessidade e pode aumentar ou diminuir a quantidade de instâncias. O scaling up/down aumenta ou diminui os recursos de forma vertical, enquanto o scaling in/out adiciona ou remove instâncias de forma horizontal.

## Route 53

**Route 53:** Basicamente ele é o servico de DNS da AWS.

**Route 53 Policies**: A vantagem do Route 53 para outros servicos são as policies, existe algumas policies como a simple routing, failover, geolocation, geopromixity, latency, ip-based, multivalue weighted.

## AWS CloudFront

**AWS CloudFront:** É um serviço de CDN (Content Delivery Network) rápido e altamente seguro. Resumidamente, é uma solução de CDN segura, escalável e de alto desempenho que melhora a experiência do usuário, acelerando a entrega de conteúdo, enquanto protege suas aplicações contra ameaças.

## AWS Global Accelerator

**AWS Global Accelerator:** É uma solução para melhorar a velocidade, disponibilidade e a segurança das aplicações na AWS. Sua escalabilidade é automática e direciona os usuários para a instância mais saudável da aplicação, resultando em um desempenho aprimorado com baixa latência.

## AWS Kinesis

**AWS Kinesis:** É um serviço de stream de dados em tempo real. Por exemplo, em aplicações de IoT, onde é necessário capturar e analisar dados em tempo real, o Kinesis Streams captura os dados, a análise pode ser feita pelo Kinesis Analytics e, posteriormente, os dados podem ser enviados para algum destino usando o Kinesis Firehose.

## AWS SQS

**AWS SQS (Simple Queue Service):** É um serviço de filas da AWS que pode ser integrado com outros serviços da AWS, como Lambda, entre outros. Quando os serviços recebem uma mensagem do SQS, eles recebem uma cópia da mensagem. As mensagens são armazenadas por um período de tempo configurado no serviço.

## AWS SNS

**AWS SNS (Simple Notification Service):** É um serviço para notificar ações na AWS. Ao contrário do SQS, o SNS não armazena as mensagens. Ele funciona com a ideia de tópicos e assinantes, onde você cria um tópico e vincula assinantes a ele para receberem notificações.

## AWS Service Catalog

**AWS Service Catalog:** É um serviço de gerenciamento de serviços que permite que organizações criem e gerenciem catálogos de serviços de TI aprovados para uso na AWS. É uma solução ideal para organizações que precisam manter um controle rigoroso sobre o uso dos serviços da AWS, ao mesmo tempo em que permitem que os usuários acessem e lancem os serviços de que precisam de forma autônoma.

## Machine Learning

**Amazon Transcribe:** É um serviço que converte fala para texto, utilizando um sistema ASR (automatic speech recognition). Funciona em várias línguas e não exibe detalhes de informações pessoais.

**Amazon Rekognition:** É um serviço que reconhece o conteúdo de imagens, vídeos, textos e outros elementos, identificando pessoas, textos e objetos em uma imagem. É ideal para moderação de documentos e chats, leitura de placas de carros, identificação de rostos, entre outros.

**Amazon Translate:** É o serviço da AWS para realizar traduções de textos.

**Amazon Polly:** Você envia um texto para a AWS e ele realiza a leitura do conteúdo utilizando a caixa de som da sua máquina, utilizando deep learning.

**Amazon Comprehend:** É um serviço serverless que tenta compreender o conteúdo de textos, utilizando NLP (Processamento de Linguagem Natural). É ideal para serviços que precisam extrair informações de textos e entender o contexto das frases.

**Amazon Lex:** É o sistema de linguagem utilizado na Alexa. Ele utiliza ASR (Reconhecimento Automático de Voz) para converter fala em texto e NLU (Entendimento de Linguagem Natural) para compreender as intenções do usuário.

**Amazon Kendra:** É um serviço que permite conectar vários tipos de fontes de dados, como buckets, bancos de dados, SharePoint, Salesforce, OneDrive, Google Drive, etc. Ele aprende com essas fontes e pode ser integrado a uma interface web com um chat, respondendo a perguntas dos usuários com base nas informações aprendidas.

**Amazon Textract:** Utilizado para extrair textos de imagens, fornecendo uma imagem e gerando um arquivo JSON com o texto extraído.

**Amazon SageMaker:** É utilizado por cientistas de dados ou desenvolvedores para criar modelos de machine learning/AI.

**Amazon Forecast:** É um serviço gerenciado da AWS que utiliza machine learning para fazer previsões altamente precisas, sendo utilizado em planejamento financeiro, entre outras áreas.

**Amazon Personalize:** É um serviço que utiliza machine learning para construir aplicativos com recomendações personalizadas em tempo real.

## Amazon Cognito

**Amazon Cognito:** É um serviço de autenticação para suas aplicações utilizando a AWS. Ele permite trabalhar com o SIP (Social Identity Provider).

## Amazon STS

**Amazon Security Token Service:** É um serviço para gerar, criar e gerenciar tokens de acesso.

## AWS Device Farm

**AWS Device Farm:** É um serviço específico para desenvolvedores que precisam testar suas aplicações em dispositivos diversos. O Device Farm realiza testes em diversos navegadores e tamanhos de tela, fornecendo relatórios detalhados sobre quais dispositivos funcionaram corretamente e quais não. É uma ferramenta essencial para garantir a compatibilidade e a qualidade das aplicações em uma ampla variedade de dispositivos.

## AWS AppSync

**AWS AppSync:** É um serviço ideal para aplicativos que necessitam de sincronização de dados entre plataformas, como aplicações web e móveis. Utilizando a tecnologia GraphQL, o AppSync permite que você defina um único ponto de acesso para seus dados, simplificando a comunicação entre os clientes e os serviços back-end. Com o AppSync, as atualizações feitas em uma plataforma são automaticamente refletidas em todas as outras, garantindo consistência e sincronização em tempo real.


## AWS Amplify

## AWS IoT Core

**AWS IoT Core (Internet of Things):** É um serviço serverless projetado para conectar e gerenciar dispositivos IoT (Internet of Things) na nuvem da AWS. Com o AWS IoT Core, você pode facilmente coletar dados de dispositivos conectados e interagir com eles usando uma variedade de serviços da AWS, como S3, SageMaker, Lambda, DynamoDB, CloudWatch, entre outros. Ele fornece recursos robustos de segurança e escalabilidade para lidar com grandes volumes de dados de dispositivos IoT, facilitando o desenvolvimento de soluções IoT escaláveis e seguras.


## AWS Step Functions

**AWS Step Functions:** É um serviço que permite coordenar e orquestrar fluxos de trabalho distribuídos e baseados em eventos na nuvem da AWS. Com o AWS Step Functions, você pode definir e gerenciar facilmente fluxos de trabalho complexos que envolvem a execução sequencial ou paralela de várias funções ou etapas. Ele permite criar workflows altamente escaláveis e resilientes, garantindo que as etapas sejam executadas na ordem correta e lidando automaticamente com erros e falhas. Os Parallel States permitem que duas ou mais etapas sejam executadas simultaneamente, enquanto o Sequence garante que as etapas sejam executadas em sequência.

## AWS Backup

**AWS Backup:** É um serviço centralizado da AWS projetado para facilitar o backup e a restauração de dados em vários serviços da AWS, incluindo Amazon EBS, Amazon RDS, Amazon DynamoDB, Amazon EFS, Amazon EC2, AWS Storage Gateway e AWS Fargate. Com o AWS Backup, os usuários podem configurar políticas de backup de forma simples e gerenciar faci


## AWS Disaster Recovery Strategy (DR)

**AWS Disaster Recovery Strategy:**
Um conjunto de estratégias e procedimentos implementados na AWS para proteger os dados e sistemas de uma organização contra desastres. Essas soluções são projetadas para minimizar o tempo de inatividade e a perda de dados em caso de falhas graves. Alguns dos serviços utilizados para implementar essa estratégia incluem:

- **AWS Backup:** Para realizar backups automatizados e gerenciar a recuperação de dados.
- **Amazon S3:** Para armazenamento seguro e durável de dados, incluindo backups e arquivos importantes.
- **Amazon EBS Snapshots:** Para criar snapshots dos volumes EBS, permitindo a recuperação rápida de instâncias EC2.
- **Amazon RDS:** Para backups automatizados de bancos de dados e recuperação de instâncias de banco de dados.
- **AWS CloudFormation:** Para automatizar a implantação e a configuração de infraestrutura em caso de falha.
- **Amazon Route 53:** Para roteamento de tráfego de DNS com failover automático em caso de interrupções.
- **AWS Direct Connect:** Para conexões de rede dedicadas entre data centers locais e a infraestrutura da AWS, garantindo conectividade confiável em situações de desastre.

Esses serviços combinados fornecem uma abordagem abrangente para garantir a resiliência dos sistemas e dados da organização na AWS, ajudando a manter a continuidade dos negócios mesmo diante de eventos adversos.

## AWS WorkSpaces

**AWS WorkSpaces:**
É um serviço gerenciado de Desktops como Serviço (DaaS) oferecido pela AWS. Ele permite provisionar desktops virtuais na nuvem para os usuários acessarem remotamente. Ao contrário dos desktops tradicionais, onde os dados são armazenados localmente nos dispositivos físicos dos usuários, no AWS WorkSpaces, os dados são armazenados de forma segura na infraestrutura da AWS.

Principais recursos e benefícios do AWS WorkSpaces:

- **Provisionamento Simples:** É fácil provisionar e gerenciar desktops virtuais para os usuários, utilizando a console da AWS ou APIs.

- **Acesso Remoto Seguro:** Os usuários podem acessar seus desktops a partir de qualquer dispositivo compatível com a internet, mantendo a segurança dos dados na nuvem.

- **Escalabilidade:** O AWS WorkSpaces permite escalar verticalmente ou horizontalmente de acordo com as necessidades da organização, adicionando ou removendo desktops conforme necessário.

- **Gerenciamento Centralizado:** Todos os desktops virtuais podem ser gerenciados centralmente pela equipe de TI, incluindo a aplicação de políticas de segurança, atualizações de software e monitoramento de desempenho.

- **Backup e Recuperação:** Os dados armazenados nos desktops virtuais são automaticamente copiados e podem ser facilmente restaurados em caso de perda de dados ou falhas.

- **Compatibilidade:** É compatível com uma variedade de aplicativos e sistemas operacionais, oferecendo uma experiência de usuário familiar e consistente.

O AWS WorkSpaces é uma solução flexível e segura para organizações que desejam oferecer desktops virtuais para seus funcionários, eliminando a necessidade de gerenciar hardware localmente e garantindo acesso remoto seguro aos recursos da empresa.

## AWS AppStream 2.0

**Amazon AppStream 2.0:**
É um serviço gerenciado pela AWS que oferece streaming seguro de aplicativos desktop para usuários, sem a necessidade de reescrever esses aplicativos para a nuvem. Em vez disso, os aplicativos são executados em instâncias na nuvem e a interface gráfica é transmitida para os dispositivos dos usuários por meio de um navegador da web.

Principais recursos e benefícios do Amazon AppStream 2.0:

- **Acesso Instantâneo:** Os usuários podem acessar instantaneamente aplicativos desktop, independentemente da localização ou do dispositivo utilizado, bastando ter um navegador da web e uma conexão com a internet.

- **Compatibilidade com Dispositivos:** O serviço é compatível com uma ampla variedade de dispositivos, incluindo laptops, tablets e smartphones, permitindo aos usuários acessar os aplicativos de onde estiverem.

- **Segurança Avançada:** O Amazon AppStream 2.0 utiliza criptografia de ponta a ponta e oferece controle granular sobre o acesso aos aplicativos, garantindo a segurança dos dados corporativos.

- **Escala Automática:** Ele pode escalar automaticamente para atender à demanda dos usuários, aumentando ou reduzindo o número de instâncias de acordo com a carga de trabalho.

- **Gerenciamento Centralizado:** Os administradores podem gerenciar centralmente os aplicativos, usuários e políticas de acesso por meio da console da AWS, facilitando a implantação e o gerenciamento.

- **Economia de Custos:** Como os aplicativos são executados em instâncias compartilhadas, o Amazon AppStream 2.0 ajuda a reduzir os custos operacionais e de infraestrutura, em comparação com a implantação tradicional de aplicativos desktop.

O Amazon AppStream 2.0 é uma solução eficiente e econômica para fornecer acesso a aplicativos desktop para usuários finais, eliminando a necessidade de instalação e manutenção local de software, ao mesmo tempo em que oferece uma experiência de usuário rica e consistente.


## Aplication Compose

**Application Composer:**
É um serviço que permite montar sua infraestrutura na AWS de forma visual e intuitiva, utilizando a interface de arrastar e soltar para conectar e configurar os serviços desejados. Com o Application Composer, os usuários podem criar rapidamente arquiteturas de aplicativos complexos sem a necessidade de escrever código manualmente.

Principais recursos e benefícios do Application Composer:

- **Interface Gráfica Intuitiva:** O serviço oferece uma interface de usuário visual e intuitiva, onde os usuários podem selecionar os serviços AWS desejados e conectá-los facilmente, arrastando e soltando componentes na tela.

- **Construção Rápida de Arquiteturas:** Com o Application Composer, é possível montar arquiteturas de aplicativos de forma rápida e eficiente, economizando tempo e esforço no processo de desenvolvimento.

- **Facilidade de Conexão entre Serviços:** Os usuários podem facilmente conectar os serviços entre si, definindo as dependências e configurações necessárias através de uma interface gráfica intuitiva.

- **Visualização da Arquitetura:** O serviço fornece uma visualização clara da arquitetura do aplicativo, permitindo que os usuários entendam facilmente como os diferentes componentes estão interconectados.

- **Integração com o CloudFormation:** Uma vez que a arquitetura do aplicativo tenha sido montada no Application Composer, os usuários podem gerar automaticamente o código CloudFormation correspondente, facilitando a implantação e o gerenciamento da infraestrutura como código.

- **Colaboração em Equipe:** O Application Composer suporta a colaboração em equipe, permitindo que vários usuários trabalhem juntos na construção e revisão da arquitetura do aplicativo.

O Application Composer é uma ferramenta poderosa para projetar e montar arquiteturas de aplicativos na AWS, oferecendo uma abordagem visual e intuitiva para o desenvolvimento de infraestrutura como código.

## AWS Elastic Disaster Recovery (DRS)

**AWS Elastic Disaster Recovery (DRS):**
O AWS Elastic Disaster Recovery (DRS) é um serviço que oferece uma solução elástica e altamente eficaz para recuperação de desastres na nuvem AWS. Ele permite que as organizações recuperem seus servidores físicos, virtuais e baseados na nuvem com maior velocidade e facilidade, garantindo a continuidade dos negócios em caso de incidentes graves.

Principais recursos e benefícios do AWS Elastic Disaster Recovery (DRS):

- **Recuperação Rápida:** Com o DRS, as organizações podem recuperar rapidamente seus servidores em caso de desastre, minimizando o tempo de inatividade e o impacto nos negócios.

- **Elasticidade e Escalabilidade:** O serviço oferece elasticidade e escalabilidade para lidar com cargas de trabalho variáveis e demandas de recuperação de desastres em larga escala.

- **Integração com Serviços AWS:** O DRS é integrado com os serviços AWS, permitindo a recuperação de servidores em diferentes regiões e zonas de disponibilidade para garantir alta disponibilidade e redundância.

- **Automação de Processos:** O DRS utiliza automação para simplificar e acelerar o processo de recuperação de desastres, reduzindo a necessidade de intervenção manual e a possibilidade de erros.

- **Monitoramento e Gerenciamento Centralizado:** O serviço oferece recursos avançados de monitoramento e gerenciamento centralizado para acompanhar o status da recuperação de desastres e tomar medidas proativas para resolver quaisquer problemas.

- **Segurança e Conformidade:** O DRS é projetado com recursos avançados de segurança e conformidade para proteger os dados e garantir a conformidade com regulamentações e padrões de segurança.

- **Custo-Efetividade:** O serviço é altamente custo-efetivo, permitindo que as organizações paguem apenas pelos recursos consumidos durante a recuperação de desastres, sem custos adicionais.

O AWS Elastic Disaster Recovery (DRS) oferece uma solução abrangente e altamente eficaz para recuperação de desastres na nuvem AWS, garantindo que as organizações estejam preparadas para lidar com qualquer cenário de interrupção de negócios.

## AWS Migration Evaluator

**AWS Migration Evaluator:**
O AWS Migration Evaluator é um serviço projetado para ajudar as organizações a criar um caso de negócios baseado em dados para migrações para a AWS (Amazon Web Services). Ele oferece uma abordagem abrangente e baseada em análises para avaliar a viabilidade e os benefícios de migrar cargas de trabalho para a nuvem AWS.

Principais recursos e benefícios do AWS Migration Evaluator:

- **Análise de Infraestrutura Atual:** O serviço instala um agente na infraestrutura existente da organização para coletar dados e métricas detalhadas sobre as cargas de trabalho, dependências, desempenho e utilização dos recursos.

- **Snapshot das Dependências:** O AWS Migration Evaluator tira um "snapshot" das dependências das cargas de trabalho, identificando as conexões e interdependências entre os sistemas, aplicativos e serviços em execução na infraestrutura existente.

- **Análise de Status Atual:** Com base nos dados coletados, o serviço realiza uma análise detalhada do status atual da infraestrutura, identificando pontos fortes, vulnerabilidades, gargalos de desempenho e áreas de melhoria.

- **Definição de Estados Futuros:** O AWS Migration Evaluator ajuda a definir estados futuros desejados para a infraestrutura na nuvem AWS, considerando objetivos de negócios, requisitos de desempenho, segurança e conformidade.

- **Plano de Migração Personalizado:** Com base na análise dos dados e requisitos específicos da organização, o serviço desenvolve um plano de migração personalizado, detalhando os passos necessários, cronogramas, custos estimados e benefícios esperados da migração para a AWS.

- **Caso de Negócio Orientado por Dados:** O AWS Migration Evaluator fornece informações precisas e baseadas em dados para criar um caso de negócio sólido e convincente para a migração para a AWS, destacando os potenciais ganhos em termos de custo, desempenho, escalabilidade, segurança e agilidade.

- **Suporte à Tomada de Decisão:** Ao oferecer insights valiosos e análises detalhadas, o serviço ajuda as organizações a tomar decisões informadas e estratégicas sobre suas iniciativas de migração para a nuvem AWS.

O AWS Migration Evaluator é uma ferramenta poderosa e abrangente para avaliar e planejar migrações para a AWS, permitindo que as organizações maximizem os benefícios da nuvem e alcancem seus objetivos de negócios com sucesso.

## AWS Migration HUB

**AWS Migration Hub:**
O AWS Migration Hub é um serviço centralizado oferecido pela Amazon Web Services (AWS) que permite coletar, organizar e gerenciar informações sobre servidores e aplicativos durante o processo de migração para a nuvem AWS. Ele fornece uma plataforma unificada para avaliação, planejamento e rastreamento de migrações, ajudando as organizações a simplificar e gerenciar com eficiência o processo de migração para a nuvem.

Principais recursos e benefícios do AWS Migration Hub:

- **Centralização das Informações:** O Migration Hub oferece um local centralizado para coletar e armazenar informações sobre servidores e aplicativos que estão sendo migrados para a AWS. Isso facilita o acesso e a visualização de dados relevantes em um único painel.

- **Avaliação de Migração:** O serviço permite avaliar a viabilidade e os requisitos de migração para cada servidor e aplicativo, incluindo compatibilidade, dependências, custos estimados e planejamento de recursos.

- **Planejamento de Migração:** Com base nas informações coletadas, o Migration Hub ajuda na elaboração de planos de migração detalhados, definindo cronogramas, tarefas, recursos necessários e estimativas de custo para cada fase do processo de migração.

- **Rastreamento de Progresso:** Durante a migração, o Migration Hub fornece ferramentas para rastrear o progresso em tempo real, monitorar o status de cada servidor e aplicativo migrado e identificar quaisquer problemas ou desafios que surjam ao longo do caminho.

- **Integração com Ferramentas de Migração:** O Migration Hub é integrado com uma variedade de ferramentas de migração da AWS e de terceiros, permitindo uma migração mais fácil e eficiente de servidores e aplicativos para a nuvem AWS.

- **Visibilidade e Transparência:** Ao oferecer uma visão abrangente e transparente do processo de migração, o Migration Hub ajuda as equipes de TI e os stakeholders a entenderem o status e o impacto da migração em tempo real.

- **Suporte à Tomada de Decisões:** Com base nos dados coletados e nas análises fornecidas pelo Migration Hub, as organizações podem tomar decisões informadas e estratégicas sobre suas iniciativas de migração para a nuvem AWS, garantindo uma migração bem-sucedida e sem problemas.

O AWS Migration Hub é uma ferramenta essencial para organizações que estão migrando para a nuvem AWS, oferecendo recursos abrangentes para simplificar, planejar e gerenciar eficientemente o processo de migração.

## AWS Fault Injection Simulator (FIS)

**AWS Fault Injection Simulator (FIS):**
O AWS Fault Injection Simulator (FIS) é um serviço fornecido pela Amazon Web Services (AWS) que permite aos usuários realizar experimentos de injeção de falhas em suas cargas de trabalho na nuvem. Baseado na prática de engenharia do CAOS (Chaos Engineering), o FIS permite simular e avaliar o comportamento de sistemas e aplicativos sob condições de falha controladas, permitindo que as organizações identifiquem e corrijam vulnerabilidades e aumentem a resiliência de suas arquiteturas na nuvem.

Principais recursos e benefícios do AWS Fault Injection Simulator:

- **Injeção de Falhas Controladas:** O FIS permite aos usuários injetar falhas de maneira controlada em suas cargas de trabalho, simulando cenários como falhas de servidores, interrupções de rede, indisponibilidade de recursos, entre outros. Isso ajuda as organizações a entenderem como seus sistemas se comportam em situações adversas e a desenvolverem estratégias de mitigação.

- **Testes de Resiliência:** Com o FIS, as organizações podem realizar testes de resiliência em suas arquiteturas na nuvem, identificando pontos de falha e avaliando a capacidade de seus sistemas de se recuperarem de falhas inesperadas. Isso é especialmente útil para garantir a alta disponibilidade e a confiabilidade de aplicativos críticos para os negócios.

- **Avaliação de Recuperação de Desastres:** O FIS permite simular cenários de recuperação de desastres, testando a eficácia dos planos de contingência e recuperação em caso de falhas catastróficas. Isso ajuda as organizações a garantirem que estão preparadas para lidar com eventos adversos e minimizar o impacto sobre suas operações.

- **Análise de Impacto:** Ao simular falhas em suas cargas de trabalho, o FIS fornece insights valiosos sobre o impacto dessas falhas em sistemas e aplicativos, permitindo que as organizações avaliem os riscos e tomem medidas proativas para mitigar potenciais danos.

- **Suporte à Melhoria Contínua:** Utilizando o FIS de forma regular, as organizações podem promover uma cultura de melhoria contínua, identificando áreas de oportunidade e implementando medidas para aumentar a resiliência e a robustez de suas arquiteturas na nuvem.

- **Integração com Ferramentas de Monitoramento:** O FIS pode ser integrado com ferramentas de monitoramento e observabilidade, permitindo uma análise mais abrangente do comportamento dos sistemas durante os testes de injeção de falhas.

O AWS Fault Injection Simulator é uma ferramenta poderosa para ajudar as organizações a fortalecerem suas arquiteturas na nuvem, aumentando a resiliência e a confiabilidade de seus sistemas e aplicativos críticos para os negócios.

## AWS Ground Station

**AWS Ground Station:**
O AWS Ground Station é um serviço oferecido pela Amazon Web Services (AWS) que permite controlar satélites e processar dados de satélites de forma rápida e econômica diretamente na nuvem da AWS. Com o AWS Ground Station, as organizações podem reduzir significativamente o tempo e o custo necessários para receber e processar dados de satélites, facilitando a tomada de decisões baseadas em informações atualizadas e precisas.

Principais recursos e benefícios do AWS Ground Station:

- **Controle de Satélites:** O AWS Ground Station oferece uma infraestrutura global de estações terrestres que permite controlar satélites em órbita a partir de qualquer lugar do mundo. Com uma rede distribuída de antenas, as organizações podem acessar facilmente serviços de controle de satélites sem a necessidade de investir em infraestrutura física.

- **Recepção de Dados:** As estações terrestres do AWS Ground Station são capazes de receber dados de satélites em tempo real, fornecendo acesso imediato a imagens, vídeos e outros tipos de dados gerados por satélites. Isso permite que as organizações monitorem eventos em tempo real e tomem decisões rápidas com base nas informações recebidas.

- **Processamento de Dados na Nuvem:** Uma vez recebidos, os dados dos satélites são processados diretamente na nuvem da AWS, utilizando serviços como o Amazon S3, Amazon EC2 e Amazon Lambda. Isso elimina a necessidade de transferir grandes volumes de dados para instalações locais, reduzindo os custos e a complexidade do processamento de dados de satélites.

- **Integração com Serviços AWS:** O AWS Ground Station é totalmente integrado com outros serviços da AWS, permitindo a criação de pipelines de processamento de dados personalizados e a integração com aplicativos e sistemas existentes na nuvem. Isso proporciona maior flexibilidade e escalabilidade no gerenciamento de dados de satélites.

- **Escalabilidade e Elasticidade:** Com a AWS, as organizações podem escalar facilmente suas operações de controle de satélites de acordo com as necessidades do negócio, adicionando ou removendo capacidade de processamento conforme necessário. Isso garante que os recursos de controle de satélites possam acompanhar a demanda e evitar gargalos de desempenho.

- **Segurança e Conformidade:** O AWS Ground Station oferece recursos avançados de segurança e conformidade, incluindo criptografia de dados, controle de acesso granular e conformidade com padrões de segurança reconhecidos internacionalmente. Isso ajuda as organizações a protegerem suas informações sensíveis e a atenderem aos requisitos regulatórios do setor.

O AWS Ground Station é uma solução poderosa para empresas e organizações que dependem de dados de satélites para suas operações, oferecendo uma maneira eficiente e econômica de controlar satélites e processar dados diretamente na nuvem da AWS.

## Amazon Pinpoint

**Amazon Pinpoint:**
O Amazon Pinpoint é um serviço oferecido pela Amazon Web Services (AWS) que permite que empresas e desenvolvedores enviem mensagens personalizadas por e-mail, SMS e notificações push para seus clientes de forma escalável e eficiente. Além disso, o Amazon Pinpoint oferece recursos avançados de análise e segmentação para ajudar as empresas a entender o comportamento dos clientes e a otimizar suas campanhas de marketing.

Principais recursos e benefícios do Amazon Pinpoint:

- **Envio de Mensagens Multicanal:** Com o Amazon Pinpoint, as empresas podem enviar mensagens personalizadas por e-mail, SMS e notificações push para seus clientes, permitindo uma comunicação eficaz em vários canais. Isso proporciona flexibilidade e alcance máximo para as campanhas de marketing e engajamento do cliente.

- **Personalização de Conteúdo:** O Amazon Pinpoint permite que as empresas personalizem o conteúdo de suas mensagens com base nas preferências e comportamentos individuais dos clientes. Isso inclui a personalização de texto, imagens, ofertas e outros elementos para aumentar a relevância e o impacto das mensagens.

- **Segmentação Avançada:** Com recursos avançados de segmentação, o Amazon Pinpoint permite que as empresas identifiquem e segmentem grupos específicos de clientes com base em critérios demográficos, comportamentais e de engajamento. Isso ajuda a direcionar as mensagens para o público certo, aumentando a eficácia das campanhas de marketing.

- **Análise de Dados:** O Amazon Pinpoint fornece insights detalhados sobre o desempenho das campanhas de marketing, incluindo métricas como taxas de abertura, cliques, conversões e muito mais. Isso permite que as empresas avaliem o impacto de suas campanhas e façam ajustes para melhorar os resultados ao longo do tempo.

- **Automação de Campanhas:** Com o Amazon Pinpoint, as empresas podem automatizar o envio de mensagens com base em eventos específicos do cliente, como inscrições, compras ou interações com o aplicativo. Isso permite que as empresas criem jornadas de cliente personalizadas e acionadas por eventos, aumentando o engajamento e a fidelidade do cliente.

- **Segurança e Conformidade:** O Amazon Pinpoint oferece recursos avançados de segurança e conformidade, incluindo criptografia de dados, controle de acesso granular e conformidade com padrões de segurança reconhecidos internacionalmente. Isso ajuda as empresas a protegerem informações sensíveis e a atenderem aos requisitos regulatórios do setor.

O Amazon Pinpoint é uma solução poderosa para empresas que desejam criar experiências de comunicação personalizadas e eficazes para seus clientes, aumentando o engajamento, a fidelidade e o sucesso do cliente.

## AWS Application Discovery Service

**AWS Application Discovery Service:**
O AWS Application Discovery Service é um serviço oferecido pela Amazon Web Services (AWS) que ajuda as empresas a planejarem e executarem migrações de seus serviços on-premises para a nuvem da AWS. Este serviço realiza a descoberta automatizada de aplicativos e infraestrutura existentes, fornecendo informações detalhadas sobre os recursos, dependências e interações entre os componentes do ambiente de TI.

Principais recursos e benefícios do AWS Application Discovery Service:

- **Descoberta Automatizada de Aplicativos:** O serviço realiza a descoberta automatizada de todos os aplicativos e serviços em execução em ambientes on-premises, identificando servidores, sistemas operacionais, aplicativos instalados e dependências entre os componentes.

- **Mapeamento de Dependências:** O AWS Application Discovery Service mapeia as dependências entre os aplicativos e os servidores em um ambiente on-premises, permitindo que as empresas entendam completamente as interações entre os diferentes componentes de sua infraestrutura de TI.

- **Análise de Performance e Utilização:** Além de mapear as dependências entre os aplicativos e servidores, o serviço também fornece informações detalhadas sobre a performance e a utilização dos recursos, ajudando as empresas a identificarem áreas de otimização e melhoria.

- **Visualizações e Relatórios:** O AWS Application Discovery Service oferece recursos de visualização e geração de relatórios que permitem às empresas visualizarem graficamente seus ambientes on-premises, incluindo a infraestrutura física e virtual, e acessarem relatórios detalhados sobre os recursos descobertos.

- **Planejamento de Migração:** Com base nas informações coletadas durante o processo de descoberta, o serviço ajuda as empresas a planejarem suas migrações para a nuvem da AWS, identificando os aplicativos e servidores que podem ser migrados, as dependências entre eles e os requisitos de recursos na nuvem.

- **Integração com Serviços de Migração:** O AWS Application Discovery Service pode ser integrado a outros serviços e ferramentas de migração da AWS, facilitando o processo de migração e garantindo uma transição suave para a nuvem.

- **Segurança e Conformidade:** O serviço oferece recursos avançados de segurança e conformidade, incluindo criptografia de dados, controle de acesso granular e conformidade com padrões de segurança reconhecidos internacionalmente, garantindo a proteção das informações sensíveis durante o processo de migração.

O AWS Application Discovery Service é uma ferramenta poderosa para empresas que desejam migrar seus serviços on-premises para a nuvem da AWS, oferecendo insights detalhados, planejamento eficaz e uma transição suave para a nuvem.


## AWS Cloud Best Practices - Design Principles

**AWS Cloud Best Practices - Design Principles:**

Ao projetar e implantar aplicativos na AWS, é essencial seguir uma série de práticas recomendadas para garantir eficiência, escalabilidade e confiabilidade. Aqui estão alguns dos princípios de design mais importantes a serem considerados:

- **Escalabilidade Horizontal e Vertical:** Projete suas aplicações de forma que possam escalar tanto horizontalmente (adicionando mais instâncias) quanto verticalmente (aumentando os recursos das instâncias existentes). Isso permite lidar com aumentos repentinos no tráfego e na demanda de forma eficaz, garantindo que sua aplicação permaneça disponível e responsiva.

- **Servidores que Possam ser Encerrados e Iniciados Rapidamente:** Utilize serviços e recursos que permitam a inicialização rápida e o encerramento de servidores e instâncias, conforme necessário. Isso ajuda a otimizar os custos, reduzindo o tempo de execução de recursos não utilizados e permitindo uma alocação eficiente de recursos sob demanda.

- **Automação:** Implemente automação em todos os aspectos do seu ambiente na nuvem, desde a provisionamento de infraestrutura até a implementação de aplicativos e a configuração de políticas de segurança. Isso não só aumenta a eficiência operacional, mas também reduz a probabilidade de erros humanos e simplifica a gestão de recursos.

- **Pouco Acoplamento:** Projete suas aplicações de forma que os componentes sejam independentes e tenham pouco acoplamento entre si. Isso facilita a manutenção, atualização e escalabilidade das aplicações, permitindo que os componentes sejam modificados ou substituídos sem afetar o funcionamento do sistema como um todo.

- **Pense em Serviços, não em Servidores:** Ao projetar sua arquitetura na nuvem, adote uma abordagem de "pensar em serviços", onde cada componente da aplicação seja tratado como um serviço independente e gerenciável. Isso permite uma arquitetura mais modular e flexível, facilitando a integração com outros serviços e a adoção de novas tecnologias no futuro.

Seguir esses princípios de design ajuda a garantir que suas aplicações na AWS sejam altamente disponíveis, eficientes em termos de custos e capazes de atender às demandas em constante evolução do seu negócio.
