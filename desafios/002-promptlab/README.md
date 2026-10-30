# 002 — PromptLab: Laboratório de Engenharia de Prompts

**Categoria:** Inteligência Artificial · Engenharia de Prompt · Front-end

## Objetivo
Construir uma ferramenta web simples para transformar uma intenção inicial em um prompt estruturado, com campos que organizam papel, objetivo, contexto, dados de entrada, público, restrições, formato e critérios de qualidade.

## Problema
Prompts vagos frequentemente produzem respostas genéricas. O desafio é criar uma interface que ajude a pessoa a explicitar o que deseja, quais informações oferece e como avaliar o resultado.

## Solução implementada
O PromptLab é uma aplicação independente, desenvolvida com HTML, CSS e JavaScript puro. Não utiliza bibliotecas, banco de dados, API ou servidor.

### Funcionalidades
- Formulário para estruturar os elementos de um prompt;
- Geração do texto final com orientações de qualidade;
- Avaliação estrutural heurística de 0 a 100, com oito dimensões e recomendações de melhoria;\n- Preparação de auditoria semântica: gera uma instrução para copiar e executar em uma IA externa, sem envio automático dos dados;
- Exemplo preenchido para análise de feedbacks bancários;
- Cópia para a área de transferência;
- Download do prompt em arquivo TXT;
- Limpeza dos campos;
- Interface responsiva para celular e computador.

## Como executar
Abra o arquivo \`index.html\` em um navegador. Não é necessário instalar dependências.

## Avaliador de qualidade — V2

O avaliador verifica presença e extensão mínima dos campos, atribuindo pesos para papel (10), objetivo (22), contexto (16), dados de entrada (10), público-alvo (8), restrições (14), formato (10) e critérios de qualidade (10). Campos ausentes ou pouco desenvolvidos recebem pontuação parcial ou zero, conforme a regra de cada dimensão. O resultado é uma heurística transparente, executada no navegador; não representa uma avaliação semântica feita por um modelo de IA.

## Evolução V3 — auditoria semântica\n\nA V3 separa duas camadas que não devem ser confundidas:\n\n1. **Avaliação estrutural local:** verifica preenchimento e extensão dos oito campos, sem conexão externa.\n2. **Auditoria semântica assistida por IA:** o botão prepara uma instrução de avaliação que inclui os campos preenchidos e solicita análise de clareza, coerência, ambiguidades, contradições, verificabilidade e recomendações. O usuário copia o texto e o executa manualmente em uma IA de sua preferência.\n\nA auditoria semântica não é executada pelo próprio PromptLab, não altera automaticamente a pontuação estrutural e não transmite dados sem ação do usuário. Recomenda-se anonimizar informações antes de copiar o conteúdo para serviços externos.\n\n## Decisões técnicas
| Decisão | Justificativa |
|---|---|
| HTML, CSS e JavaScript puros | Reduzir dependências e facilitar a leitura do código |
| Estado mantido na página | Evitar armazenamento de dados do usuário |
| Sem API externa | Não enviar o conteúdo preenchido para terceiros |
| Campos independentes | Facilitar revisão e refinamento incremental |

## Critérios de validação
- [ ] Não gerar prompt sem objetivo principal;
- [ ] Incluir no resultado os campos preenchidos;
- [ ] Omitir seções opcionais vazias;
- [ ] Copiar o texto gerado;
- [ ] Baixar arquivo TXT;
- [ ] Usar em telas pequenas sem rolagem horizontal;
- [ ] Confirmar que os dados não são enviados a serviços externos.

## Aprendizados e próximos passos
Este desafio demonstra como transformar princípios de engenharia de prompt em uma ferramenta utilizável. Uma evolução futura poderá incluir avaliação heurística do prompt, histórico local opcional e modelos por tipo de tarefa.

## Registro de desenvolvimento
- **Data:** 30/10/2026
- **Versão:** 3.0
- **Stack:** HTML5, CSS3 e JavaScript
- **Status:** V3 implementada no repositório; validação funcional pendente em navegador móvel e desktop.
