# ☁️ Nuvem de Palavras

Ferramenta interativa de **brainstorming colaborativo em tempo real** para salas de aula. Participantes enviam palavras que aparecem em uma nuvem dinâmica — quanto mais repetida uma palavra, maior ela fica.

## ✨ Funcionalidades

- **Tempo real** — palavras aparecem instantaneamente para todos na sala via Supabase
- **Nuvem dinâmica** — tamanho das palavras proporcional à frequência de envio
- **Controle de ciclos** — ciclos automáticos com timer configurável
- **Limite por participante** — número máximo de palavras por usuário configurável
- **Reset de sala** — professor pode reiniciar a nuvem para todos simultaneamente
- **Contador de participantes ativos** — visibilidade do engajamento da turma
- **Exportação** — gera código HTML standalone e código de incorporação (`<iframe>`)

## 🚀 Como usar

1. Acesse o arquivo `index.html` diretamente no navegador (ou hospede em qualquer servidor estático)
2. Na tela de configuração:
   - Defina o **número máximo de palavras** por participante (1–9)
   - Defina a **duração do ciclo** em minutos (1–9)
   - Informe um **identificador de sala** com pelo menos 3 caracteres (ex: `GLA`)
3. Clique em **Iniciar Nuvem em Tempo Real**
4. Compartilhe o link com os participantes — eles acessam a mesma tela e enviam palavras usando um apelido

## 🛠️ Tecnologias

| Tecnologia | Uso |
|---|---|
| [Supabase](https://supabase.com) | Banco de dados e sincronização em tempo real |
| [D3.js](https://d3js.org) + [d3-cloud](https://github.com/jasondavies/d3-cloud) | Renderização da nuvem de palavras |
| [Tailwind CSS](https://tailwindcss.com) | Estilização |
| HTML + JavaScript puro | Sem necessidade de build ou framework |

## 📋 Pré-requisitos

Nenhuma instalação necessária. O projeto é um único arquivo HTML com todas as dependências carregadas via CDN.

Para usar com seus próprios dados, configure as credenciais do Supabase no início do script em `index.html`:

```js
const SUPABASE_URL = "sua-url-do-supabase";
const SUPABASE_KEY = "sua-chave-publica-do-supabase";
```

O banco de dados precisa de uma tabela `palavras` com as colunas: `room`, `word`, `nickname`, `timestamp`, e uma função RPC `get_server_time`.

## 🎓 Uso Pedagógico

- Brainstorming colaborativo no início ou encerramento de aulas
- Avalie o consenso da turma visualmente pelo tamanho das palavras
- Use ciclos rápidos para manter o engajamento elevado
- Identifique os conceitos mais associados a um tema pela frequência

---

Elaborado por **Prof. Glauber Santiago** — DAC/UFSCar
