# Padrões de Projeto Existentes

## 1. Repository Pattern

O arquivo `modelo.js` centraliza operações relacionadas ao acesso aos dados do sistema.

Exemplos:

```javascript
function listar_perguntas() {
    return bd.queryAll('select * from perguntas', []);
}
