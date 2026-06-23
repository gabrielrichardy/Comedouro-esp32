# Comedouro ESP32

Sistema de controle de motor DC via ESP32 com dashboard web em tempo real.

---

## Hardware utilizado

- ESP32 Dev Module
- Driver BTS7960B
- Motor DC 12V (parafusadeira Stanley SCD12)
- Fonte DC 12V 7A

---

## Mapeamento de pinos

| Pino ESP32 | Driver BTS7960B | Função          |
|------------|-----------------|-----------------|
| GPIO 25    | RPWM            | PWM Motor A     |
| GPIO 26    | IN1             | Direção Motor A |
| GPIO 27    | IN2             | Direção Motor A |
| GPIO 13    | LPWM            | PWM Motor B     |
| GPIO 14    | IN3             | Direção Motor B |
| GPIO 12    | IN4             | Direção Motor B |
| GND        | GND             | Terra comum     |
| 5V         | VCC             | Alimentação     |

---

## Alimentação

Fonte 12V (+) → B+ do BTS7960B
Fonte 12V (-) → B- do BTS7960B e GND do ESP32
BTS7960B M+  → Motor (fio 1)
BTS7960B M-  → Motor (fio 2)

---

## Funcionalidades

- Controle de velocidade PWM (0–100%) por motor
- Direção FWD / REV individual
- Joystick direcional com controle diferencial
- Controle de pinos GPIO
- Telemetria em tempo real (CPU, RAM, temperatura, uptime)
- Parada de emergência
- Monitor serial no navegador

---

Desenvolvido por Gabriel
