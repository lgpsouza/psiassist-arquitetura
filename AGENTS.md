# Instruções para agentes de desenvolvimento

Este repositório documenta a arquitetura do **PsiAssist** em fase de discovery. Ainda não há código. Se você é um agente de IA implementando qualquer parte do sistema, siga as regras abaixo.

## Fonte da verdade

1. [README.md](README.md): descrição, diagramas, decisões e lacunas.
2. ADRs em `docs/adr/`, quando existirem. Uma ADR aceita prevalece sobre a tabela de decisões propostas do README.

## Regras

- **Não invente decisões.** Se a tarefa depende de algo listado em [Lacunas](README.md#18-lacunas), pare e pergunte, ou implemente atrás de uma interface usando a *suposição de trabalho* documentada, e declare isso no PR.
- **Respeite as invariantes I1 a I6** ([README, seção 1.7](README.md#17-restrições)). Mudar uma invariante exige uma nova ADR, não um ajuste no código.
- **Respeite as regras de dependência** do diagrama de containers ([seção 2.2](README.md#22-containers-c4-nível-2)): integrações externas só no Worker, front-ends só falam com a API.
- **Use os nomes dos diagramas** (App Web do Consultório, Portal do Paciente, API Core, Worker de Processamento) em módulos, pastas e logs.
- **Nunca registre conteúdo clínico em logs**, mensagens de erro, notificações ou dados de teste versionados.
- **Mudou a arquitetura? Atualize o diagrama no mesmo PR.**
