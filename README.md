# Instalando o Whaticket 10.9

Esta versão está sendo lançada graças à contribuição de @LeandroReis2907, especialista em infraestrutura de TI no Brasil. Sob esse conceito, minha contribuição em conteúdo em espanhol está alinhada aos conceitos de @LeandroReis2907.

---

## 1. Acesso ao servidor VPS

Compre um servidor VPS com sistema operacional **Ubuntu 20.04** ou superior. Neste caso, o provedor [Contabo](https://contabo.com) é recomendado.

Exemplo de servidor:
```
Servidor: 62.xx4.2x0.x0
```

---

## 2. Configuração de Domínio

Você deve configurar dois subdomínios com seu provedor de domínio, como [GoDaddy](https://www.godaddy.com/) ou outro de sua escolha. Esses subdomínios devem apontar para o seu servidor VPS:
```
app.seudominio.com.br
api.seudominio.com.br
```

---

## 3. Carregue o código no GitHub

Para acelerar o processo, você pode clonar o repositório com o código-fonte do Whaticket:
```
Repositório: https://github.com/nicogueta/waticketsaas.git
```

---

## 4. Inicie a instalação no Ubuntu

1. Acesse seu servidor VPS.
2. Crie um usuário chamado `deploy` e conceda a ele permissões:
```bash
sudo adduser deploy
```
- Atribua uma senha.
- Pressione **Enter** nos campos adicionais.
3. Conceda permissões sudo ao usuário:
```bash
sudo usermod -aG sudo deploy
```
4. Encerre a sessão com:
```bash
exit
```
5. Efetue novamente o login como usuário `deploy`:
```bash
ssh deploy@seu.ip.vps
```

---

## 5. Execute a instalação

Execute o seguinte script para instalar o Whaticket:
```bash
sudo apt update && sudo apt install -y git \
&& git clone https://github.com/nicogueta/instalador-whaticket-main-v.10.0.1.git \
&& sudo chmod -R 777 instalador-whaticket-main-v.10.0.1 \
&& cd instalador-whaticket-main-v.10.0.1 \
&& sudo ./install_primaria
```

### Dados necessários durante a instalação:

- **Tipo de instalação:** `0` (Instalação)
- **Nome do banco de dados:** `seu_banco_de_dados`
- **Repositório GitHub:** `https://github.com/nicogueta/waticketsaas.git`
- **Instância/Empresa:** `coloqueumnome`
- **Valor QR:** `999`
- **Usuários online:** `999`
- **Aplicativo de subdomínio:** `app.seudominio.com.br`
- **API de subdomínio:** `api.seudominio.com.br`
- **Conexão 1:** `3000`
- **Conexão 2:** `4000`
- **Conexão 3:** `5000`

> **Observação:** a instalação pode levar entre **40 e 60 minutos** dependendo da velocidade do servidor VPS que você contratar.

---

## 6. Acesse o sistema

Após a conclusão da instalação, faça login na plataforma em:
```
app.seudominio.com.br
```

Credenciais padrão:
```
Usuário: admin@admin.com
Senha: 123456
```

---

### Instalação concluída com sucesso! 🎉
