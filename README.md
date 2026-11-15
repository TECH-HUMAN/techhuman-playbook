# Playbook Tech Human

Distribuidor público do **Playbook Tech Human** em GitHub Pages. Este repositório mantém a automação de publicação; a fonte de conteúdo e da aplicação fica no repositório privado `TECH-HUMAN/th-new-business-model/07-playbook-site`.

**Destino configurado:** [https://playbook.techhuman.com.br/](https://playbook.techhuman.com.br/). A configuração de um domínio e um workflow não comprova, por si só, a disponibilidade atual do site.

## Onde alterar cada coisa

| Item | Local |
|---|---|
| Conteúdo, interface e dependências | Repositório canônico privado, diretório `07-playbook-site/` |
| Distribuição por GitHub Pages | [`.github/workflows/deploy-pages.yml`](.github/workflows/deploy-pages.yml) |
| Apresentação deste distribuidor | `README.md` |

O código da aplicação não é mantido em paralelo aqui. Para colaborar na fonte, solicite o acesso adequado à organização e siga as instruções do diretório canônico. Não copie estratégia, credenciais ou documentos internos para este repositório público.

## Como a publicação funciona

O workflow busca `th-new-business-model` na branch `main`, usa Node.js 22, instala com `npm ci`, executa `npm run validate`, confere o artefato e publica no ambiente `github-pages`. O acesso à fonte depende do secret `TH_NEW_BUSINESS_MODEL_DEPLOY_KEY`, configurado no GitHub; nunca coloque seu valor no README.

Os gatilhos existentes são push em `main`, execução manual pela aba Actions e sincronização agendada a cada seis horas. Uma edição de documentação também pode acionar o gatilho de push; confirme o escopo antes de integrar mudanças. Merge, build e publicação são estados distintos.

O workflow do Playbook exige `npm audit --audit-level=moderate --registry=https://registry.npmjs.org` antes da validação/build. Uma falha bloqueia a publicação.

Para validar conteúdo, trabalhe no diretório `07-playbook-site/` da fonte canônica. Este distribuidor não possui aplicação ou instalação npm independente. Confira as regras locais e os logs do workflow antes de considerar uma publicação concluída.

## Como contribuir

Leia as instruções e a documentação do projeto antes de alterar arquivos. Abra um PR com objetivo, escopo e verificações realizadas; relacione uma issue quando houver trabalho a acompanhar. Segredos, dados de clientes e informações pessoais devem permanecer nos ambientes autorizados. Os [princípios gerais da organização](https://github.com/TECH-HUMAN/.github/blob/main/CONTRIBUTING.md) complementam as regras locais.

## Sobre a Tech Human

A Tech Human conecta negócios, liderança humana, adoção de IA, pessoas e governança organizacional.

- [Site institucional](https://www.techhuman.com.br/)
- [Adoção de IA e BMAI](https://techhuman.digital/)
- [LinkedIn](https://www.linkedin.com/company/techhumanbr/)
- [Organização no GitHub](https://github.com/TECH-HUMAN)
- [Contato](mailto:contato@techhuman.com.br)
