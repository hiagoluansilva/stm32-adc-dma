# STM32 ADC Multi-Canal + DMA — 4 Canais com Sensor de Temperatura

🇧🇷 **Português** | 🇺🇸 [English](#english)

---

## Português

Aquisição multicanal de ADC via DMA no STM32F4xx: 4 canais simultâneos (CH0, CH1, CH4 e sensor interno de temperatura).

### O que faz
- Lê **4 canais ADC** simultaneamente via DMA: CH0, CH1, CH4 e sensor de temperatura interno
- Converte para tensão usando `kADC = 3.3 / 4096`
- Calcula temperatura em °C usando a fórmula do sensor interno:
  `tempC = (V25 - vtemp) / AVG_SLOPE + 25`

### Código e constantes
```c
#define NDMA       4
#define V25        0.76       // tensão do sensor a 25°C
#define AVG_SLOPE  0.0025     // V/°C (2.5 mV/°C)
#define kADC       (3.3/4096) // fator de conversão ADC

uint16_t amostras[NDMA];
uint16_t ach0, ach1, ach4, atemp;
float    vch0, vch1, vch4, tempC;
```

### Fórmula de temperatura
```
tempC = (V25 - (atemp × kADC)) / AVG_SLOPE + 25
```

### Microcontrolador
STM32F4xx — Atollic TrueSTUDIO

---

## English

Multi-channel ADC acquisition via DMA on STM32F4xx: 4 simultaneous channels (CH0, CH1, CH4, and internal temperature sensor).

### What it does
- Reads **4 ADC channels** simultaneously via DMA: CH0, CH1, CH4, and internal temperature sensor
- Converts to voltage using `kADC = 3.3 / 4096`
- Calculates temperature in °C using the internal sensor formula:
  `tempC = (V25 - vtemp) / AVG_SLOPE + 25`

### Code and constants
```c
#define NDMA       4
#define V25        0.76       // sensor voltage at 25°C
#define AVG_SLOPE  0.0025     // V/°C (2.5 mV/°C)
#define kADC       (3.3/4096) // ADC conversion factor

uint16_t amostras[NDMA];
uint16_t ach0, ach1, ach4, atemp;
float    vch0, vch1, vch4, tempC;
```

### Temperature formula
```
tempC = (V25 - (atemp × kADC)) / AVG_SLOPE + 25
```

### MCU
STM32F4xx — Atollic TrueSTUDIO
