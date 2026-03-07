# DESAFIO-QA-BEEDOO-2026
Qual é o objetivo da aplicação?
A aplicação funciona como um sistema simples de gestão de catálogo educacional. Seu objetivo principal é permitir que os usuários realizem o registro de novas capacitações através de um formulário e visualizem, de forma consolidada, os cursos já cadastrados na base de dados.

Quais são os principais fluxos disponíveis?
O sistema é focado em operações de Criação e Leitura, dividindo-se em dois fluxos centrais:

Listagem (Read): Acesso à visualização geral dos cursos já cadastrados na tela principal ("Lista de cursos") e a possibilidade de excluí-los.

Cadastro (Create): Acesso à tela "Cadastro de curso" > Preenchimento das informações do curso > Submissão e finalização do cadastro.

Quais pontos do sistema você considera mais críticos para teste?
O ponto de maior criticidade é o formulário de cadastro de cursos, especificamente na camada de validação dos dados de entrada. Durante a exploração exploratória, identifiquei que o sistema falha em garantir a integridade dos dados antes de salvá-los. Os focos mais críticos identificados foram:

Falta de validação de campos obrigatórios: O sistema permite a submissão e gravação de formulários completamente em branco, gerando cards vazios na listagem.

Ausência de tipagem e limites (Boundary Values): O sistema aceita a inserção de datas incoerentes e permite valores irreais (como textos ou números excessivamente longos) no campo de "Número de vagas", o que chega a causar a quebra visual (layout) da tela de listagem.

Os cenários de teste foram escritos em Gherkin (BDD) para facilitar a compreensão do comportamento esperado e preparar o terreno para uma futura automação. A suíte de testes cobre o caminho feliz (fluxo principal e listagem), cenários negativos (validações de inputs, datas e campos obrigatórios) e edge cases (comportamentos inesperados que afetam a UI).
Link da planilha com o caso de teste: https://docs.google.com/spreadsheets/d/17WGduqvNiIJu0Hm4e-BVMU125ykbA62Qrak75KnHgh4/edit?usp=sharing
