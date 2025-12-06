# 📱 Automação de Testes Mobile com Maestro

![Maestro](https://img.shields.io/badge/-Maestro-black?style=for-the-badge&logo=maestro&logoColor=white)
![Android](https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)
![iOS](https://img.shields.io/badge/iOS-000000?style=for-the-badge&logo=ios&logoColor=white)
![YAML](https://img.shields.io/badge/YAML-CB171E?style=for-the-badge&logo=yaml&logoColor=white)

Este repositório reúne estratégias de automação de testes mobile utilizando o framework **Maestro**. O projeto demonstra desde fluxos simples em aplicações de demonstração até estruturas avançadas testando aplicativos reais como a **Wikipedia**.

## 🚀 Destaques do Projeto

O repositório está dividido em duas abordagens principais:

### 1. Wikipedia Advanced (`/wikipedia-android-advanced`)
Uma suíte de testes robusta aplicada ao app oficial da Wikipedia, demonstrando:
- **Page Object Pattern (Adaptado):** Organização de fluxos por funcionalidades (`auth`, `dashboard`, `onboarding`).
- **Scripts Auxiliares:** Uso de JavaScript para gerar credenciais dinâmicas (`generateCredentials.js`) e buscar usuários (`fetchTestUser.js`).
- **Massa de Dados:** Testes com dados dinâmicos para login e cadastro.
- **Fluxos Complexos:** Validação de *Feed*, *Salvos* e *Busca*.

### 2. Demo Apps & Conceitos Fundamentais (Raiz)
Testes focados na validação de componentes e fluxos essenciais em apps de treino (QAzando/SauceLabs):
- **E2E Completo:** Login (`e2e/login.yaml`) e Fluxo de Pedido (`e2e/pedido.yaml`).
- **Reutilização de Código:** Uso de `runFlow` para modularizar o *Onboarding* (`subflows/onboarding-android.yaml`).
- **Cross-Platform:** Exemplos de fluxos rodando em Android e iOS.

## 🛠️ Tecnologias

- **Maestro**: Framework de automação (simples, rápido e resiliente).
- **YAML**: Definição declarativa dos fluxos de teste.
- **JavaScript**: Scripts de apoio para lógica complexa.
- **Android Debug Bridge (ADB)**: Interação com emuladores.

## 📂 Estrutura do Repositório

├── wikipedia-android-advanced/  # 🏆 Projeto Principal (Wikipedia)
│   ├── auth/                    # Fluxos de autenticação
│   ├── dashboard/               # Testes da tela principal
│   ├── onboarding/              # Testes de boas-vindas
│   └── scripts/                 # Scripts JS auxiliares
├── e2e/                         # Testes End-to-End (Demo Apps)
├── subflows/                    # Fluxos reutilizáveis (Login, Setup)
├── *.yaml                       # Fluxos de execução rápida
└── *.apk                        # Apps alvo dos testes (para facilidade de execução)

## ▶️ Como Rodar

### Pré-requisitos
1. Instale o [Maestro CLI](https://maestro.mobile.dev/).
2. Tenha um Emulador Android (ou Simulador iOS) rodando.
3. Instale o app alvo no emulador:
   
   # Para os apps de demonstração
   adb install qazando.apk
   
   # Para a Wikipedia (Necessário extrair ou baixar da PlayStore)
   adb install sample.zip/Wikipedia.app 
   

### Executando os Testes

**Para rodar o projeto da Wikipedia:**

maestro test wikipedia-android-advanced/run-test.yml


**Para rodar os fluxos de demonstração:**

maestro test android-flow.yaml


**Para rodar um fluxo específico:**

maestro test e2e/login.yaml


---
Desenvolvido por **Thiago Linhares** [LinkedIn](https://www.linkedin.com/in/thiagolinharesm/)
