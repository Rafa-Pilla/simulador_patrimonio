<img width="831" height="204" alt="image" src="https://github.com/user-attachments/assets/6981b057-9c29-4894-9606-2e9d15f7b387" />

# Oinc — Simulador de Patrimônio (Excel)

Ferramenta desenvolvida no Excel para simular investimentos mensais em Fundos Imobiliários (FIIs), projetar o patrimônio acumulado e os dividendos mensais em diferentes horizontes de tempo e distribuir o aporte mensal entre seis tipos de FII conforme o perfil de investidor.

> **Aviso:** Os valores, percentuais e configurações presentes nesta planilha são meramente ilustrativos e de exemplo, não constituindo recomendação de investimento.

---


## Perguntas Respondidas e Onde Encontrar Cada Resposta

Na aba **`Simulador de Patrimônio`**, a ferramenta responde as seguintes perguntas de negócio:

1. **Quanto investir por mês:** *Investimento por Mês* diz respeito ao valor separado para o investimento, configurada como entrada manual.  Como referência complementar na seção *Configurações*, a célula *Sugestão de Investimento* calcula `30%` do salário informado.
2. **Por quantos anos:** *Tempo Investimento (Anos)* entra de forma manual, mas para além disso, a tabela **Evolução do Investimento** projeta o **Patrimônio** e o **Dividendo** para **2, 5, 10, 20 e 30 anos**.
3. **Qual a taxa de rendimento mensal:** *Taxa de Rendimento*, entrada manual da taxa mensal de acumulação.
4. **Quanto de patrimônio vai acumular:** *Patrimônio Acumulado* calculada automaticamente a partir do aporte mensal, do prazo em meses e da taxa mensal.
5. **Quanto vai receber de dividendos por mês:** *Dividendo Mensais* é calculado multiplicando o patrimônio acumulado pela taxa de rendimento da carteira definida.

A seção de alocação divide o aporte mensal entre seis tipos de FII de acordo com o perfil selecionado (lista suspensa com validação de dados: `Conservador`, `Moderado` e `Agressivo`).

---


## Aplicação das fórmulas `FV` (`VF`) e `VLOOKUP` (`PROCV`)
- **`FV` (`VF`):** calcula o valor futuro (`=FV(taxa_mensal,qtd_anos*12,-aporte)`) e nas projeções de 2 a 30 anos. Os dividendos saem da multiplicação do patrimônio pela taxa da carteira.
- **Chave composta + `VLOOKUP` (`PROCV`):** a `Tabela de Apoio` cria a chave `Perfil-Tipo`. Em seguida é aplicado a fórmula `=VLOOKUP()` que busca o percentual do perfil escolhido e calcula o valor por tipo de FII.


