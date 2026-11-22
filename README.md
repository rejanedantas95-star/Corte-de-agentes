# Corte de Agentes

**Estudo de caso de Rejane Dantas · Coordenação de agentes de IA com aprovação humana**

Desenhei um fluxo para dividir tarefas de atendimento, vendas e operação entre agentes especializados. Cada passagem registra quem assume a tarefa, a prioridade, o prazo e a fonte dos dados. As duas demonstrações documentam o desenho do projeto com cenários e dados fictícios.

## Comece pela correção de cardápio

Kim registra a solicitação e repassa a tarefa a Nick, que confere o preço publicado e guarda uma imagem do antes. A responsável aprova ou recusa a proposta. Se aprovada, Nick altera o preço, relê o portal e registra o depois. Se recusada, o preço fica como está e o motivo fica registrado.

[Ver o diagrama de correção de cardápio](diagramas/correcao-cardapio.webp)

## Do pedido ao caixa

Um pedido de 30 cestas passa por atendimento, proposta comercial, coordenação, agenda e conferência fiscal. Max consulta uma API de preços fictícia e de somente leitura. Propostas com desconto passam por aprovação humana. A agenda permite uma gravação por vez, e Juca confere o registro no dia seguinte. Divergências são registradas na mesma issue.

[Ver o diagrama do pedido ao caixa](diagramas/do-pedido-ao-caixa.webp)

## Decisões de design

| Decisão | Como aparece nos fluxos |
| --- | --- |
| Aprovação humana | A decisão fica registrada para descontos na proposta e mudanças de preço no portal. |
| Responsabilidade por recurso | Nick controla a gravação na agenda com uma trava que impede escritas simultâneas. |
| Passagem rastreável | Cada bilhete registra responsável, prioridade, prazo e fonte no log de passagens. |
| Fonte de referência | A proposta consulta a API de preços. A correção de cardápio começa pela leitura do valor publicado. |
