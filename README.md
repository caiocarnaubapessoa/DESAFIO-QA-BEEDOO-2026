# DESAFIO-QA-BEEDOO-2026
Desafio Técnico QA Beedoo
Objetivo da aplicação:
A aplicação atua como um sistema de cursos. Seu objetivo principal é permitir que administradores ou usuários autorizados realizem o registro de novas capacitações e visualizem de forma consolidada os cursos já disponíveis na base de dados.

Principais fluxos disponíveis:
O sistema é focado em operações de Criação (Create) e Leitura (Read), dividindo-se nos seguintes fluxos centrais:

Visualização: Acesso à listagem geral dos cursos cadastrados.

Criação: Acesso ao formulário de cadastro > Preenchimento de dados > Submissão e finalização do cadastro.

Pontos do sistema considerados mais críticos para teste:
O ponto de maior criticidade é o formulário de cadastro de cursos, especificamente na camada de validação de dados de entrada (Front-end/Back-end). Durante a exploração inicial, identifiquei ausência de tratamentos básicos, o que compromete a integridade do banco de dados. Os focos críticos de teste são:

Obrigatoriedade de campos: O sistema atualmente permite a submissão de formulários em branco.

Tipagem e formatação de dados: O sistema aceita a inserção de datas irreais/inválidas e permite números decimais/quebrados em campos que logicamente deveriam aceitar apenas números inteiros (como carga horária ou quantidade de vagas).
