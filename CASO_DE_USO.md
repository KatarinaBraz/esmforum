# Caso de Uso: Buscar Perguntas por Palavra-chave

## Nome do Caso de Uso

Buscar perguntas por palavra-chave

## Atores

Usuário do fórum

## Pré-condições

- O sistema está disponível.
- Existem perguntas cadastradas no banco de dados.
- O usuário está na tela principal de perguntas.

## Fluxo Principal

1. O sistema exibe a lista de perguntas cadastradas.
2. O usuário digita uma palavra-chave no campo de busca.
3. O usuário confirma a busca.
4. O frontend envia a palavra-chave para a API.
5. A API consulta o banco de dados buscando perguntas com título ou conteúdo relacionado.
6. O banco de dados retorna as perguntas encontradas.
7. A API envia os resultados para o frontend.
8. O sistema exibe ao usuário a lista de perguntas encontradas.

## Fluxo Alternativo 1: Nenhuma pergunta encontrada

5a. A API consulta o banco de dados e não encontra perguntas relacionadas à palavra-chave.  
5b. A API retorna uma lista vazia para o frontend.  
5c. O sistema exibe a mensagem: "Nenhuma pergunta encontrada."  

## Fluxo Alternativo 2: Campo de busca vazio

2a. O usuário deixa o campo de busca vazio.  
2b. O sistema mantém ou recarrega a lista completa de perguntas.  

## Pós-condições

- O usuário visualiza perguntas relacionadas à palavra-chave pesquisada.
- Nenhuma pergunta é alterada ou removida do banco de dados.
