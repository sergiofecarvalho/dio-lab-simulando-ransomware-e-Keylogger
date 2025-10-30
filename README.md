# dio-lab-simulando-ransomware-e-keylogger
Simulando um Malware de Captura de Dados Simples em Python e Aprendendo a se Proteger

📚 Documentação Completa do Projeto
🎯 Objetivo
Este projeto implementa um simulador educacional de ransomware que demonstra, em ambiente controlado, como esse tipo de malware funciona: criptografando arquivos e exigindo "resgate" para descriptografia.
⚠️ AVISO IMPORTANTE
Este código é EXCLUSIVAMENTE para fins educacionais!

✅ Use apenas em ambientes de teste isolados
✅ Nunca execute em sistemas de produção
✅ Não utilize com dados reais
❌ O uso malicioso é CRIME previsto em lei

🔧 Instalação e Configuração
1. Pré-requisitos:
   Python 3.7 ou superior

2. Instalar dependências:
   pip install cryptography

3. Executar o simulador:

   python ransomware_simulator.py
```

---

### 🏗️ Arquitetura do Projeto

#### **Componentes Principais:**

1. **`RansomwareSimulator` (Classe Principal)**
   - Gerencia todo o ciclo de vida do simulador
   - Controla criptografia/descriptografia
   - Gerencia ambiente de teste

2. **Sistema de Criptografia**
   - Utiliza `Fernet` (criptografia simétrica)
   - Algoritmo: AES-128 em modo CBC
   - Chave única gerada para cada sessão

3. **Ambiente de Teste**
   - Diretório isolado: `./test_files`
   - Arquivos simulados com conteúdo fictício
   - Totalmente separado de arquivos reais

---

### 🎮 Como Usar

#### **Fluxo de Uso Típico:**

**1. Criar Ambiente de Teste**
```
Opção 1 → Cria diretório e arquivos de teste
```

**2. Simular Ataque**
```
Opção 2 → Gera chave, criptografa arquivos, cria nota de resgate
```

**3. Descriptografar**
```
Opção 3 → Usa a chave salva para restaurar arquivos
```

**4. Visualizar Status**
```
Opção 4 → Mostra estado atual dos arquivos
```

**5. Limpar Ambiente**
```
Opção 5 → Remove todo o diretório de teste
```

---

### 📊 Exemplo de Execução
```
[*] Criando ambiente de teste...
[✓] Criados 5 arquivos de teste em './test_files'

📄 Arquivos normais (5):
  • documento_importante.txt
  • relatorio_financeiro.txt
  • notas_pessoais.txt
  • dados_projeto.txt
  • backup_config.txt

--- APÓS CRIPTOGRAFIA ---

🔒 Arquivos criptografados (5):
  • documento_importante.txt.locked
  • relatorio_financeiro.txt.locked
  • notas_pessoais.txt.locked
  • dados_projeto.txt.locked
  • backup_config.txt.locked

⚠️ Nota de resgate presente: LEIA_ME_URGENTE.txt

🔐 Detalhes Técnicos
Processo de Criptografia:

Geração de Chave

key = Fernet.generate_key()  # 32 bytes aleatórios
```

2. **Criptografia de Arquivo**
```
   Arquivo Original → Leitura → Criptografia → .locked → Deletar Original

Salvamento da Chave

Armazenada em .encryption_key.key
Em ransomware real: enviada ao atacante
Aqui: mantida local para permitir descriptografia


Processo de Descriptografia:

Carregamento da Chave

key = load_key_from_file()
```

2. **Descriptografia**
```
   Arquivo .locked → Leitura → Descriptografia → Restaurar Original → Deletar .locked
```

---

### 🛡️ Conceitos de Segurança Demonstrados

#### **1. Criptografia Simétrica**
- Mesma chave para criptografar e descriptografar
- Algoritmo forte (AES-128)
- Velocidade de processamento

#### **2. Vetor de Ataque**
- Modificação de arquivos
- Persistência de dados criptografados
- Remoção de originais

#### **3. Engenharia Social**
- Nota de resgate com urgência
- Prazo limite (pressão psicológica)
- Instruções específicas de pagamento

#### **4. Mitigações (Demonstradas)**
- Manutenção de backups
- Isolamento de sistemas
- Não pagamento de resgate

---

### 📁 Estrutura de Arquivos
```
projeto/
│
├── ransomware_simulator.py    # Script principal
│
└── test_files/                 # Criado automaticamente
    ├── documento_importante.txt
    ├── relatorio_financeiro.txt
    ├── notas_pessoais.txt
    ├── dados_projeto.txt
    ├── backup_config.txt
    │
    ├── .encryption_key.key     # Após criptografia
    └── LEIA_ME_URGENTE.txt     # Nota de resgate


    🚨 Proteção Contra Ransomware Real
Medidas Preventivas:

✅ Backups regulares em locais isolados
✅ Antivírus atualizado com proteção em tempo real
✅ Atualizações de sistema aplicadas regularmente
✅ Segmentação de rede para limitar propagação
✅ Treinamento de usuários contra phishing

Se Infectado:

🔌 Isolar imediatamente da rede
📸 Documentar o incidente (prints, logs)
👨‍💼 Contatar especialistas em segurança
🚫 NÃO pagar o resgate (sem garantias)
💾 Restaurar de backups se disponível


🎓 Aprendizados do Projeto
Conceitos Técnicos:

Criptografia simétrica (Fernet/AES)
Manipulação de arquivos em Python
Path e gestão de diretórios
Tratamento de exceções

Conceitos de Segurança:

Funcionamento de ransomware
Importância de backups
Engenharia social em ataques
Resposta a incidentes


⚖️ Aspectos Legais
No Brasil:

Lei 12.737/2012 (Lei Carolina Dieckmann): tipifica invasão de dispositivos
Art. 154-A do Código Penal: invasão de dispositivo informático
Pena: 3 meses a 1 ano de detenção + multa

Uso deste código com fins maliciosos é CRIME!

🔬 Extensões Possíveis
Para aprofundar o aprendizado:

Adicionar criptografia assimétrica (RSA)
Implementar propagação em rede (simulada)
Adicionar detecção de máquinas virtuais
Criar logs detalhados de ações
Simular diferentes famílias de ransomware


📞 Recursos Adicionais

CERT.br: https://www.cert.br/
Guia de Ransomware: Documentação sobre prevenção
Cryptography Docs: https://cryptography.io/

Este projeto é uma ferramenta educacional poderosa para entender ameaças cibernéticas e desenvolver estratégias de defesa! 🛡️
