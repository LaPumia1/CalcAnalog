# CalcAnalog

**Calculadora de sinal analógico** para instrumentação industrial: converte, nos dois sentidos, entre **contagem do cartão de entrada (CLP)**, **sinal elétrico** e **valor de engenharia**.

Suporta os padrões mais usados em campo:

| Padrão  | Início | Fim   |
|---------|--------|-------|
| 4–20 mA | 4 mA   | 20 mA |
| 0–20 mA | 0 mA   | 20 mA |
| 0–10 V  | 0 V    | 10 V  |

Disponível como **página web (HTML único, funciona offline)** e como **aplicativo Android (APK)**.

---

## Funcionalidades

- **Conversão bidirecional** – digite em qualquer campo (contagem, sinal ou valor de engenharia) ou deslize a barra do mostrador; os demais valores se ajustam automaticamente.
- **Faixa de engenharia configurável** – defina mínimo, máximo e unidade (ex.: 0–100 %, 0–10 bar, −50–150 °C). Aceita faixas invertidas (máximo menor que o mínimo) e valores negativos.
- **Contagem de fim de escala ajustável** – padrão de 30.000 contagens, editável para qualquer cartão (ex.: 27.648, 32.000, 4.095…).
- **Mostrador visual** em arco com percentual, sinal e valor em tempo real.
- **Diagnóstico do sinal 4–20 mA**:
  - abaixo de 3,6 mA → possível fio rompido;
  - acima de 21 mA → sinal fora do padrão.
- **Tabela de pontos de teste** (0, 25, 50, 75 e 100 %) – toque em uma linha para carregar o ponto; útil para calibração e comissionamento.
- **Tema claro/escuro automático**, layout responsivo para celular e desktop.

## Fórmulas utilizadas

Com `p` = fração da faixa (0 a 1):

```
contagem = p × contagem_fim
sinal    = sinal_min + p × (sinal_max − sinal_min)
valor    = eng_min   + p × (eng_max   − eng_min)
```

Exemplo (4–20 mA, faixa 0–100 bar, 30.000 contagens): 12 mA → p = 0,5 → 15.000 contagens → 50 bar.

---

## Download e uso

### Android (APK)

1. Baixe o [`CalcAnalog.apk`](CalcAnalog.apk) (também disponível na página de [Releases](../../releases/latest)).
2. No celular, abra o arquivo e permita a instalação de **fontes desconhecidas** quando solicitado.
3. Instale e abra o **CalcAnalog**.

### Web (HTML)

- Baixe o [`calculadora-sinal-analogico.html`](calculadora-sinal-analogico.html) e abra em qualquer navegador (Chrome, Edge, Firefox, Safari).
- Não precisa de instalação nem servidor; todo o cálculo roda localmente no navegador. A internet só é usada para carregar as fontes do Google Fonts (sem ela, o app usa as fontes do sistema).

## Estrutura do repositório

```
CalcAnalog/
├── CalcAnalog.apk                      # Aplicativo Android
├── calculadora-sinal-analogico.html    # Versão web (arquivo único: HTML + CSS + JS)
└── README.md
```

## Tecnologias

- HTML5, CSS3 e JavaScript puro (sem frameworks nem dependências)
- SVG para o mostrador
- Empacotamento Android a partir da mesma interface web

---

## Autor

Desenvolvido por **Lucas Souza dos Santos**.

Gostou da ferramenta? Você pode apoiar com uma doação via Pix (chave aleatória disponível dentro do app).
