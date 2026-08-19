# 🍗 Assadão do Carioca — Sistema de Gestão

Sistema web completo para gestão de reservas, estoque, pagamentos, estatísticas e pedidos online dos clientes do **Assadão do Carioca**.

**Stack:** Node.js 20 · Express · PostgreSQL  
**Hospedagem:** Render.com  
**URL Admin:** https://assadao.onrender.com  
**URL Reservas (pública):** https://assadao.onrender.com/reserva

---

## 📱 Funcionalidades

### Painel Administrativo

Painel protegido por senha para gerenciamento da operação.

- **Nova Reserva** — cadastro pelo atendente com nome, telefone, itens, quantidades, preços e forma de pagamento
- **Reservas** — visualização dos pedidos pendentes
- **Histórico** — pedidos pagos e cancelados, agrupados por data
- **Estatísticas** — análise de vendas, quantidade de produtos vendidos e receita por período
- **Estoque** — controle de estoque por data de venda
- **Abatimento automático** — redução do estoque conforme os pedidos são registrados
- **Devolução automática** — retorno do estoque em caso de cancelamento
- **Exportação CSV** — download dos dados de vendas no dispositivo do administrador
- **Exportação PDF** — geração e download de relatório de vendas
- **Autenticação** — acesso administrativo protegido por senha
- **Controle de sessões** — autenticação por token

### Página Pública de Reservas `/reserva`

- Acesso sem login
- Link direto para clientes finais
- Exibe as datas disponíveis
- Exibe os produtos disponíveis e respectivos estoques
- Fluxo simplificado para realização do pedido
- Cadastro de nome e telefone
- Abatimento automático do estoque ao confirmar a reserva
- Confirmação do pedido após o registro
- Interface responsiva para celular
- Preview para compartilhamento em redes sociais e WhatsApp

---

## 🍗 Produtos

O sistema está preparado para trabalhar com os produtos comercializados pelo Assadão do Carioca.

### Produtos principais

| Produto | Unidade | Preço |
|---|---:|---:|
| Frango Assado | unidade | R$ 60,00 |
| Frango Assado Recheado | unidade | R$ 65,00 |
| Costela Bovina | kg | R$ 80,00 |

Os produtos podem ser controlados individualmente no estoque conforme a configuração da operação.

---

## 🔐 Acesso e Segurança

- Login por senha única configurada através de variável de ambiente
- Senha armazenada no ambiente do servidor, não no código do navegador
- Token de sessão salvo no navegador
- Rotas administrativas protegidas por autenticação
- Página `/reserva` pública e isolada dos dados administrativos
- Rate limit nas rotas de login
- Rate limit nas rotas públicas
- Sessão invalidada ao sair do sistema

### Variável de ambiente obrigatória

```text
APP_PASSWORD
