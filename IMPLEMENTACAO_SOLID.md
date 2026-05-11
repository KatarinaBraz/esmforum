
---

# `IMPLEMENTACAO_SOLID.md`

```md
# Implementação com SOLID

## Funcionalidade Implementada

Foi implementada a funcionalidade de busca de perguntas por palavra-chave.

A função adicionada permite pesquisar perguntas cadastradas utilizando o conteúdo textual.

## Código Implementado

```javascript
function buscar_perguntas(palavra) {
    return bd.queryAll(
        'select * from perguntas where texto like ?',
        [`%${palavra}%`]
    );
}
