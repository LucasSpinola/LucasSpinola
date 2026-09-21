<div align="center">

<img src="./assets/terminal.svg" width="100%" alt="Terminal Linux com o perfil de Lucas Spinola" />

<a href="https://www.linkedin.com/in/lucasspinola3/">
  <img src="https://img.shields.io/badge/LinkedIn-1c2128?style=for-the-badge&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHJlY3Qgd2lkdGg9IjI0IiBoZWlnaHQ9IjI0IiByeD0iNCIgZmlsbD0iIzBBNjZDMiIvPjxjaXJjbGUgY3g9IjciIGN5PSI2LjYiIHI9IjEuOSIgZmlsbD0iI2ZmZiIvPjxyZWN0IHg9IjUuMyIgeT0iOS42IiB3aWR0aD0iMy40IiBoZWlnaHQ9IjkuNiIgZmlsbD0iI2ZmZiIvPjxwYXRoIGQ9Ik0xMSA5LjZoMy4yVjExYy42LTEgMS44LTEuNyAzLjMtMS43IDIuNiAwIDMuNSAxLjcgMy41IDQuM3Y1LjZoLTMuNHYtNWMwLTEuMi0uMy0yLjEtMS41LTIuMXMtMS44LjktMS44IDIuMXY1SDExeiIgZmlsbD0iI2ZmZiIvPjwvc3ZnPg%3D%3D" alt="LinkedIn" />
</a>
<a href="mailto:lucasspinola3@gmail.com">
  <img src="https://img.shields.io/badge/E--mail-1c2128?style=for-the-badge&logo=gmail&logoColor=EA4335" alt="E-mail" />
</a>
<a href="https://lattes.cnpq.br/2230852814710667">
  <img src="https://img.shields.io/badge/Lattes-1c2128?style=for-the-badge&logo=googlescholar&logoColor=4285F4" alt="Currículo Lattes" />
</a>
<a href="https://orcid.org/0009-0005-9206-8452">
  <img src="https://img.shields.io/badge/ORCID-1c2128?style=for-the-badge&logo=orcid&logoColor=A6CE39" alt="ORCID" />
</a>

</div>

## ~/sobre

Estudante de Engenharia de Computação na UFRN, trabalhando com DevOps e infraestrutura. Sou estagiário de DevOps na Aiyra Engenharia de Dados e, na incubadora inPACTA (ECT/UFRN), administro o cluster Proxmox de cinco nós onde rodam mais de 20 aplicações, entre elas mais de 15 MVPs de startups incubadas, com monitoramento em Zabbix e Grafana e deploy pelo GitLab CI.

Cheguei na infraestrutura vindo do desenvolvimento: foram dois anos como dev na LogAp, com Angular, Django e Spring Boot, e quatro anos de Iniciação Científica (CNPq) em IA aplicada à educação. Nesse período criei um bot educacional no Discord e depois uma plataforma integrada ao SIGAA, que juntos já foram usados por mais de 1000 estudantes e renderam três artigos publicados.

## ~/experiencia

<details>
<summary><b>DevOps</b> · Aiyra Engenharia de Dados &nbsp;<code>estágio · 2026 → atual</code></summary>

Na Aiyra, empresa de engenharia de dados, cuido do caminho que o código percorre até produção: os ambientes onde ele roda, a esteira que o entrega e o monitoramento que avisa quando algo sai do normal.

**Ambientes e infraestrutura como código**

- Configuro e mantenho os ambientes de desenvolvimento, teste e produção descritos como código, para que possam ser recriados do mesmo jeito e as diferenças entre eles não virem bug em produção

**Entrega contínua**

- Construo e mantenho as pipelines de CI/CD, com deploy automatizado em produção
- Uso containers para rodar os serviços de apoio e as suítes de teste das aplicações, então os testes rodam sempre no mesmo ambiente, isolados da máquina de quem desenvolve

**Monitoramento e incidentes**

- Acompanho o desempenho dos sistemas com monitoramento contínuo, identifico problemas e apoio a resolução dos incidentes

</details>

<details>
<summary><b>Infraestrutura e DevOps</b> · inPACTA (ECT/UFRN) &nbsp;<code>bolsista · 2026 → atual</code></summary>

Respondo pela infraestrutura computacional da inPACTA, a incubadora da ECT/UFRN, e pela automação de implantação das aplicações. É uma infraestrutura própria: hoje são **42 containers** rodando **mais de 20 aplicações**, das quais **mais de 15 são MVPs** das startups incubadas, além dos ambientes de professores e das cargas de pesquisa que precisam de GPU. Por isso o trabalho vai do hardware ao deploy: virtualização, padronização, monitoramento, entrega contínua e segurança de acesso.

**Virtualização e cluster**

- Consolidei num cluster Proxmox VE de cinco nós os servidores que antes rodavam isolados e eram administrados um a um. Hoje tudo é gerenciado de um lugar só
- Armazenamento em ZFS e cargas em containers LXC, mais leves que máquinas virtuais para os MVPs e os serviços internos
- Integrei ao cluster um nó com GPU dedicada, compartilhada via passthrough entre containers LXC de pesquisa. Assim vários trabalhos usam a placa sem precisar de uma VM exclusiva para cada um

**Padronização de ambientes**

- Criei um template de container em Debian 12 que já nasce com Docker, agente de monitoramento, chave SSH de acesso, limites de log e localização configurados
- Criar um ambiente novo virou clonar o template: o container sobe acessível, com os logs sem risco de lotar o disco e já aparecendo no monitoramento, sem nenhuma configuração manual

