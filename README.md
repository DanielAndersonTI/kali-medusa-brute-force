# 🔐 Kali Medusa Brute Force - Projeto de Segurança Ofensiva

![Kali Linux](https://img.shields.io/badge/Kali-Linux-557C94?style=for-the-badge&logo=kalilinux&logoColor=white)
![Medusa](https://img.shields.io/badge/Medusa-Brute_Force-FF6B6B?style=for-the-badge)
![Metasploitable](https://img.shields.io/badge/Metasploitable-Vulnerable_Lab-8B4513?style=for-the-badge)

Projeto prático de testes de força bruta em ambiente controlado, demonstrando técnicas de segurança ofensiva e medidas defensivas.

## 📋 Visão Geral

Este projeto simula ataques de força bruta contra serviços de rede vulneráveis, utilizando Kali Linux e a ferramenta Medusa contra o ambiente Metasploitable 2. O objetivo é entender vulnerabilidades comuns e implementar medidas de mitigação eficazes.

## 🎯 Resultados Principais

| Serviço | Status | Tempo de Comprometimento | Credencial Encontrada |
|---------|--------|-------------------------|---------------------|
| **FTP (21)** | ✅ Comprometido | 2.3 segundos | `msfadmin:msfadmin` |
| **SMB (445)** | ✅ Comprometido | 0.8 segundos | `msfadmin:msfadmin` |

## 🛠️ Tecnologias Utilizadas

- **Kali Linux 2024.1** - Plataforma de pentest
- **Medusa 2.3** - Ferramenta de força bruta
- **Metasploitable 2** - Ambiente vulnerável
- **Nmap 7.95** - Scanner de rede
- **VirtualBox** - Virtualização


