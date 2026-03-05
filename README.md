# PROJETO COM ESP32-CAM PARA MONITORAMENTO 

Este projeto foi desenvolvido por **mim** no **primeiro semestre de 2024**, durante o início da minha graduação em **Análise e Desenvolvimento de Sistemas**.

A ideia do projeto foi explorar conceitos iniciais de **IoT (Internet of Things)**, integração de hardware com software e automação utilizando microcontroladores.

O sistema utiliza um **ESP32-CAM** junto com um **sensor de movimento PIR** para detectar presença no ambiente. Quando um movimento é detectado, o dispositivo captura uma imagem e envia automaticamente para o **Telegram do usuário** através de um bot.

Esse projeto foi uma das minhas primeiras experiências práticas combinando **programação, redes, automação e eletrônica**.

---

# 📷 Como funciona

O sistema funciona da seguinte forma:

1. O **sensor PIR** monitora o ambiente
2. Quando detecta movimento, envia um sinal para o **ESP32-CAM**
3. O ESP32 ativa a câmera integrada
4. Uma foto é capturada
5. A imagem é enviada automaticamente para o **Telegram do usuário**

Isso permite criar um sistema simples de **monitoramento remoto utilizando IoT**.

---

# 🧰 Hardware utilizado

* ESP32-CAM
* Sensor PIR HC-SR501
* Conversor USB para Serial
* Jumpers
* Fonte 5V
* Case feita em impressão 3D

---

# 🔌 Conexões

### Sensor PIR → ESP32-CAM

| PIR | ESP32   |
| --- | ------- |
| VCC | 5V      |
| GND | GND     |
| OUT | GPIO 13 |

O pino pode ser alterado diretamente no código caso necessário.

---

# 📂 Estrutura do Projeto

```
Deteccao-de-movimentos-ESP32
│
├── esp32_cam_telegram.ino
└── README.md
```

---

# ⚙️ Configuração

Antes de compilar o código, configure as seguintes variáveis com suas informações:

```
const char* ssid = "SEU_WIFI";
const char* password = "SENHA_WIFI";

String BOTtoken = "SEU_BOT_TOKEN";
String CHAT_ID = "SEU_CHAT_ID";
```

---

# 🤖 Criando um Bot no Telegram

1. Abra o Telegram
2. Procure por **@BotFather**
3. Execute o comando:

```
/newbot
```

4. Escolha um nome e um username para o bot
5. O BotFather irá gerar um **TOKEN de acesso**
6. Esse será o valor usado em `BOTtoken`.

---

# 🆔 Obtendo o Chat ID

1. Envie uma mensagem para o seu bot
2. Acesse no navegador:

```
https://api.telegram.org/botSEU_TOKEN/getUpdates
```

3. Procure pelo campo:

```
chat -> id
```

Esse número será utilizado como `CHAT_ID`.

---

# 💻 Configurando a Arduino IDE

1. Instale a **Arduino IDE**
2. Vá em:

```
File → Preferences
```

3. Adicione o link abaixo em **Additional Board Manager URLs**:

```
https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json
```

4. Depois vá em:

```
Tools → Board → Boards Manager
```

Instale:

```
esp32 by Espressif Systems
```

---

# 📷 Configurando a placa

Selecione a seguinte placa na IDE:

```
AI Thinker ESP32-CAM
```

---

# 📤 Upload do código

Para enviar o código ao ESP32-CAM:

1. Conecte **GPIO0 ao GND**
2. Clique em **Upload**
3. Após gravar o código:

   * Remova GPIO0 do GND
   * Aperte o botão **RST**

---

# 🚀 Funcionamento

Após inicializar:

* O ESP32 conecta ao WiFi
* O sensor PIR monitora o ambiente
* Quando um movimento é detectado:

  * Uma foto é capturada
  * A imagem é enviada automaticamente para o Telegram

---

# 📌 Possíveis melhorias futuras

Algumas melhorias que podem ser implementadas no projeto:

* Gravação de vídeo
* Armazenamento em cartão SD
* Detecção de pessoas utilizando visão computacional
* Integração com dashboard web
* Detecção de objetos suspeitos utilizando visão computacional
* 
---

# 🧠 Tecnologias utilizadas

* ESP32
* Arduino IDE
* Telegram Bot API
* Sensor PIR
* IoT

---

# 👨‍💻 Autor

**Gabriel Orlandi**

Projeto desenvolvido em **2024**, durante o primeiro semestre da graduação em **Análise e Desenvolvimento de Sistemas**, como forma de explorar conceitos iniciais de **Internet das Coisas, automação e integração entre hardware e software**.
