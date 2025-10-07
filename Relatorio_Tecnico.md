# RELATÓRIO DE TESTE DE FORÇA BRUTA (RESUMO EXECUTIVO)

**Classificação:** CONFIDENCIAL  
**Data do Teste:** Outubro 2024  
**Alvo:** Metasploitable 2 (192.168.56.101)  
**Analista:** Daniel Anderson  
**Repositório:** [github.com/DanielAndersonTI/kali-medusa-brute-force](https://github.com/DanielAndersonTI/kali-medusa-brute-force)

## ⚠️ SUMÁRIO DE RISCOS

| Métrica | Classificação | Detalhe |
|---------|---------------|---------|
| **Risco Geral** | 🔴 CRÍTICO | 9.2/10 (CVSS) |
| **Status do Alvo** | 🔴 Comprometido | 100% dos serviços testados foram explorados com sucesso |
| **Tempo de Comprom** | 🟡 1.5 segundos | Demonstra ausência total de controles de segurança (Rate Limiting) |
| **Causa Raiz** | 🔴 Credenciais fracas | Reutilização da senha `msfadmin:msfadmin` (Usuário igual à Senha) |

## 🔍 ACHADOS E IMPACTO TÉCNICO

### 1. Serviço FTP (Porta 21)
**Vulnerabilidade:** Acesso via força bruta e Backdoor Crítica (CVE-2011-2523) no vsftpd 2.3.4  
**Tempo de Comprom:** 2.3 segundos  
**Credencial Encontrada:** `msfadmin:msfadmin`  
**Impacto:** Acesso completo a arquivos do sistema, possibilidade de obtenção de Shell Root com a senha `:)`

### 2. Serviço SMB (Porta 445)
**Vulnerabilidade:** Acesso privilegiado via força bruta (ADMIN$)  
**Tempo de Comprom:** 0.8 segundos  
**Credencial Encontrada:** `msfadmin:msfadmin` (Reutilização da senha do FTP)  
**Impacto:** Controle total sobre recursos de rede (compartilhamentos) e potencial para ataques laterais

### 3. Falhas de Política
**Políticas de Senha:** Inexistentes (senha idêntica ao usuário, sem complexidade e reutilizada)  
**Controles de Acesso:** Sem limite de tentativas (rate limiting) ou bloqueio de contas (lockout)

## 📈 TÁTICAS MITRE ATT&CK

O ataque explorou diretamente a falha de credencial, caracterizando:

- **Tática:** Credential Access (T1110 - Brute Force)
- **Tática:** Initial Access (T1078 - Valid Accounts)

## 💰 IMPACTO NO NEGÓCIO

O risco de comprometimento resulta em um prejuízo estimado em **R$ 650.000+** devido a:

- **Vazamento de Dados** (Via FTP)
- **Paralisação Operacional** (Comprometimento da rede via SMB)
- **Multas Regulatórias** (Violação de LGPD/GDPR)

## 🛡️ PLANO DE MITIGAÇÃO

### 🔴 Ações Imediatas (24h)
- **ALTERAR CREDENCIAIS:** Resetar imediatamente todas as senhas fracas
  ```bash
  # Nova Senha Exemplo: M1nhaS3nh@Sup3rF0rt3!2024
  passwd msfadmin