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

Estudante de Engenharia de Computação na UFRN, trabalhando com DevOps e infraestrutura. Sou estagiário de DevOps na Aiyra Engenharia de Dados, onde cuido dos ambientes de desenvolvimento, teste e produção com infraestrutura como código, das pipelines de CI/CD e do monitoramento das aplicações.

Fui responsável pela infraestrutura da inPACTA, a incubadora da ECT/UFRN, onde professores, alunos e startups dependem dos mesmos servidores. Estruturei um cluster Proxmox VE de cinco nós com ZFS e containers LXC, trazendo para dentro dele servidores que antes rodavam isolados, entre eles um com GPU NVIDIA dedicada à pesquisa, cujo passthrough precisou ser preservado sem derrubar o trabalho de quem usava. Para parar de configurar ambiente na mão, criei um template Debian com Docker, agente de monitoramento e limites de log já prontos: um ambiente novo passou a sair de um único clone, já monitorado. No fim, eram 42 containers servindo mais de 20 aplicações, entre elas mais de 15 MVPs de startups incubadas.

Implantei o Zabbix 7.0 LTS com Grafana por cima, num dashboard único com todos os nós lado a lado e alertas por e-mail. Foi por ele que apareceram problemas que ainda não davam sinal, como um container de produção perto de lotar o disco e o ZFS consumindo memória sem limite. Também entraram cofre de senhas com Vaultwarden, acompanhamento de disponibilidade com Uptime Kuma, acesso às aplicações pelo Nginx Proxy Manager com certificados automáticos, backups no Proxmox Backup Server e deploy dos MVPs por pipelines de CI/CD no GitLab. A parte menos visível foi revisar os acessos servidor por servidor, conferindo chaves SSH, credenciais e permissões, e migrando as senhas para o cofre.

Cheguei na infraestrutura vindo do desenvolvimento: foram dois anos como dev na LogAp, com Angular no front, Django e Spring Boot no back, e sustentação de sistemas em produção de clientes do setor público. Em paralelo, quatro anos de Iniciação Científica do CNPq em IA aplicada à educação, onde criei um bot educacional no Discord e depois uma plataforma integrada ao SIGAA para avaliação contínua, usados por mais de 1000 estudantes e com três artigos publicados.

## ~/stack

<div align="center">

**Infraestrutura e DevOps**

<img src="https://skillicons.dev/icons?i=linux,debian,docker,gitlab,grafana&theme=dark" alt="Linux, Debian, Docker, GitLab, Grafana" />

<img src="./assets/icons-infra.svg" alt="Proxmox VE, OpenZFS, LXC, Zabbix, Nginx Proxy Manager, Uptime Kuma, Vaultwarden" />

**Backend e Dados**

<img src="https://skillicons.dev/icons?i=java,spring,py,django,fastapi,postgres,redis,rabbitmq,graphql&theme=dark" alt="Java, Spring Boot, Python, Django, FastAPI, PostgreSQL, Redis, RabbitMQ, GraphQL" />

<img src="./assets/icons-backend.svg" alt="gRPC" />

**Frontend**

<img src="https://skillicons.dev/icons?i=angular,ts,react&theme=dark" alt="Angular, TypeScript, React" />

</div>

<img src="./assets/contato.svg" width="100%" alt="Terminal com o contato de Lucas Spinola: lucasspinola3@gmail.com, linkedin.com/in/lucasspinola3, Lattes e ORCID" />
