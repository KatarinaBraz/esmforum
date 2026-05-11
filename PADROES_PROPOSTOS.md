# Proposta de Aplicação de Padrões de Projeto

## 1. Factory Pattern

### Contexto

O padrão Factory poderia ser utilizado na criação de perguntas e respostas.

### Problema Resolvido

Centraliza a criação de objetos e evita repetição de código.

### Proposta

Criar uma fábrica responsável pela criação dos objetos do sistema.

### Exemplo

```javascript
class ConteudoFactory {
    criarPergunta(texto, usuario) {
        return {
            tipo: 'pergunta',
            texto,
            usuario
        };
    }

    criarResposta(texto, usuario) {
        return {
            tipo: 'resposta',
            texto,
            usuario
        };
    }
}
```

### Benefícios

- Reutilização
- Melhor organização
- Facilidade de manutenção

---

## 2. Observer Pattern

### Contexto

Aplicável no sistema de notificações de respostas.

### Problema Resolvido

Permite notificar usuários automaticamente quando uma nova resposta for cadastrada.

### Proposta

Quando uma resposta for criada, observadores seriam notificados.

### Exemplo

```javascript
class Notificador {
    atualizar(usuario) {
        console.log('Nova resposta para o usuário');
    }
}
```

### Benefícios

- Baixo acoplamento
- Facilidade para adicionar novos tipos de notificação

---

## 3. Facade Pattern

### Contexto

Aplicável para simplificar comunicação entre frontend, backend e banco.

### Problema Resolvido

Reduz complexidade das chamadas do sistema.

### Proposta

Criar uma camada intermediária centralizando operações.

### Exemplo

```javascript
class ForumFacade {
    buscarPerguntas() {}
    cadastrarPergunta() {}
    cadastrarResposta() {}
}
```

### Benefícios

- Código mais organizado
- Menor complexidade
- Facilidade de manutenção
