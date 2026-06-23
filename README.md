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

## Como usar

1. Abra firmware/main.ino na Arduino IDE
2. Instale as bibliotecas: WebSocketsServer (by Markus Sattler) e ArduinoJson
3. Selecione a placa ESP32 Dev Module
4. Faça o upload
5. Conecte ao Wi-Fi Comedouro-ESP32 — senha: 12345678
6. Abra dashboard/index.html no navegador
7. Digite o IP 192.168.4.1 e clique em Conectar

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

## API WebSocket

{"cmd": "motor",    "motor": "A", "speed": 75, "dir": "FWD"}
{"cmd": "estop"}
{"cmd": "gpio",     "pin": 2,     "state": 1}
{"cmd": "joystick", "x": 30,      "y": 60}

---

## Estrutura do projeto

comedouro-esp32/
├── firmware/
│   └── main.ino
├── dashboard/
│   └── index.html
└── README.md

---

Desenvolvido por Gabriel
