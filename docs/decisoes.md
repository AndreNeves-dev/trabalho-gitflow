# Diário de Decisões e Conflitos

Registre aqui:
- **Arquivo/linhas** com conflito (aproximado).
- **Causa** (ex.: alteração simultânea da mesma linha).
- **Alternativas consideradas**.
- **Decisão final** e **racional**.
- **Quem resolveu** (A/B/C) e **data**.

## Convenções de branch (Fase 0)
- `main`: versão estável, publicada.
- `develop`: integração das funcionalidades.
- `feature/nome`: novas funcionalidades, saem de `develop` e voltam para `develop`.
- `release/x.y.z`: preparação de versão, sai de `develop` e vai para `main` e `develop`.
- `hotfix/ajuste`: correção urgente, sai de `main` e vai para `main` e `develop`.
- Todos os merges são feitos com `--no-ff`, para manter as branches visíveis no histórico.

## Conflitos da Fase 3 (merge de feature/tema-ajustavel em develop)
Ordem dos merges: primeiro `feature/incremento-rename` (sem conflito), depois `feature/tema-ajustavel` (com conflito).

### 1. app.js – bloco do botão "+" (aprox. linhas 15 a 16)
- **Causa:** B e C alteraram a mesma linha do incremento. B escreveu `state.count += 2` e renomeou a chamada para `updateCount`; C escreveu `state.count = state.count + 2` e manteve `setCount`.
- **Alternativas:** manter a versão do B, manter a versão do C ou combinar as duas.
- **Decisão:** combinar. Fica `state.count += 2` com `updateCount` (versão do B), porque a função foi renomeada e `setCount` não existe mais. As melhorias do C no `toggleTheme` (cartão, bordas e texto do botão) foram mantidas.
- **Quem resolveu:** Aluno A – outubro/2026.

### 2. styles.css – variável `--primary` (linha 2)
- **Causa:** B mudou a cor primária para verde e C para vermelho, na mesma linha.
- **Alternativas:** verde (B) ou vermelho (C).
- **Decisão:** manter o verde do B. O vermelho passa ideia de erro e prejudica a leitura dos botões; o tema escuro do C continua funcionando, pois usa as outras variáveis.
- **Quem resolveu:** Aluno A – outubro/2026.

### 3. index.html – título `<h1 id="title">` (linha 11)
- **Causa:** B incluiu "Equipe B" e C incluiu "Modo Escuro" no mesmo título.
- **Alternativas:** manter um dos dois ou juntar os dois textos.
- **Decisão:** manter "Mini App – GitFlow – Equipe B". O texto "Modo Escuro" já aparece de forma dinâmica pelo `app.js` quando o tema escuro é ativado, então fixá-lo no HTML ficaria errado no tema claro.
- **Quem resolveu:** Aluno A – outubro/2026.
