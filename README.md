<img width="1585" height="579" alt="image" src="https://github.com/user-attachments/assets/e496c5cf-6fbc-420b-a473-c6432773db5c" />

# Postagem-grupos-via-whatsapp
Automação desenvolvida no n8n para envio programado de conteúdos via WhatsApp utilizando Evolution API e Google Sheets como banco de dados

## Fluxo do Processo

O fluxo é dividido em três seções principais: **Busca de Conteúdo**, **Formatação** e **Envio e Controle de Status**.

### 1. Busca de Conteúdo
- **Gatilho agendado:** Executa todos os dias às 09:00.  
- **Pegando conteúdo:** Lê a planilha `Postagem Whatsapp` filtrando apenas linhas com status "Pendente".  
- **Pega um conteúdo:** Limita a execução para uma postagem por vez, evitando duplicações.

> Este bloco garante que apenas uma postagem seja processada por vez, evitando envios duplicados.

### 2. Formatação
- **Postagem:** Monta o corpo do texto unindo conteúdo e link da planilha.  
- **Lista grupos:** Define manualmente os IDs dos grupos de WhatsApp para onde a mensagem será enviada.

> Esses blocos preparam a mensagem para envio, incluindo formatação e definição de destinatários.

### 3. Envio e Controle de Status
- **Envia uma por vez:** Separa a lista de grupos para enviar individualmente via API do Evoluttion.  
- **Envio postagem:** Faz o envio real da mensagem.  
- **Marca enviado:** Atualiza a planilha com o status "Enviado" usando o ID da linha como referência.

> Essa etapa garante que cada mensagem seja enviada de forma controlada e que o status seja atualizado corretamente.

## Tecnologias Utilizadas
- Planilhas Google (Google Sheets)  
- API Evoluttion para envio de mensagens WhatsApp  
- Ferramenta de automação de workflow 

## Observações
- Certifique-se de ter os IDs dos grupos de WhatsApp configurados corretamente.  
- O gatilho agendado só processa postagens com status "Pendente".  
- Cada postagem é enviada individualmente para evitar bloqueios ou spam no WhatsApp.

