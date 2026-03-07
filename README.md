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

Os cenários de teste foram escritos em Gherkin (BDD) para facilitar a compreensão do comportamento esperado e preparar o terreno para uma futura automação. A suíte de testes cobre o caminho feliz (fluxo principal e listagem), cenários negativos (validações de inputs, datas e campos obrigatórios) e edge cases (comportamentos inesperados que afetam a UI).
Link da planilha com o caso de teste: https://docs.google.com/spreadsheets/d/17WGduqvNiIJu0Hm4e-BVMU125ykbA62Qrak75KnHgh4/edit?usp=sharing
