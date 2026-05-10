# Design Simples

## Análise do Backend

O código atual do backend segue alguns princípios de Design Simples presentes no Extreme Programming (XP).

## Aplicação do princípio YAGNI

O sistema implementa apenas funcionalidades necessárias para o funcionamento atual do fórum, evitando complexidade desnecessária.

Exemplo:

As rotas de perguntas e respostas possuem apenas operações essenciais, como:

- criação
- listagem
- busca por ID

Não existem abstrações excessivas ou funcionalidades futuras implementadas sem necessidade.

## Exemplos observados

### routes/perguntas.js

As rotas são simples e diretas, utilizando poucas camadas de abstração.

Exemplo:

```javascript
router.get('/', async (req, res) => {
  const perguntas = await db.all('SELECT * FROM perguntas');
  res.json(perguntas);
});
```

O código é objetivo e fácil de entender.

### routes/respostas.js

A mesma abordagem é utilizada nas respostas, mantendo simplicidade e legibilidade.

## Oportunidades de Simplificação

Apesar da simplicidade atual, algumas melhorias poderiam ser aplicadas:

- Separar acesso ao banco em arquivos específicos
- Criar tratamento centralizado de erros
- Evitar repetição de código entre rotas

Essas melhorias aumentariam a organização sem adicionar complexidade excessiva.
