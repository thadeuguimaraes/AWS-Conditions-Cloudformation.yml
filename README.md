# Projeto AWS Conditions Cloudformation YML.

Nesse projeto foi trocado as condições que contém declarações que definem
as circunstâncias em que as entidades são criadas ou configuradas através do script YML utilizado no Cloudformation.

Conditions

Stack simplify 

• A seção Condições contém declarações que definem as circunstâncias em que as entidades são criadas ou configuradas.

• Exemplo: 1 - Podemos criar uma condição e depois associá -la a um recurso ou saída para que a AWS CloudFormation
  Crie apenas o recurso ou saída se a condição for verdadeira.
  
• Exemplo: 2 - Podemos associar a condição a uma propriedade para que a AWS CloudFormation defina apenas a propriedade
  Para um valor específico se a condição for verdadeira, se a condição for falsa, a AWS CloudFormation
  define a propriedade para um valor diferente que especificamos.
• Usaremos as condições, quando queremos reutilizar o modelo em diferentes contextos, como ambientes de desenvolvimento e producao.


• As condições são avaliadas com base em parâmetros predefinidos do PSUDO ou em valores de parâmetros
  de entrada que especificamos quando criamos ou atualizamos a pilha.
• Dentro de cada condição, podemos referir a outra condição.
• Podemos associar essas condições em três lugares.
• Recursos
• Propriedades de recursos
• Saídas
• Na criação de pilha ou atualização da pilha, o AWS CloudFormation avalia todas as condições em nosso modelo.Durante a atualização da pilha,
  Os recursos que agora estão associados a uma condição falsa são excluídos.
• Nota importante: durante a atualização da pilha, não podemos atualizar as condições por si mesmas.
  Só podemos atualizar as condições quando incluímos alterações que adicionam, modificam ou excluam recursos.

  Conditions:
    CreateEIPForProd:
      Fn:Equals 
        - !Ref EnviromentName
        - prod 

  ============================================================================================================================================

Conditions -  Intrinsic Functions 

• Podemos usar as funções intrínsecas listadas abaixo para definir condições em
  Modelo de formação de nuvem.

• Fn::And 
• Fn::Equals 
• Fn::If 
• Fn::Not 
• Fn::Or

• Abordaremos todas essas funções em nossos exercícios de prática.

=================================================================================================================================================

Condições - Prática

• Etapa 01: Crie um EIP Quando o ambiente é Prod, use a função intrínseca fn :: equals

• Etapa 02: Crie um grupo de segurança para o ambiente de desenvolvimento quando a condição é atendida e demonstre o parâmetro pseudo "AWS :: Novalue" para
  quando o ambiente é o produto.Use função intrínseca fn :: se

• Etapa 03: Crie um grupo de segurança para o Prod Env com condição relacionada ao Prod adicionada.Use função intrínseca fn :: se

• Etapa 04: demonstrar função intrínseca fn :: não

• Etapa 05: Demonstrar função intrínseca fn :: ou

• Etapa 06: Demonstrar função intrínseca fn :: e