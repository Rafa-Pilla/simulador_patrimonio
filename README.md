<img width="831" height="204" alt="image" src="https://github.com/user-attachments/assets/6981b057-9c29-4894-9606-2e9d15f7b387" />

# Oinc — Simulador de Patrimônio (Fundos Imobiliários)

Ferramenta desenvolvida no Excel para simular investimentos mensais em Fundos Imobiliários (FIIs), projetar o patrimônio acumulado e os dividendos mensais em diferentes horizontes de tempo e distribuir o aporte mensal entre seis tipos de FII conforme o perfil de investidor.

> **Aviso:** Os valores, percentuais e configurações presentes nesta planilha são meramente ilustrativos e de exemplo, não constituindo recomendação de investimento.

---


## Perguntas Respondidas e Onde Encontrar Cada Resposta

Na aba **`Simulador de Patrimônio`**, a ferramenta responde as seguintes perguntas de negócio:

1. **Quanto investir por mês:** célula **`D10`** (*Investimento por Mês*), configurada como entrada manual (exemplo: `R$ 500,00`). Como referência complementar na seção *Configurações*, a célula **`H12`** (*Sugestão de Investimento*) calcula `30%` do salário informado em `H10` (`=$H$10*30%`, resultando em `R$ 1.500,00` para um salário de `R$ 5.000,00`).
2. **Por quantos anos:** célula **`D11`** (*Tempo Investimento (Anos)*), entrada manual em anos (exemplo: `5` anos).
3. **Qual a taxa de rendimento mensal:** célula **`D12`** (*Taxa de Rendimento*), entrada manual da taxa mensal de acumulação (exemplo: `1,079%` ao mês, ou `0,01079`).
4. **Quanto de patrimônio vai acumular:** célula **`D13`** (*Patrimônio Acumulado*), calculada automaticamente a partir do aporte mensal, do prazo em meses e da taxa mensal (exemplo: `R$ 41.888,46` em 5 anos).
5. **Quanto vai receber de dividendos por mês:** célula **`D14`** (*Dividendo Mensais*), calculada multiplicando o patrimônio acumulado pela taxa de rendimento da carteira definida em `H11` (exemplo: `R$ 418,88/mês` com rendimento da carteira de `1,0%` ao mês).

Além disso, a tabela **Evolução do Investimento** (`A18:D22`) projeta o **Patrimônio** (`C18:C22`) e o **Dividendo** (`D18:D22`) para **2, 5, 10, 20 e 30 anos**, e a seção de alocação (`F17:H22`) divide o aporte mensal entre seis tipos de FII de acordo com o perfil selecionado em **`H14`** (*Perfil*, via lista suspensa com validação de dados: `Conservador`, `Moderado` e `Agressivo`).

---


## Aplicação das fórmulas `FV` (`VF`) e `VLOOKUP` (`PROCV`)
- **`FV` (`VF`):** calcula o valor futuro em `D13` (`=FV(taxa_mensal,qtd_anos*12,-aporte)`) e nas projeções de 2 a 30 anos (`C18:C22`). Os dividendos saem da multiplicação do patrimônio pela taxa da carteira (`D14` e `D18:D22`).
- **Chave composta + `VLOOKUP` (`PROCV`):** a `Tabela de Apoio` cria a chave `Perfil-Tipo` (`=C3&"-"&D3`). Em `G17:G22`, `=VLOOKUP($H$14&"-"&F17,'Tabela de Apoio'!B2:E20,4,FALSE)` busca o percentual do perfil escolhido em `H14` e `H17:H22` calcula o valor por tipo de FII (`=aporte*G17`).

---

## Simulação de Uso
<img width="821" height="448" alt="image" src="https://github.com/user-attachments/assets/c125d520-ad2c-4f20-ac29-d187d942dc76" />
<img width="821" height="448" alt="image" src="https://github.com/user-attachments/assets/ebf968f7-f7ae-40fd-854f-087c7db2db11" />


