Neste projeto, realizei a configuração completa de um ambiente de Auto Scaling na AWS com balanceamento de carga

1- Foi criado um Launch Template, que é basicamente o modelo da instância que é criada quando o gatilho é ativado.
Utilizei a AMI Amazon Linux 2 (free tier) e uma instância do tipo t.2 micro para não haver custos.
Utilizei VPC e Security Group default, adicionando apenas uma configuração de entrada no SG, liberando acesso ssh de qualquer endereço da internet para conseguir me conectar à máquina.
2- O segundo passo foi criar um Target Group para agrupar as instâncias que irão receber o tráfego do Load Balancer.
3 - O terceiro passo foi criar o Application Load Balancer que distribui as requisições entre as instâncias do Target Group.
4 - O próximo passo foi criar o Auto Scaling Group, que gerencia automaticamente a quantidade de instâncias com base na demanda.
5 - O quinto passo foi configurar um Target Tracking Scaling Policy baseada no uso da CPU, para que seja criada uma segunda instância quando a utilização de CPU da primeira instância ultrapassar 50%.
6 - O último passo foi se conectar à instância via SSH e utilizar a ferramenta Stress, para que a utilização de CPU ultrapassasse os 50%

A infraestrutura foi configurada com sucesso, permitindo escalabilidade automática e balanceamento de carga entre instâncias. Essa configuração garante maior disponibilidade, desempenho e economia de recursos em aplicações web hospedadas na AWS.

Mesmo sem experiência prévia com infraestrutura em nuvem, consegui entender e aplicar os principais conceitos de escalabilidade automática e arquitetura resiliente na AWS.

Abaixo evidências do projeto após a segunda máquina ser instanciada automaticamente

1 - Teste de Stress - https://github.com/RobertoJanuario/EC2-Load-Balancer/blob/master/stress.png
2- Launch Template - https://github.com/RobertoJanuario/EC2-Load-Balancer/blob/master/launch_template.png
3- Target Group - https://github.com/RobertoJanuario/EC2-Load-Balancer/blob/master/target_group.png
4 - Auto Scaling - https://github.com/RobertoJanuario/EC2-Load-Balancer/blob/master/auto_scaling.png
5 - Auto Scaling Group - https://github.com/RobertoJanuario/EC2-Load-Balancer/blob/master/auto_scaling_group.png
6 - Target Tracking - https://github.com/RobertoJanuario/EC2-Load-Balancer/blob/master/policy_auto_scaling.png
7 - Auto Scaling Group Gerenciamento de Instâncias - https://github.com/RobertoJanuario/EC2-Load-Balancer/blob/master/gerenciamento_instancias.png
8 - Evidência da utilização de CPU >50 - https://github.com/RobertoJanuario/EC2-Load-Balancer/blob/master/utilizacao_CPU.png


