# DESAFIO-QA-BEEDOO-2026
Exploração da Aplicação
Qual você acredita ser o objetivo da aplicação?

A aplicação atua como um sistema simples de gestão de catálogo educacional. Seu objetivo principal é permitir que administradores ou usuários realizem o registro de novas capacitações através de um formulário e visualizem, de forma consolidada, os cursos já disponíveis na base de dados.

Quais são os principais fluxos disponíveis?

O sistema é construído sobre operações básicas de CRUD (Create, Read, Delete), dividindo-se nos seguintes fluxos centrais:

Cadastro (Create): Acesso à tela de "Cadastro de curso", preenchimento das informações (incluindo campos com lógicas condicionais) e submissão do formulário.

Listagem (Read): Acesso à tela principal ("Lista de cursos") para visualização geral dos cards com as informações cadastradas.

Exclusão (Delete): Ação de remoção de um curso específico através do botão "Excluir Curso" presente em cada card na listagem.

Quais pontos do sistema você considera mais críticos para teste?

O ponto de maior criticidade é a camada de validação e integridade de dados no formulário de cadastro, além da garantia de funcionamento dos fluxos principais. Durante a exploração exploratória, considerei críticos os seguintes pontos (que atualmente apresentam falhas):

Falta de validação de campos obrigatórios: O sistema permite a submissão e gravação de formulários completamente em branco, gerando cards vazios na listagem e comprometendo a base de dados.

Perda de dados em regras de negócio condicionais: Ao alternar o tipo de curso (Online ou Presencial), o sistema exibe campos específicos (Link ou Endereço). No entanto, essas informações não são salvas ou exibidas após o cadastro, caracterizando perda de dados inseridos pelo usuário.

Ausência de limites e tipagem (Boundary Values): O sistema aceita a inserção de datas cronologicamente incoerentes e permite valores irreais (texto ou números excessivamente longos) no campo de vagas, o que chega a causar a quebra visual (layout) da tela de listagem.

Falha em fluxo principal (Exclusão): O botão de excluir cursos não executa a ação solicitada, impedindo o gerenciamento correto do catálogo.

Documentação do Desafio
1. Análise inicial da aplicação
A aplicação avaliada funciona como um sistema de gestão de catálogo educacional. O objetivo principal é permitir que administradores realizem o registro de novas capacitações e visualizem os cursos cadastrados de forma consolidada.

Os fluxos centrais baseiam-se em operações de CRUD (Create, Read, Delete):

Cadastro (Create): Inserção de dados através do formulário de novos cursos, incluindo o tratamento de campos com regras condicionais (ex: Link para cursos Online e Endereço para Presenciais).

Listagem (Read): Visualização geral dos cards informativos na tela principal.

Exclusão (Delete): Remoção de cursos através do botão dedicado nos cards da listagem.

Durante a exploração, identifiquei que a camada de validação de dados no formulário e o funcionamento dos fluxos principais (como a exclusão) são os pontos mais críticos do sistema, apresentando falhas graves de integridade e usabilidade que afetam diretamente o banco de dados.

2. Decisões tomadas para criação dos testes
Para a estruturação dos cenários de teste, tomei as seguintes decisões técnicas:

Uso da sintaxe BDD (Gherkin): Escrevi os passos de execução utilizando Dado/Quando/Então. Essa escolha visa facilitar o entendimento do comportamento esperado por qualquer membro da equipe (técnico ou não) e já preparar a documentação para uma futura automação de testes (utilizando frameworks como Cypress, por exemplo).

Organização em Planilha Estruturada: Dividi a documentação em "Casos de Teste" e "Relatório de Bugs". Adicionei colunas de rastreabilidade (como Prioridade, Versão Testada, Resultado Esperado x Real e Link de Evidências) para simular um ambiente real e profissional de gestão de Qualidade.

Cobertura Abrangente: Os testes não se limitaram ao "caminho feliz". Priorizei cenários negativos, validação de limites (boundary values em campos numéricos) e testes em regras de negócio condicionais.

3. Explicação do raciocínio durante a análise
Minha abordagem de testes foi fortemente moldada pela minha vivência diária atuando com análise e resolução de incidentes técnicos. A prática me ensinou que o usuário frequentemente interage com os sistemas de maneiras imprevistas, e é nas exceções que os defeitos mais críticos se escondem.

Por isso, meu raciocínio não foi apenas "verificar se o sistema cadastra um curso", mas sim adotar uma postura investigativa: "O que acontece se eu enviar o formulário em branco? O sistema aceita datas temporalmente ilógicas? O que ocorre com os dados quando altero a modalidade do curso?"

Esse pensamento focado na quebra do sistema e na preservação da integridade dos dados me levou a identificar não apenas bugs visuais (como a quebra de layout no campo de vagas), mas falhas graves de lógica, como a perda de dados dos campos "Endereço" e "Link de inscrição" no momento do salvamento e a inatividade do botão de exclusão. O foco foi garantir a confiabilidade da aplicação antes que essas falhas chegassem ao usuário final.


Os cenários de teste foram escritos em Gherkin (BDD) para facilitar a compreensão do comportamento esperado e preparar o terreno para uma futura automação. A suíte de testes cobre o caminho feliz (fluxo principal e listagem), cenários negativos (validações de inputs, datas e campos obrigatórios) e edge cases (comportamentos inesperados que afetam a UI).
Link da planilha com o caso de teste: https://docs.google.com/spreadsheets/d/17WGduqvNiIJu0Hm4e-BVMU125ykbA62Qrak75KnHgh4/edit?usp=sharing
