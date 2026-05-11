# Análise SOLID

## Pontos Positivos

### 1. Single Responsibility Principle (SRP)

A função `listar_perguntas()` possui uma responsabilidade específica: retornar perguntas cadastradas no sistema.

```javascript
function listar_perguntas() {
    const perguntas = bd.queryAll('select * from perguntas', []);
    perguntas.forEach(pergunta => pergunta['num_respostas'] = get_num_respostas(pergunta['id_pergunta']));
    return perguntas;
}
```

O código mantém foco em uma única operação relacionada às perguntas.

---

### 2. Dependency Inversion Principle (DIP)

O uso da função `reconfig_bd(mock_bd)` permite desacoplamento do banco de dados real durante testes.

```javascript
function reconfig_bd(mock_bd) {
    bd = mock_bd;
}
```

Isso facilita testes unitários utilizando versões mockadas do banco.

---

### 3. Open/Closed Principle (OCP)

O sistema permite adicionar novas funções sem alterar funções já existentes.

Exemplo:

```javascript
function buscar_perguntas(palavra) {
    return bd.queryAll(
        'select * from perguntas where texto like ?',
        [`%${palavra}%`]
    );
}
```

A funcionalidade foi adicionada sem modificar o comportamento das funções anteriores.

---

## Oportunidades de Melhoria

### 1. Violação do SRP

O arquivo `modelo.js` concentra múltiplas responsabilidades:

- perguntas
- respostas
- consultas
- contagem
- cadastro

Uma melhoria seria separar responsabilidades em módulos distintos:

- `PerguntaModel.js`
- `RespostaModel.js`

---

### 2. Violação do OCP

A lógica SQL está diretamente embutida nas funções.

```javascript
bd.queryAll('select * from perguntas', []);
```

Caso o banco de dados mude, várias funções precisariam ser modificadas.

Uma solução melhor seria utilizar uma camada de repositório para abstrair consultas SQL.
