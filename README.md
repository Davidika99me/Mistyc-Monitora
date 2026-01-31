# 📊 Mistyc Monitora - Ecossistema IoT & BI (Indústria 4.0)

O **Mistyc Monitora** é uma solução completa de telemetria industrial que integra hardware embarcado, persistência de dados em nuvem e análise de indicadores. O sistema monitora a produção em tempo real, gerencia turnos de trabalho e exporta dados para dashboards estratégicos.

---

## 🛠️ Arquitetura da Solução

O projeto opera em um fluxo de três camadas:

1.  [cite_start]**Edge Computing (Arduino Mega 2560):** Processa os sinais dos sensores, controla a lógica de produção e exibe dados locais no LCD[cite: 9, 10, 48].
2.  [cite_start]**Cloud & Storage (IoT + MySQL):** Os acionamentos dos relés e contadores de produção são enviados para um banco de dados MySQL, criando um histórico auditável de cada evento[cite: 31, 33, 45].
3.  **Intelligence (Power BI):** Os dados brutos do MySQL são tratados e visualizados em um dashboard interativo, permitindo a análise de KPIs de eficiência e volume produtivo.

---

## ✨ Funcionalidades do Firmware (C++)

* [cite_start]**Gestão de 3 Turnos:** O sistema controla automaticamente ciclos de 8 horas (28.800 segundos por turno)[cite: 41, 42].
* [cite_start]**Monitoramento de Eficiência:** Cálculo em tempo real da relação entre tempo de máquina ligada vs. tempo total[cite: 14, 40].
* [cite_start]**Controle de Atuadores:** * **Relé IN1:** Alterna estado a cada 11 segundos para sinalização de atividade[cite: 32].
    * [cite_start]**Relé IN2:** Mantém acionamento constante de 24V enquanto a máquina estiver operando[cite: 31, 54].
* [cite_start]**Persistência Crítica:** Salvamento automático na EEPROM a cada 30 segundos para evitar perda de dados em quedas de energia[cite: 44, 45].
* [cite_start]**Simulação de Falhas:** Comando via Serial para simular "apagões" e validar a resiliência do sistema[cite: 18, 25, 26].

---

## 📂 Estrutura de Pastas e Dados

* [cite_start]**`/src`**: Código-fonte C++ para Arduino Mega 2560[cite: 9].
* **`/database`**: Scripts SQL para criação das tabelas de produção e histórico.
* **`/analytics`**: Template do Power BI (.pbix) para visualização dos dados.

---

## 🔧 Configuração e Uso

1.  **Hardware:**
    * [cite_start]Conecte o LCD 16x2 ao barramento I2C (Endereço 0x27)[cite: 1].
    * [cite_start]Switch de operação no pino 10 e Botão de Reset no pino 11[cite: 1, 2].
    * [cite_start]LEDs nos pinos 8 (Verde) e 9 (Vermelho)[cite: 1, 2].
2.  [cite_start]**Integração:** Configure sua ponte IoT para enviar as variáveis `producaoTotal`, `eficiencia` e `turnoAtual` para o MySQL[cite: 52, 53].
3.  **Visualização:** Aponte o Power BI para a base de dados para gerar os gráficos de desempenho.

---

## 🔗 Demonstração e Repositório

* **Vídeo do Projeto:** [Assista no YouTube](https://youtu.be/tJ2KDcP56NU?si=b6oguV7sNTwL3kg8)
* **Código Fonte:** [GitHub - Mistyc Monitora](https://github.com/Davidika99me/Mistyc-Monitora)

---
👨‍💻 **Desenvolvido por David Moreto** - Integrando Hardware e Inteligência de Dados.
