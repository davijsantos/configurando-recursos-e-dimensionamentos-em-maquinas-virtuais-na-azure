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


