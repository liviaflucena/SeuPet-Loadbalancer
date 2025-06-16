# 🌐 Projeto AplicacaoPWeb2 - Load Balancer com NGINX e Docker Compose

Este projeto implementa um Load Balancer com NGINX, balanceando 5 nós de uma aplicação ReactJS utilizando o algoritmo de Round Robin. Toda a orquestração dos containers é realizada via Docker Compose.

---

## 🚀 Estrutura do Projeto

- \`build/\` — aplicação React compilada
- \`nginx.conf\` — configuração principal do NGINX (load balancer)
- \`default.conf\` — configuração dos nodes para servir os arquivos estáticos
- \`docker-compose.yml\` — orquestração dos containers
- \`README.md\` — documentação completa do projeto

---

## ⚙️ Como executar

### 1️⃣ Gere o build da sua aplicação React

Dentro do seu projeto React (\`~/SeuPet-1\`):

\`\`\`bash
npm install
npm run build
mv dist build
\`\`\`

### 2️⃣ Copie a pasta \`build/\` para o diretório deste repositório

\`\`\`bash
cd ~/SeuPet-Loadbalancer
cp -R ~/SeuPet-1/build .
\`\`\`

### 3️⃣ Execute o projeto com Docker Compose

\`\`\`bash
docker-compose up --build
\`\`\`

A aplicação estará acessível em \`http://localhost\`.

---

✅ Pronto! Load Balancer funcional com Docker e NGINX.

---

## 🔧 Detalhes técnicos

- O algoritmo de balanceamento de carga é Round Robin (padrão do NGINX).
- Preservação do IP real do cliente com \`proxy_set_header X-Real-IP\` e \`X-Forwarded-For\`.
- Utilização de volumes do host para as configurações \`nginx.conf\` e \`default.conf\`.
