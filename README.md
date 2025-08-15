# 📱 Interface de Monitoramento de Dados - IFECO

**Software para acompanhamento de dados do protótipo de eficiência energética da equipe IFECO.**

Este projeto foi desenvolvido como Trabalho de Conclusão de Curso para o Técnico em Informática para Internet Integrado ao Ensino Médio do IFRS - Campus Rio Grande.

## 🎯 Objetivo

Desenvolver uma interface que capture, processe e exiba dados do veículo, permitindo a otimização de desempenho em competições. [cite: 1] O sistema é composto por um hardware (ESP32) que coleta e envia os dados, um backend para processamento e armazenamento, e um aplicativo mobile para visualização.

## 📊 Funcionalidades

### ✅ Principais Recursos

  * Autenticação de usuários com JWT.
  * Coleta de dados de sensores via Bluetooth Low Energy (BLE) ou HTTP.
  * Armazenamento das informações em banco de dados MySQL.
  * Visualização de gráficos em tempo real no aplicativo mobile.
  * Simulador de dados integrado para facilitar o desenvolvimento sem o hardware.

### 🛠️ Dados Monitorados

  * Velocidade
  * Temperatura
  * Tensão
  * Corrente

### ⚡ Processamento

  * Cálculo automático de consumo em **kWh/h** com base nos dados recebidos do hardware.

## 📱 Telas do Aplicativo

| Tela | Descrição |
| :--- | :--- |
| **Principal** | Exibe a velocidade atual e o consumo instantâneo (kWh/h).  |
| **Conexão Wi-Fi** | Permite a configuração e exibe o status da conexão.  |
| **Configurações** | Oferece personalização de alertas e outros parâmetros.  |
| **Gráficos** | Apresenta a variação histórica dos dados monitorados.  |
| **Histórico** | Mantém um registro de sessões de monitoramento anteriores.  |

## 🛠️ Arquitetura e Tecnologias

#### Hardware

  * **ESP32** com Bluetooth (BLE) para envio de dados.
  * Sensores de velocidade, temperatura, tensão e corrente.

#### Backend

  * **Node.js** com **Express** para a criação da API REST.
  * **MySQL** como banco de dados.
  * **Sequelize** como ORM para abstração do banco de dados.
  * **JSON Web Tokens (JWT)** para autenticação de usuários.

#### Frontend Mobile

  * **React Native** com **TypeScript**.
  * **React Navigation** para o gerenciamento de telas.
  * **React Native Chart Kit** para a exibição de gráficos.

## ⚙️ Configuração e Execução

### 1\. Backend

```bash
# Navegue até a pasta do backend
cd backend

# Instale as dependências
npm install
```

**Banco de Dados:**

1.  Crie um banco de dados MySQL com o nome `tcc_esp32`.
2.  Configure as credenciais de acesso no arquivo `.env`, com base no arquivo `.env.example`:

<!-- end list -->

```env
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=sua_senha
DB_NAME=tcc_esp32
JWT_SECRET=sua_chave_secreta_aqui
```

**Iniciar o servidor:**

```bash
node server.js
```

### 2\. Mobile (React Native)

```bash
# Navegue até a pasta do mobile
cd mobile

# Instale as dependências
npm install
```

**Configuração:**

  * Altere a variável `API_URL` no arquivo `src/services/api.ts` para o endereço IP da máquina onde o backend está rodando.

**Executar o aplicativo:**

```bash
# Para Android
npx react-native run-android

# Para iOS
npx react-native run-ios
```

### 3\. ESP32 (Opcional)

  * Carregue o sketch `esp32_ble_json.ino` (localizado na pasta `/esp32`) no seu dispositivo ESP32.
  * O dispositivo será detectado via Bluetooth com o nome `ESP32_Sensor`.

## 👥 Autores e Orientadores

  * **Greice Braga Pereira**
  * **Pedro Henrique Rocha Oliveira**
  * **Eduardo Wenzel Brião** (Orientador)
  * **Serguei Nogueira da Silva** (Co-Orientador)
