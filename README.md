# DINO-AI
DINO AI — Mensagens para a Direção (WhatsApp)  Formulário simples e moderno para que estudantes enviem mensagens à direção via WhatsApp. Inclui histórico local (com exportação CSV), contador de caracteres, atalhos de teclado e layout responsivo.  Stack: HTML + CSS + JavaScript puro (sem dependências)

✨ Recursos

Envio para WhatsApp com texto formatado (nome, turma e mensagem)

Histórico local (usa localStorage)

Exportar CSV dos envios

Limpar histórico com confirmação

Contador (0–500 caracteres)

Atalho: Ctrl/Cmd + Enter para enviar

Acessível: feedback visual de validação e ARIA no histórico

Responsivo: funciona bem em desktop e celular

🔧 Como usar localmente

Baixe/clon e o repositório:

git clone https://github.com/<seu-usuario>/<seu-repo>.git
cd <seu-repo>


Abra o index.html no navegador (duplo clique)

Dica: para testes mais fiéis, sirva com um servidor local:

# Python 3
python -m http.server 8080
# depois abra http://localhost:8080


Não há build nem dependências externas além da fonte do Google Fonts.

📁 Estrutura do projeto
.
├─ index.html
├─ styles.css
├─ app.js
└─ logo/
   └─ logo dino.png

🛠️ Configurações rápidas
1) Número do WhatsApp da escola

No arquivo app.js, altere a constante (apenas dígitos, com DDI+DDD):

// app.js
const NUMERO_DIRECAO = "5535997143523";


Formato: https://wa.me/<DDI+DDD+NUMERO>

Ex.: Brasil (55) + DDD (35) + número 997143523 → 5535997143523

2) Logo no topo

No index.html, o caminho já aponta para logo/logo dino.png.
Coloque sua imagem nessa pasta ou ajuste o src:

<img src="logo/logo dino.png" alt="Logo DINO AI" class="logo-img">


Atenção: evite espaços antes/depois do caminho.
Se precisar de outra dimensão, ajuste no styles.css a classe .logo-img.

🧩 Detalhes de implementação

Formatação da mensagem (negritos/ícones) está em app.js:

function formatarMensagem(nome, turma, mensagem) {
  return `*📩 Mensagem do Aluno (via DINO AI)*\n\n👤 *Nome:* ${nome}\n🏫 *Turma:* ${turma}\n💬 *Mensagem:* ${mensagem}`;
}


Histórico é persistido em localStorage (chave dinoai_hist).

Exportação CSV gera arquivo historico_dino_ai.csv em um clique.

Validação marca campos com aria-invalid="true" e exibe alerta amigável.

🔐 Privacidade

Nenhum dado é enviado a servidores do projeto.

O histórico fica somente no navegador do usuário (pode ser apagado a qualquer momento).

O envio pelo WhatsApp abre a tela de conversa do número configurado com o texto pronto.

🌐 Compatibilidade

Navegadores modernos Chromium/Firefox/Safari/Edge.

Requer JavaScript habilitado para todas as funcionalidades.

🚀 Deploy

GitHub Pages: basta publicar a branch com index.html na raiz.

Netlify / Vercel: projeto estático (sem build). Arraste e solte.

✅ Roadmap / Ideias futuras

Tema dark (fundo azul-escuro com glow combinando com a logo)

Máscara/validação de turma e nome

i18n (PT/EN)

Parametrização do template de mensagem via JSON

Quer que eu implemente o tema dark e um seletor de tema? Posso commitar um styles-dark.css e um toggle.

🤝 Contribuindo

Faça um fork do repositório

Crie uma branch: git checkout -b feat/meu-melhoria

Commit: git commit -m "feat: minha melhoria"

Push: git push origin feat/meu-melhoria

Abra um Pull Request

📄 Licença

Este projeto pode ser usado livremente para fins educacionais.
Se preferir, adicione uma licença (ex.: MIT) criando um arquivo LICENSE.

📬 Suporte

Achou um bug ou tem sugestão?
Abra uma Issue no repositório ou mande mensagem. 💚
