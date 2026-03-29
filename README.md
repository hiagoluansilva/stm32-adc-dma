# stm32-adc-dma

Aquisição simultânea de múltiplos canais analógicos utilizando ADC com DMA no STM32F4xx.

## Descrição

Projeto que demonstra a configuração do ADC em modo de varredura (scan mode) com transferência automática via DMA para um buffer na memória, liberando o CPU para outras tarefas durante a conversão.

## Hardware

- Microcontrolador: STM32F4xx

## Funcionalidades

- Conversão de múltiplos canais ADC em sequência
- Transferência DMA para buffer circular
- CPU livre durante aquisição

## Estrutura do projeto

```
ADC_multi_DMA/
├── Src/        # Código-fonte principal
├── Inc/        # Headers
├── Drivers/    # STM32 HAL
└── ADC_multi_DMA.ioc
```

## IDE

STM32CubeIDE / Atollic TrueSTUDIO

## Escola

Centro Tecnológico Liberato — Novo Hamburgo/RS
