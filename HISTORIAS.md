# Histórias de Usuário - ESM Forum

## Priorização das Histórias

As histórias foram priorizadas considerando impacto para o usuário, facilidade de implementação e valor entregue ao fórum.

1. Busca de perguntas por palavra-chave
2. Sistema de votação em perguntas
3. Categorização de perguntas por tags

A busca foi priorizada em primeiro lugar porque melhora diretamente a navegação e ajuda os usuários a encontrarem conteúdos já existentes. Em seguida, o sistema de votação ajuda a destacar perguntas relevantes. Por fim, a categorização por tags organiza melhor o conteúdo, mas depende de uma estrutura um pouco mais detalhada.

---

## História 1: Busca de Perguntas

**Como** usuário do fórum,  
**Eu quero** buscar perguntas por palavra-chave,  
**Para** encontrar rapidamente dúvidas e respostas relacionadas ao tema que estou pesquisando.

**Critérios de Aceitação:**

- [ ] O sistema deve exibir um campo de busca na tela de perguntas.
- [ ] O usuário deve conseguir pesquisar perguntas pelo título ou conteúdo.
- [ ] O sistema deve retornar apenas perguntas relacionadas à palavra-chave digitada.
- [ ] Caso nenhuma pergunta seja encontrada, o sistema deve exibir uma mensagem informativa.
- [ ] A busca deve funcionar sem remover as perguntas existentes do banco de dados.

---

## História 2: Sistema de Votação

**Como** usuário do fórum,  
**Eu quero** votar em perguntas com upvote ou downvote,  
**Para** ajudar a destacar perguntas úteis e relevantes para a comunidade.

**Critérios de Aceitação:**

- [ ] Cada pergunta deve exibir botões de upvote e downvote.
- [ ] O sistema deve mostrar o total de votos da pergunta.
- [ ] O usuário deve poder votar apenas uma vez em cada pergunta.
- [ ] O usuário deve conseguir alterar seu voto.
- [ ] O contador de votos deve ser atualizado após a votação.

---

## História 3: Categorização de Perguntas

**Como** usuário do fórum,  
**Eu quero** associar tags às perguntas,  
**Para** organizar os conteúdos por temas como tecnologia, carreira e dúvidas gerais.

**Critérios de Aceitação:**

- [ ] O usuário deve conseguir selecionar uma ou mais tags ao criar uma pergunta.
- [ ] As tags devem ser exibidas junto com cada pergunta.
- [ ] O sistema deve permitir filtrar perguntas por tag.
- [ ] O sistema deve possuir tags iniciais como tecnologia, carreira e dúvidas-gerais.
- [ ] Perguntas sem tag não devem impedir o funcionamento do fórum.
