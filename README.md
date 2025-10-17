# Decoder-to-Huawei-Log 🛡️

![Wazuh](https://img.shields.io/badge/Wazuh-4.7%2B-blue)
![Huawei](https://img.shields.io/badge/Huawei-Network%20Equipment-red)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Production%20Ready-brightgreen)

Solução completa para integração de logs de equipamentos Huawei no Wazuh.  
Inclui **decoders** e **rules** customizadas para parser estruturado de eventos, transformando logs livres em dados analisáveis para SIEM e monitoramento.


## 📋 Sobre o Projeto

Este repositório contém **decoders** e **rules customizadas** para integrar logs de equipamentos **Huawei** (switches, routers, firewalls) com o **Wazuh**, permitindo:

- ✅ Estruturação de logs livres em campos organizados  
- 🔍 Detecção de eventos de segurança e falhas  
- ⚙️ Correlação automática de incidentes  
- 🚨 Alertas inteligentes baseados em severidade  
- 📊 Dashboard pronto para visualização no Wazuh


## 📁 Estrutura do Repositório

```bash
Decoder-to-Huawei-Log/
├── decoders/
│   └── huawei_decoder.xml        # Arquivo de decodificação dos logs Huawei
├── rules/
│   └── huawei_rules.xml          # Regras de correlação e alerta
├── examples/
│   └── sample_logs.txt           # Exemplos reais de logs Huawei
└── README.md
```


## ⚙️ Instalação e Uso

### 1️⃣ Copiar arquivos para o Wazuh Manager
```bash
# Copiar decoder
sudo cp decoders/huawei_decoder.xml /var/ossec/etc/decoders/

# Copiar rules
sudo cp rules/huawei_rules.xml /var/ossec/etc/rules/
```

### 2️⃣ Validar sintaxe
```bash
sudo /var/ossec/bin/wazuh-logtest
```

### 3️⃣ Reiniciar o Wazuh Manager
```bash
sudo systemctl restart wazuh-manager
```


## 🧠 Testando o Decoder

Use o comando abaixo para testar logs de exemplo e verificar se o parser está funcionando corretamente:

```bash
sudo /var/ossec/bin/wazuh-logtest < examples/sample_logs.txt
```

A saída deve exibir os **campos decodificados** e a **regra correspondente**.


## 🧩 Compatibilidade

| Componente | Versão mínima |
|-------------|----------------|
| Wazuh Manager | 4.7+ |
| Huawei Devices | V200R019C00 e superiores |
| SO recomendado | Ubuntu 22.04 / Rocky Linux 9 |


## 🛠️ Tecnologias Utilizadas

- 🧩 **Wazuh Rules Engine**
- 🧠 **Custom Decoders XML**
- 🧾 **Regex (expressões regulares)**
- ☁️ **Logs Syslog UDP/TCP**


## 🧭 Autor

**Elder Ribeiro Storck**  
