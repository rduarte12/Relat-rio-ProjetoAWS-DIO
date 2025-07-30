# RELATÓRIO DE IMPLEMENTAÇÃO DE SERVIÇOS AWS

**Data:** 29/07/2025
**Empresa:** PharmaCloud Soluções (Farmácia Fictícia)
**Responsável:** Rafael Mendonça Duarte

## Introdução
Este relatório apresenta o projeto de implementação de uma nova arquitetura de nuvem para a empresa PharmaCloud Soluções. O objetivo principal do projeto, realizado por Rafael Mendonça Duarte, foi elencar 3 serviços essenciais da AWS (Amazon Web Services) com a finalidade de construir uma plataforma virtual para a farmácia, garantindo uma **diminuição drástica de custos imediatos com infraestrutura**, ao mesmo tempo em que se cria uma base moderna, escalável e de alta performance.

## Descrição do Projeto
O projeto de implementação foi dividido em 3 etapas, focando nos serviços que compõem o núcleo de uma arquitetura *Serverless* (sem servidor). A seguir, são descritas as etapas do projeto:

### Etapa 1: Computação Principal
* **[Nome da ferramenta]**
    * AWS Lambda
* **[Foco da ferramenta]**
    * Computação Sem Servidor (*Serverless*) e Otimização de Custo.
* **[Descrição de caso de uso]**
    * O AWS Lambda será o cérebro da operação da farmácia, executando toda a lógica de negócio sem a necessidade de manter servidores ligados 24/7. Funções Lambda serão usadas para: processar pedidos de clientes, validar receitas médicas enviadas por upload, gerenciar a autenticação de usuários, e controlar o sistema de busca no catálogo de produtos. O custo é gerado apenas no milissegundo em que a função é executada, resultando em economia máxima durante períodos de baixa atividade.

### Etapa 2: Ponto de Entrada da Aplicação
* **[Nome da ferramenta]**
    * Amazon API Gateway
* **[Foco da ferramenta]**
    * Gerenciamento e Publicação de APIs de Forma Segura e Escalável.
* **[Descrição de caso de uso]**
    * O API Gateway atuará como a "porta de entrada" para todas as requisições do site e do aplicativo móvel da farmácia. Ele criará endpoints seguros (URLs) que, ao serem chamados, acionarão as funções Lambda correspondentes. Por exemplo, uma requisição `POST` para `/pedidos` acionará a função Lambda que processa um novo pedido. Ele gerencia o tráfego, a segurança contra ataques e o versionamento das APIs, simplificando a arquitetura e a comunicação entre o cliente e o backend.

### Etapa 3: Armazenamento de Dados
* **[Nome da ferramenta]**
    * Amazon DynamoDB
* **[Foco da ferramenta]**
    * Banco de Dados NoSQL de Alta Performance, Totalmente Gerenciado.
* **[Descrição de caso de uso]**
    * O DynamoDB será o repositório de dados principal da plataforma. Ele armazenará informações críticas de forma rápida e escalável, como: o catálogo completo de medicamentos e produtos (com preço, estoque, descrição), perfis de clientes (histórico de compras, endereços), sessões de usuário e os itens no carrinho de compras. Por ser gerenciado e operar no modo `On-Demand` (Sob Demanda), não há custos com licenças, manutenção de servidores ou capacidade ociosa, alinhando-se perfeitamente ao objetivo de custo-benefício.

## Conclusão
A implementação destes três serviços na empresa **PharmaCloud Soluções tem como esperado uma redução de custos operacionais na casa de 60-80%** em comparação com uma infraestrutura tradicional baseada em servidores. Além da economia, os benefícios incluem escalabilidade automática para lidar com qualquer volume de acessos, diminuição da carga de gerenciamento de infraestrutura e um aumento significativo na agilidade para desenvolver e lançar novas funcionalidades. Recomenda-se a adoção desta arquitetura *Serverless* como pilar tecnológico e a contínua exploração de outros serviços gerenciados da AWS para otimizar ainda mais os processos da empresa.

## Anexos

### Anexo A: Diagrama da Arquitetura Serverless Proposta
O diagrama abaixo ilustra o fluxo de uma requisição do usuário através dos serviços da AWS propostos, desde a chamada da API até a interação com o banco de dados.

---
**<img width="769" height="269" alt="diagramaDIO drawio" src="https://github.com/user-attachments/assets/190fea50-4153-4be3-93ea-df8445329db7" />
**

---

### Anexo B: Estimativa de Custos Mensais
A tabela a seguir detalha a estimativa de custo mensal baseada em uma projeção de 1.000.000 de requisições por mês. Os valores foram calculados utilizando a AWS Pricing Calculator e demonstram o baixíssimo custo operacional da arquitetura *Serverless*. Em anexo no repositório, está o arquivo PDF com a precificação e mais detalhes.

---

| Serviço              | Uso Mensal Estimado                         | Custo Mensal (USD) - Após Free Tier |
| :------------------- | :------------------------------------------ | :---------------------------------- |
| Amazon API Gateway   | 1.000.000 requisições (HTTP API)            | ~$1.59                              |
| AWS Lambda           | 1.000.000 requisições (256MB/200ms/arm64) | ~$0.87                              |
| Amazon DynamoDB      | 0.5M WCU, 1.5M RCU, 10GB (On-Demand)      | ~$4.36                              |
| **CUSTO MENSAL ESTIMADO** |                                             | **~ $6.82** |


---

### Anexo C: Cronograma de Implementação do Projeto
Este cronograma macro apresenta as fases e durações estimadas para a execução completa do projeto, desde o planejamento até o lançamento.

| Fase                        | Principais Atividades                                                                                               | Duração Estimada    |
| :-------------------------- | :------------------------------------------------------------------------------------------------------------------ | :------------------ |
| **1. Planejamento e Design** | - Definição detalhada dos requisitos da plataforma.<br>- Design da UX.<br>- Desenho final da arquitetura AWS.        | 2 Semana            |
| **2. Configuração e Backend** | - Criação da conta AWS.<br>- Desenvolvimento das funções Lambda.<br>- Configuração do API Gateway e do DynamoDB. | 4 Semanas           |
| **3. Desenvolvimento Frontend** | - Criação da interface do site ou aplicativo móvel que consumirá as APIs.                                          | 4 Semanas (paralelo)|
| **4. Testes e Validação** | - Testes unitários e de integração.<br>- Testes de segurança e de carga.<br>- Homologação com a área de negócio.     | 2 Semana            |
| **5. Tranferência do sistema e campacitação** | - Implantação final (Go-Live) da plataforma.<br>- Monitoramento inicial da aplicação e dos custos.                  | 4 Semanas            |
| **6. Lançamento e Operação** | - Implantação final (Go-Live) da plataforma.<br>- Monitoramento inicial da aplicação e dos custos.                  | Contínuo            |

<br>
<br>

**Assinatura do Responsável pelo Projeto:**

---
---
Rafael Mendonça Duarte
