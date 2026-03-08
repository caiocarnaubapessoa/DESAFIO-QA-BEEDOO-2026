# DESAFIO-QA-BEEDOO-2026
Documentação do Desafio
1. Análise e Exploração da Aplicação
A aplicação atua como um sistema de gestão de catálogo educacional, com o objetivo de permitir o registro de novas capacitações e a visualização consolidada dos cursos na base de dados.

Os fluxos centrais baseiam-se em operações de CRUD:

Cadastro (Create): Inserção de dados através do formulário, incluindo o tratamento de campos com regras condicionais (ex: Link para cursos Online e Endereço para Presenciais).

Listagem (Read): Visualização geral dos cards informativos na tela principal.

Exclusão (Delete): Remoção de cursos através do botão dedicado nos cards da listagem.

O ponto de maior criticidade identificado é a camada de validação de dados no formulário, além da garantia de funcionamento dos fluxos principais, que atualmente apresentam falhas graves de integridade e usabilidade.

2. Decisões tomadas para criação dos testes
Para a estruturação dos cenários, tomei as seguintes decisões técnicas:

Uso da sintaxe BDD (Gherkin): A escrita em Dado/Quando/Então facilita o entendimento do comportamento esperado por qualquer membro da equipe e prepara a documentação para uma futura automação de testes (utilizando ferramentas como Cypress).

Organização Estruturada: Dividi a entrega em "Casos de Teste" e "Relatório de Bugs", adicionando colunas de rastreabilidade (Prioridade, Versão Testada, Resultado Esperado x Real) para refletir um ambiente profissional de gestão de Qualidade.

Cobertura Abrangente: Priorizei cenários negativos, validação de limites (boundary values) e testes em regras de negócio condicionais, não me limitando apenas ao "caminho feliz".

3. Explicação do raciocínio durante a análise
Minha abordagem foi fortemente moldada pela vivência diária com análise e resolução de incidentes técnicos. A prática mostra que o usuário interage com os sistemas de maneiras imprevistas, e é nas exceções que os defeitos mais críticos se escondem.

Adotei uma postura investigativa focada na quebra do sistema e na preservação da integridade dos dados: "O que acontece se enviar o formulário em branco? O sistema aceita datas temporalmente ilógicas?"


Os cenários de teste foram escritos em Gherkin (BDD) para facilitar a compreensão do comportamento esperado e preparar o terreno para uma futura automação. A suíte de testes cobre o caminho feliz (fluxo principal e listagem), cenários negativos (validações de inputs, datas e campos obrigatórios) e edge cases (comportamentos inesperados que afetam a UI).
Link da planilha com o caso de teste: https://docs.google.com/spreadsheets/d/17WGduqvNiIJu0Hm4e-BVMU125ykbA62Qrak75KnHgh4/edit?usp=sharing
