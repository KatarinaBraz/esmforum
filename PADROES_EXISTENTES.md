# Padrões de Projeto Existentes

## 1. Repository Pattern Parcial

O arquivo `modelo.js` funciona parcialmente como uma camada de acesso aos dados, pois centraliza funções responsáveis por consultar e alterar informações no banco.

Exemplo:

```javascript
function listar_perguntas() {
    const perguntas = bd.queryAll('select * from perguntas', []);
    perguntas.forEach(pergunta => pergunta['num_respostas'] = get_num_respostas(pergunta['id_pergunta']));
    return perguntas;
}
```

Outro exemplo:

```javascript
function cadastrar_pergunta(texto) {
    return bd.exec(
        'INSERT INTO perguntas (texto, id_usuario) VALUES(?, ?)',
        [texto, 1]
    );
}
```

Esse padrão aparece de forma parcial porque o arquivo concentra o acesso ao banco, mas ainda mistura diferentes responsabilidades em um único módulo.

### Possível melhoria

Separar o acesso aos dados em repositórios específicos:

- `PerguntaRepository.js`
- `RespostaRepository.js`
- `UsuarioRepository.js`

---

## 2. Dependency Injection Parcial

A função `reconfig_bd()` permite substituir o banco de dados real por uma versão mockada.

```javascript
function reconfig_bd(mock_bd) {
    bd = mock_bd;
}
```

Isso se aproxima do padrão Dependency Injection, pois permite injetar uma dependência externa no módulo.

### Possível melhoria

Criar uma estrutura mais explícita para injeção de dependências, facilitando testes e manutenção.

---

## 3. Module Pattern

O sistema utiliza módulos JavaScript por meio de `require` e `exports`.

Exemplo:

```javascript
var bd = require('./bd/bd_utils.js');
```

E no final do arquivo:

```javascript
exports.listar_perguntas = listar_perguntas;
exports.cadastrar_pergunta = cadastrar_pergunta;
exports.buscar_perguntas = buscar_perguntas;
```

Esse padrão ajuda a organizar o código e permite reutilizar funções em outras partes do sistema.

### Possível melhoria

Dividir os módulos em camadas mais claras, como:

- controllers
- services
- repositories
- models
