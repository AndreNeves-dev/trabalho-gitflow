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
