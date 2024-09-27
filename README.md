# configurando-recursos-e-dimensionamentos-em-maquinas-virtuais-na-azure
Configurando Recursos e Dimensionamentos em Máquinas Virtuais na Azure

## Validando modelos de VMs

![image](https://github.com/user-attachments/assets/13c98169-ed3e-4797-8f87-8b3d13ae875c)

Os objetivos de cada modelo estão destacados abaixo:

![image](https://github.com/user-attachments/assets/dbf28497-0660-4877-b0a1-b54f226e28ae)

Em cada modelo de VM, os recursos abaixo serão contemplados na criação:

![image](https://github.com/user-attachments/assets/855f169b-f277-4176-a8d4-a7eb0949fef7)

## Criando uma VM

Estabelecendo uma opção de disponibilidade

![image](https://github.com/user-attachments/assets/d7ab8db0-cdfe-457a-a983-bc88f237c24b)
*De cima abaixo: (1) Zonas de Disponibilidade são locais fisicamente separados dentro de uma mesma região do Azure, com consumo independente de recursos entre si (como energia, refrigeração e rede) para garantir a alta disponibilidade e a continuidade dos negócios. (2) Conjunto de Dimensionamento de Máquinas Virtuais define um conjunto de máquinas virtuais idênticas gerenciadas em conjunto como uma unidade; facilita a escalabilidade automática, permitindo que você ajuste o número de instâncias em resposta à demanda de carga. (3) Conjunto de Disponibilidade define um grupo de máquinas virtuais distribuídas entre diferentes racks de servidores e unidades de armazenamento dentro de um datacenter, usando dois tipos de separação para garantia de disponibilidade: (3.1) Domínio de falha, onde as VMs de um mesmo grupo não compartilham do mesmo hardware físico; (3.2) Domínio de Atualização, onde as VMs de um mesmo grupo são atualizadas de forma escalonada, evitando que sejam reiniciadas ao mesmo tempo.*

Criando a partir de um conjunto de dimensionamento de máquinas virtuais

![image](https://github.com/user-attachments/assets/d5342517-c908-4973-84eb-63ea65f29a27)

Criando um conjunto de dimensionamento de máquinas virtuais. Aqui é possível definir o modo de orquestração, onde o modo Uniforme define um modo centralizado de orquestração, onde as VMs do conjunto possuem as mesmas configurações e mesma imagem de sistema operacional; e o modo Flexível define um modo de personalização individual sobre cada VM, ideal para ambientes heterogêneos, onde existem diversos cenários de carga de trabalho.

![image](https://github.com/user-attachments/assets/911e8826-de16-467c-8385-1829358fa958)

Na Contagem de Instâncias, é possível definir o número de máquinas virtuais do conjunto.

![image](https://github.com/user-attachments/assets/ed7a6e37-0af9-4b26-849d-ecbfc41797dd)

Esse número define um número fixo, mas ele se torna escalável quando configuramos o dimensionamento automático. 

![image](https://github.com/user-attachments/assets/6d8dcbfc-a4f5-455c-a773-05c76356c994)

Ao configurar o dimensionamento automático, é possível definir as condições de escalabilidade vertical e horizontal, com número-limite de máquinas virtuais, e condições com base no consumo de CPU, tanto para escalar como para reduzir o número de máquinas virtuais no conjunto.

![image](https://github.com/user-attachments/assets/1aff5517-79d0-4ad3-becd-180c090ab922)

Em ambientes toleráveis a interrupções, é possível economizar dinheiro através da configuração da opção Spot. Com esta opção habilitada, as máquinas virtuais estarão disponíveis apenas quando a capacidade da nuvem não estiver sendo utilizada por outros serviços de alta prioridade.

![image](https://github.com/user-attachments/assets/fc84c85e-a4d6-4d26-8943-da90db125823)

Em Tamanho, é possível definir recursos para a máquina virtual, como CPU e Memória.

![image](https://github.com/user-attachments/assets/74fe25a8-ce35-4dcb-af7c-a5c1f1cc8fb6)

Em "Ver todos os tamanhos", é possível visualizar todas as opções de configuração de recursos disponíveis para criação de uma máquina virtual.

![image](https://github.com/user-attachments/assets/ef67da80-498c-4611-b997-5c5531a81d23)

Em "Conta de administrador", é possível definir o método de autenticação para de forma segura estabelecer conexão com a máquina virtual criada.

![image](https://github.com/user-attachments/assets/ed5f4953-f4bf-4451-aff7-37bde4f5c0c9)

Em "Regras de portas de entrada", define-se as portas TCP que podem ser acessadas pela internet pública.

![image](https://github.com/user-attachments/assets/4f5d984e-aa4f-4202-8ec2-c3474171899b)

A próxima etapa consistem em criar o disco de armazenamento para a máquina virtual. Neste ponto é interessante manter marcada a opção "Excluir com VM"; isto porque a os discos existem indepentendemente da máquina virtual. Sem que esta opção esteja marcada, quando da exclusão da máquina virtual, o disco permanecerá existindo.

![image](https://github.com/user-attachments/assets/7774caac-c481-4f5d-b96a-bec3a5384886)

Na seção a seguir, é possível criar e/ou adicionar outros discos de armazenamento.

![image](https://github.com/user-attachments/assets/97be9ce5-023a-4b03-bfd9-4c88f29d0376)

Nos passos a seguir é possível criar a rede privada da qual a máquina fará parte. No campo de IP público é possível criar e atribuir o IP público que tornará viável acessar a máquina virtual pela internet. Posteriormente é importante prestar atenção na opção "Excluir o IP público e a NIC quando a VM for excluída". Caso esta opção esteja desmarcada, caso a máquina virtual seja excluída NIC e IP público continuaram existindo.

![image](https://github.com/user-attachments/assets/35f942e1-7473-4fd7-96db-5b0052df3f94)

![image](https://github.com/user-attachments/assets/6d80d12e-1284-4cf8-9ad8-628f76e58757)

![image](https://github.com/user-attachments/assets/90446db5-9e4b-4732-8c73-6dd2ea662d63)

No passo seguinte, é possível configurar opções de gerenciamento. Na imagem a seguir, é possível visualizar a opção que permite que se utilize o MS Entra ID para logar na máquina virtual.

![image](https://github.com/user-attachments/assets/bf12bccb-c5d0-4146-bcf3-d488ccc42aa2)

É possível habilitar o serviço de desligamento automático e configurar o período de desligamento.

![image](https://github.com/user-attachments/assets/99c50930-8196-4f11-ba75-14bbfcb7f7fd)

Na aba de Monitoramento, é possível criar regras de alertas para monitorar o consumo dos recursos ligados à máquina virtual.

![image](https://github.com/user-attachments/assets/3157f6c4-b943-46dd-a877-581bad36b062)










