# grafico-psi

Este é o **Gráfico Psi**, um app para desktop para pessoas que querem criar gráficos de uma forma rápida e fácil.

Escolha um formato, adicione seus números, personalize e exporte o resultado, tudo em poucos cliques e sem precisar de internet para trabalhar com os seus dados.

## Funcionalidades

- **4 tipos de gráfico:** barras, linhas, pizza e rosca.
- **Pré-visualização ao vivo:** o gráfico é atualizado conforme você digita.
- **Dados editáveis:** adicione e remova linhas livremente, cada uma com categoria, valor e cor própria.
- **Título personalizado** para o gráfico.
- **Escolha de fonte:** DM Sans, Manrope, Arial, Georgia ou Courier New.
- **Exportação em PNG, JPG e PDF** (o PDF sai em A4 paisagem).
- **Validação de dados:** avisa quando alguma linha está incompleta ou quando há valores negativos em gráficos de pizza e rosca.
- **Privacidade:** seus dados ficam neste dispositivo.
- **Atualizações automáticas** na versão instalada.

## Tecnologias

- [Electron](https://www.electronjs.org/)
- [Chart.js](https://www.chartjs.org/)
- [electron-updater](https://www.electron.build/auto-update) para atualizações automáticas
- [electron-builder](https://www.electron.build/) para gerar os instaladores
- [Fontsource](https://fontsource.org/) (DM Sans e Manrope)

## Como usar

1. Escolha o **tipo de gráfico**.
2. Preencha o **título** e os **dados** (categoria, valor e cor).
3. Ajuste a **fonte** em *Aparência*.
4. Clique em **PNG**, **JPG** ou **PDF** para exportar e escolha onde salvar.

## Rodando o projeto em desenvolvimento

### Requisitos

- [Node.js](https://nodejs.org/) **22.12.0 ou superior**
- npm


## Gerando o instalador (Windows)

```bash
npm run dist
```

Os arquivos serão gerados na pasta `dist/`:

- **Instalador (NSIS):** `grafico-psi-setup-<versão>.exe`
- **Versão portátil:** executável que roda sem instalação

## Atualizações automáticas

O app instalado verifica por novas versões ao abrir e a cada 4 horas, usando o `electron-updater` com um servidor genérico configurado em `package.json` (`build.publish`). Para lançar uma nova versão:

1. Aumente o campo `version` no `package.json`.
2. Rode `npm run dist`.
3. Envie os arquivos gerados em `dist/` (incluindo o `latest.yml`) para o servidor de atualizações.

Se não houver internet ou o servidor estiver fora do ar, o app continua funcionando normalmente. A verificação não acontece ao rodar com `npm start`.

## Estrutura do projeto

```
├── main.js        # Processo principal do Electron (janela, exportação e atualizações)
├── preload.js     # Ponte segura entre o app e o processo principal
├── renderer.js    # Lógica da interface e geração dos gráficos
├── index.html     # Estrutura da interface
├── styles.css     # Estilos
└── package.json   # Dependências, scripts e configuração do build
```

## Autoria

Criado por **alice-ti-projetos**.
