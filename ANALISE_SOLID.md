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
