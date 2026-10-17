# matutando

Gestão de estúdio para artistas de música eletrônica: faixas, versões de áudio, lançamentos, envios de demo e sets. É um único arquivo HTML, funciona offline e não precisa de servidor nem de instalação.

## Como usar

Abra `app gestão de studio.html` no Chrome ou no Edge. No Firefox também funciona, sem a pasta de backup.

Os dados ficam **só no seu navegador**:
- o catálogo vai para o `localStorage`;
- os áudios e as capas vão para o IndexedDB, indexados por referência.

Nada é enviado para nenhum servidor. O backup (`.json`) guarda o catálogo e as referências dos arquivos, mas não os áudios nem as capas: eles ficam indexados no navegador, e você mantém os originais nas suas pastas.

> Mudar o nome ou a pasta do arquivo HTML pode fazer o navegador tratá-lo como um site novo, que abre vazio. Faça um backup antes de mover o arquivo e importe o backup depois.

## O que tem

- **Hoje:** atrasados, próximos 7 dias, próximo lançamento com contagem regressiva, próximo set, demos aguardando resposta e faixas paradas há mais de 30 dias.
- **Mesa de trabalho:** kanban por status (Ideia → Demo → Mixagem → Masterização → Assinada → Lançada), com reordenação por arrastar.
- **Catálogo:** busca e filtros por projeto, status e gravadora.
- **Versões de áudio:** histórico de versões por faixa, forma de onda, comentários marcados no tempo e A/B entre versões no mesmo ponto.
- **Envios de demo:** registro por gravadora, status e lembrete de cobrança.
- **Planejamento e releases:** cenários de lançamento por arrastar, data de lançamento, número de catálogo e checklist com prazos calculados a partir da data.
- **Sets:** código Camelot, aviso de salto de BPM, duração em relação ao slot e setlist exportável em `.txt`.
- **Tarefas e aprendizados:** prazos e aprendizados por faixa, reunidos em visões globais.
- **Backup:** exportação e importação em `.json`, pasta de backup (Chrome/Edge), lembrete semanal e medidor de espaço.

## Testes

```bash
node tests/logic.test.cjs
```

Os testes rodam a lógica do app numa VM do Node, sem navegador. Se existir um backup privado ao lado do app (`studio_backup (6).json`, ignorado pelo git), um teste extra valida esse arquivo.
