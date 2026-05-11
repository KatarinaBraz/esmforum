# Implementação com SOLID

## Funcionalidade Implementada

Foi implementada a funcionalidade de busca de perguntas por palavra-chave.

A função adicionada permite pesquisar perguntas cadastradas utilizando o conteúdo textual da pergunta.

## Código Implementado

```javascript
function buscar_perguntas(palavra) {
    return bd.queryAll(
        'select * from perguntas where texto like ?',
        [`%${palavra}%`]
    );
}
```

Também foi adicionada a exportação da função:

```javascript
exports.buscar_perguntas = buscar_perguntas;
```

---

## Aplicação dos Princípios SOLID

### Single Responsibility Principle (SRP)

A função `buscar_perguntas()` possui apenas uma responsabilidade: realizar a busca de perguntas no banco de dados a partir de uma palavra-chave.

Isso evita misturar a busca com outras regras, como cadastro, listagem ou contagem de respostas.

---

### Open/Closed Principle (OCP)

A funcionalidade foi adicionada sem modificar o comportamento das funções já existentes.

O sistema foi estendido com uma nova função, mantendo as operações anteriores funcionando da mesma forma.

---

### Dependency Inversion Principle (DIP)

A implementação utiliza o objeto `bd` como dependência para acesso ao banco de dados, evitando que a lógica da busca dependa diretamente de detalhes internos do SQLite.

Além disso, o projeto já permite substituir essa dependência por um banco mockado durante testes:

```javascript
function reconfig_bd(mock_bd) {
    bd = mock_bd;
}
```

---

## Benefícios da Implementação

- Código simples e reutilizável
- Facilidade para manutenção
- Possibilidade de expansão futura
- Melhor organização lógica
- Funcionalidade adicionada sem quebrar o código existente
