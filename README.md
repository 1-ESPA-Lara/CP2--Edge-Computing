# Sistema de Monitoramento – Vinheria Agnello

## Discrição do projeto
Projeto acadêmico desenvolvido na FIAP com foco em monitoramento ambiental aplicado ao armazenamento de vinhos. O sistema realiza leitura contínua de temperatura, umidade e luminosidade, garantindo que as variáveis permaneçam dentro das faixas ideais de conservação. Conta com interface interativa via display (LCD ou gráfico 128x64), menus configuráveis e persistência de dados na EEPROM.

## Visão geral do projeto 
Simulação disponivel o Wokwi: https://wokwi.com/projects/445364386655015937
<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/046abb29-3b29-4406-9723-3bb7d9dd71a2" />

## Funcionalidades
- Monitoramento ambiental automatizado: mede temperatura, umidade e luminosidade em tempo real.
- Sinalização inteligente: LEDs e buzzer indicam condições normais, de alerta e críticas.
- Interface de usuário: menus interativos acessados via joystick.
- Configuração de data e hora: ajuste direto no RTC sem necessidade de computador.
- EEPROM integrada: armazenamento permanente de parâmetros ideais e logs de eventos.
- Compatibilidade dupla:
  -Simulador: LCD 16x2 (ambiente de teste).
  -Hands-on: Display gráfico ST7920 128x64 com biblioteca U8g2.

# Conceitos envolvidos
- Sensoriamento analógico e digital: leitura de sinais ambientais via DHT11 (digital) e LDR (analógico).
- Sistemas embarcados: integração de sensores, atuadores e interface gráfica em microcontrolador Arduino.
- RTC (Real Time Clock): manutenção de data e hora em tempo real, mesmo após desligamento.
- EEPROM: memória não volátil para armazenar dados de configuração e eventos críticos.
- Interface homem-máquina (IHM): interação simplificada por menus e feedback visual/sonoro.
- Mapeamento de variáveis ambientais: comparação automática entre medições e limites ideais definidos.

## Como reproduzir o projeto
1. Monte o circuito conforme o diagrama disponível na simulação do Wokwi ou na imagem de referência do repositório.
2. Faça o upload do código para o Arduino usando a Arduino IDE (arquivo da pasta /hands-on ou /simulador, conforme o display utilizado).
3. Utilize o joystick para navegar pelos menus do sistema.
4. Configure os valores mínimos e máximos de temperatura, umidade e luminosidade no menu Setup (os dados são salvos na EEPROM).
5. Ative o modo “Monitoramento” para iniciar a leitura contínua dos sensores.
6. Alertas visuais e sonoros serão acionados automaticamente quando algum valor ultrapassar os limites definidos, e os eventos serão registrados na EEPROM.

Para depuração
- Acesse Logs > Ver registros para imprimir os eventos no Monitor Serial.
- Acesse Logs > Limpar registros para resetar as flags e limpar a EEPROM.

## Componentes utilizados
- Arduino UNO
- DHT11 – sendor de temperatura e umidade
- LDR – sensor de luminosidade
- RTC DS1307 – relógio em tempo real
- EEPROM – memória não volátil integrada
- Display LCD I2C 16x2 (simulador)
- Display ST7920 128x64 (versão física, via U8g2)
- Joystick analógico (2 eixos + botão)
- LEDs: verde, amarelo e vermelho
- Buzzer 
- Fonte de alimentação 5V

## Mapa do menu (modo “tudo OK”)
1. Mudar horário – ajuste de hora, minuto, dia, mês e ano (RTC)
2. Ver status atual – exibe leituras vigentes (temperatura (T), umidade (U), luminosidade (L))
3. Ver status ideal – mostra faixas configuradas para a vinheria
Se qualquer parâmetro estiver fora do ideal, o menu é desativado e o sistema entra em modo de alerta.

## Licenças
- Bibliotecas utilizadas:
  - U8g2lib – open source (Oliver Kraus)
  - RTClib – Adafruit / BSD-like
  - DHT sensor library – Adafruit
  - LiquidCrystal_I2C – open source
  - EEPROM.h - biblioteca padrão Arduino
- Código disponível para uso educacional e demonstrações acadêmicas, mediante citação da fonte e da instituição.

## Equipe de Desenvolvimento
- Lara Mofid Essa Alssabak — RM567947
- Maria Luisa Boucinhos Franco — RM567355
- Roberta Moreira dos Santos — RM567825

## Etapa 2 do Projeto Vinheria Agnello
Nesta fase, o projeto evoluiu de um monitor de luminosidade para um sistema completo de controle ambiental, medindo temperatura, umidade e luminosidade.
Foram adicionados RTC, EEPROM e um display gráfico com menus interativos, além de LEDs e buzzer para alertas automáticos.
Essa etapa representa a integração total dos sensores e interface, tornando o sistema mais preciso, autônomo e próximo de uma aplicação real.

