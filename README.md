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


