# 📖 Guia de Contribuição

Obrigado por seu interesse em contribuir para o **GXHUB**! Este documento fornece diretrizes e instruções para ajudar você a contribuir de forma eficaz.

## 📋 Índice

- [Código de Conduta](#código-de-conduta)
- [Como Começar](#como-começar)
- [Processo de Contribuição](#processo-de-contribuição)
- [Diretrizes de Commit](#diretrizes-de-commit)
- [Padrões de Código](#padrões-de-código)
- [Testes](#testes)
- [Documentação](#documentação)
- [Pull Requests](#pull-requests)
- [Reportar Issues](#reportar-issues)

## 🎯 Código de Conduta

Todos os contribuidores devem aderir ao nosso [Código de Conduta](CODE_OF_CONDUCT.md):
- Ser respeitoso e inclusivo
- Acolher diferentes perspectivas
- Manter um ambiente profissional e seguro
- Reportar comportamentos inaceitáveis

## 🚀 Como Começar

### 1. Configure Seu Ambiente

```bash
# Clone o repositório
git clone https://github.com/GXHub-Group/GXHUB.git
cd GXHUB

# Instale as dependências
npm install

# Configure git hooks (opcional)
npm run prepare
```

### 2. Crie Uma Branch

```bash
# Atualize a branch main
git checkout main
git pull origin main

# Crie uma nova branch
git checkout -b feature/sua-feature
# ou
git checkout -b fix/seu-fix
# ou
git checkout -b docs/sua-documentacao
```

### Convenção de Nomes de Branch

- `feature/nome-da-feature` - Para novas funcionalidades
- `fix/nome-do-bug` - Para correções de bugs
- `docs/nome-documentacao` - Para melhorias de documentação
- `refactor/nome-refator` - Para refatorações
- `test/nome-teste` - Para testes

## 🔄 Processo de Contribuição

### Passo 1: Fork do Repositório

```bash
# Clique no botão "Fork" no GitHub
```

### Passo 2: Clone seu Fork

```bash
git clone https://github.com/SEU-USERNAME/GXHUB.git
cd GXHUB
```

### Passo 3: Adicione o Upstream

```bash
git remote add upstream https://github.com/GXHub-Group/GXHUB.git
git fetch upstream
```

### Passo 4: Crie uma Branch

```bash
git checkout -b feature/sua-feature
```

### Passo 5: Faça suas Mudanças

- Siga os [Padrões de Código](#padrões-de-código)
- Adicione testes se aplicável
- Atualize a documentação

### Passo 6: Commit suas Mudanças

```bash
git add .
git commit -m "tipo: descrição clara da mudança"
```

### Passo 7: Push para sua Branch

```bash
git push origin feature/sua-feature
```

### Passo 8: Abra um Pull Request

- Descreva claramente as mudanças
- Referencie issues relacionadas (Closes #123)
- Aguarde revisão

## 📝 Diretrizes de Commit

### Formato de Mensagem

```
tipo: descrição breve (máximo 50 caracteres)

Descrição mais detalhada da mudança (até 72 caracteres por linha).
Explique por que a mudança é necessária e o que ela faz.

Closes #123
```

### Tipos de Commit

- `feat:` - Nova funcionalidade
- `fix:` - Correção de bug
- `docs:` - Mudanças na documentação
- `style:` - Formatação, espaços em branco (sem mudanças de código)
- `refactor:` - Refatoração de código sem alterar funcionalidade
- `test:` - Adição ou modificação de testes
- `chore:` - Atualização de dependências, configurações
- `perf:` - Melhorias de performance

### Exemplo

```bash
git commit -m "feat: adicionar autenticação por token JWT

Implementa validação de token JWT para proteger endpoints.
Adiciona middleware de autenticação reutilizável.

Closes #42"
```

## 🎨 Padrões de Código

### JavaScript/TypeScript

```javascript
// Use const por padrão, let quando necessário
const name = 'John';

// Use arrow functions
const greet = (name) => `Hello, ${name}`;

// Use template literals
const message = `User: ${name}`;

// Escreva código legível
const isUserValid = user => 
  user && 
  user.email && 
  user.password;
```

### Convenções

- **Indentação:** 2 espaços
- **Aspas:** Simples (')
- **Ponto e vírgula:** Obrigatório
- **Nomes:** camelCase para variáveis, PascalCase para classes

### Linting e Formatação

```bash
# Verificar formatação
npm run format:check

# Corrigir formatação automaticamente
npm run format

# Verificar linting
npm run lint:check

# Corrigir linting automaticamente
npm run lint
```

## 🧪 Testes

### Executar Testes

```bash
# Executar todos os testes
npm test

# Executar com coverage
npm test -- --coverage

# Watch mode
npm run test:watch
```

### Escrever Testes

- Crie testes para nova funcionalidade
- Mantenha test coverage > 80%
- Use nomes descritivos para testes
- Um conceito por teste

### Exemplo

```javascript
describe('UserService', () => {
  test('should create a new user', () => {
    const user = new UserService().create({
      name: 'John',
      email: 'john@example.com'
    });
    
    expect(user).toBeDefined();
    expect(user.name).toBe('John');
  });
});
```

## 📚 Documentação

### Atualizar Documentação

- Atualize README.md se necessário
- Adicione comentários para código complexo
- Mantenha documentação sincronizada com código
- Use Markdown para documentação

### Exemplo de Comentário

```javascript
/**
 * Valida um endereço de email
 * @param {string} email - Email para validar
 * @returns {boolean} True se email é válido
 */
const isValidEmail = (email) => {
  const regex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  return regex.test(email);
};
```

## 🔀 Pull Requests

### Checklist Antes de Submeter

- [ ] Meu código segue o estilo do projeto
- [ ] Realizei self-review do meu código
- [ ] Adicionei testes para novas funcionalidades
- [ ] Todos os testes passam (`npm test`)
- [ ] Atualizei a documentação relevante
- [ ] Minhas mudanças não geram novos warnings
- [ ] Sem conflitos com a branch principal

### Descrição do PR

```markdown
## Descrição

(Descrição clara do que foi mudado)

## Tipo de Mudança

- [ ] Bug fix
- [ ] New feature
- [ ] Breaking change
- [ ] Documentation update

## Related Issues

Closes #123

## Testing

(Como testar as mudanças)
```

## 🐛 Reportar Issues

### Template para Bug Report

1. **Descrição:** Descrever o bug claramente
2. **Como Reproduzir:** Passos passo a passo
3. **Comportamento Esperado:** O que deveria acontecer
4. **Comportamento Atual:** O que está acontecendo
5. **Ambiente:** SO, versão Node.js, etc.
6. **Screenshots:** Se relevante

[Abra uma Issue](https://github.com/GXHub-Group/GXHUB/issues/new?template=bug_report.md)

## 🎓 Recursos Úteis

- [GitHub Flow Guide](https://guides.github.com/introduction/flow/)
- [Semantic Versioning](https://semver.org/)
- [Conventional Commits](https://www.conventionalcommits.org/)
- [Code of Conduct](CODE_OF_CONDUCT.md)

## 📞 Precisa de Ajuda?

- 💬 [Abra uma Discussion](https://github.com/GXHub-Group/GXHUB/discussions)
- 📧 Email: support@gxhub.dev
- 🐛 [Reporte um bug](https://github.com/GXHub-Group/GXHUB/issues/new?template=bug_report.md)

## 🙏 Obrigado!

Suas contribuições são essenciais para tornar o GXHUB melhor! 🎉