**Observabilidade**

- Migrei o Zabbix do 5.4 para o 7.0 LTS e o Grafana do 9.5 para o 13, saltos que atravessam várias versões principais. Para não arriscar o monitoramento em produção, subi as versões novas em paralelo e mantive as antigas prontas como rollback
- Refiz os dashboards do Grafana numa visão única do cluster, com variáveis e repetição de painéis: o mesmo painel se replica para cada nó, então um nó novo entra no dashboard sem precisar editá-lo
- Coloquei o Uptime Kuma para acompanhar a disponibilidade dos serviços, complementando as métricas do Zabbix

**Entrega contínua e segurança**

- Mantenho o GitLab próprio da incubadora, com pipelines de CI/CD que fazem o deploy automatizado dos MVPs em produção
- Implantei o Vaultwarden como cofre de senhas da equipe, centralizando as credenciais num só lugar e com controle de quem acessa o quê

**Stack:** Proxmox VE, ZFS, LXC, Docker, Debian, Zabbix, Grafana, Uptime Kuma, GitLab CI/CD, Vaultwarden

</details>

<details>
<summary><b>Desenvolvedor</b> · LogAp Sistemas &nbsp;<code>estágio · 2024 → 2026</code></summary>

Na LogAp trabalhei em aplicações web e sistemas distribuídos passando por todas as etapas, da análise à implantação, e depois na sustentação desses sistemas em produção para clientes do setor público.

**Desenvolvimento**

- Front-end em Angular, com interfaces dinâmicas e responsivas
- Back-end em Django (Python) e em Spring Boot (Java), com APIs REST e bancos de dados relacionais
- Comunicação entre serviços com GraphQL, gRPC e RabbitMQ
- Testes automatizados das APIs

**Sustentação em produção**

- Monitoramento e análise de desempenho dos sistemas dos clientes, identificação de problemas e apoio à resolução de incidentes
- Correção de falhas, otimização de desempenho e aplicação de boas práticas de segurança

**Ambientes e entrega**

- Configuração e manutenção dos ambientes de desenvolvimento, teste e produção com infraestrutura como código
- Pipelines de CI/CD com implantação automatizada em produção
- Trabalho em equipe multidisciplinar com Scrum e Kanban

</details>

<details>
<summary><b>Iniciação Científica (CNPq)</b> · UFRN &nbsp;<code>bolsista · 2022 → 2026</code></summary>

Quatro anos de pesquisa em IA aplicada à educação na Escola de Ciências e Tecnologia, com foco em acompanhar o aprendizado da turma de forma contínua e apoiar as decisões do professor. A resposta evoluiu de um bot no Discord para uma plataforma integrada ao sistema acadêmico da UFRN.

**Monitor Bot**

- Assistente no Discord em Python, com discord.py, FastAPI e NLTK. As funcionalidades saíram de uma pesquisa qualitativa com alunos e professores
- Perguntas e respostas com PLN: a dúvida passa por remoção de stopwords e stemming e é comparada por similaridade com uma base de perguntas conhecidas
- Minitestes ao vivo, registro de presença e análise das respostas para o professor enxergar onde a turma errou
- Virou [artigo](https://periodicos.ufrn.br/casoseconsultoria/article/view/33870) em que sou primeiro autor. Na mesma linha de pesquisa, sou coautor de mais dois artigos, sobre autorregulação da aprendizagem e sobre uma ferramenta de visualização para a Educação 4.0

**Plataforma integrada ao SIGAA**

- Evolução do bot para uma plataforma web usada na disciplina de Lógica de Programação, com três formas de avaliação contínua
- **Código:** correção automática executando a resposta contra casos de teste, registrando tentativas e tempo de resolução
- **Quizzes:** múltipla escolha com modo ao vivo e participação em tempo real
- **Questões discursivas:** a resposta do aluno é comparada com a esperada por similaridade de cosseno entre representações vetoriais, e um modelo de linguagem gera retorno com nota, resumo, pontos a revisar e sugestões de estudo, com registro por aluno e por turma. O professor continua revisando o que a IA gera
- Feita com Angular, Django REST Framework, Django Channels e Redis para o tempo real, PostgreSQL, Docker e GitLab CI

**Resultado**

- Somando o bot e a plataforma, **mais de 1000 estudantes** usaram as ferramentas. Na validação formal da plataforma, com cerca de 60 alunos das turmas de laboratório, caiu o tempo de espera por retorno e a sobrecarga da monitoria

</details>

## ~/stack

<div align="center">

**Infraestrutura e DevOps**

<img src="https://skillicons.dev/icons?i=linux,debian,docker,gitlab,grafana&theme=dark" alt="Linux, Debian, Docker, GitLab, Grafana" />

<sub>+ Proxmox VE, ZFS, LXC, Zabbix, Uptime Kuma, Vaultwarden</sub>

**Backend e Dados**

<img src="https://skillicons.dev/icons?i=java,spring,py,django,fastapi,postgres,redis,rabbitmq,graphql&theme=dark" alt="Java, Spring Boot, Python, Django, FastAPI, PostgreSQL, Redis, RabbitMQ, GraphQL" />

<sub>+ gRPC, Django Channels</sub>

**Frontend**

<img src="https://skillicons.dev/icons?i=angular,ts,react&theme=dark" alt="Angular, TypeScript, React" />

</div>

<img src="./assets/contato.svg" width="100%" alt="Terminal com o contato de Lucas Spinola: lucasspinola3@gmail.com, linkedin.com/in/lucasspinola3, Lattes e ORCID" />
