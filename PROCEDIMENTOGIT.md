# Passo a Passo para Trabalhar em Equipe no GitHub

## 1. Configuração Inicial

Clone o repositório: Certifique-se de que todos têm o projeto localmente.

```sh
git clone <URL-do-repositório>
```

Entre no diretório:

```sh
cd nome-do-repositório
```

Defina a branch principal como base: Geralmente é main ou master. Confirme com:

```sh
git checkout main
```

## 2. Crie uma Branch para Sua Tarefa

Para cada nova funcionalidade ou correção, crie uma branch com um nome descritivo:

```sh
git checkout -b nome-da-tarefa
```

Exemplo: `git checkout -b adiciona-login-usuario`.

Dica: Use nomes que indiquem o propósito (ex.: `fix-bug-botao`, `feature-cadastro`).

## 3. Trabalhe na Sua Tarefa

Faça suas alterações no código.

Commit frequente: Divida o trabalho em pequenos commits com mensagens claras:

```sh
git add .
git commit -m "adiciona validacao idade maxima"
```

Envie para o GitHub: Suba suas mudanças para a branch remota:

```sh
git push origin nome-da-tarefa
```

## 4. Mantenha Sua Branch Atualizada

Antes de continuar ou finalizar, synchronize com a branch principal:

```sh
git pull origin main
```

Se houver conflitos, resolva manualmente nos arquivos indicados, depois confirme:

```sh
git add <arquivo-conflitante>
git commit
```

## 5. Crie um Pull Request (PR)

Vá ao GitHub, na aba "Pull Requests", e clique em "New Pull Request".

Selecione sua branch (`nome-da-tarefa`) e a branch principal (`main`) como destino.

Descreva o que você fez no PR (ex.: "Adiciona função de login com validação").

Peça revisão: Marque colegas para revisar o código.

## 6. Revise e Resolva Feedback

Se a equipe sugerir mudanças, edite localmente na mesma branch:

```sh
git add .
git commit -m "Ajusta validação conforme feedback"
git push origin nome-da-tarefa
```

O PR atualiza automaticamente com os novos commits.

## 7. Faça o Merge

Após aprovação, peça ao PO e ao Scrum Master clicar em "Merge Pull Request".

Delete a branch no GitHub após o merge.

Localmente, atualize sua cópia:

```sh
git checkout main
git pull origin main
git branch -d nome-da-tarefa
```

## 8. Repita o Ciclo

Para a próxima tarefa, volte ao passo 2 e crie uma nova branch.

## Boas Práticas para Compartilhar com a Equipe

- **Comunicação**: Avisem no grupo (ex.: WhatsApp, Discord) antes de mexer em algo importante ou na branch principal.
- **Padrão de Nomenclatura para branch**: (ex.: `feature/nome`, `bugfix/nome`).
  - **Tipos**:
    - `feature`: Nova funcionalidade.
    - `bugfix`: Correção de bug.
    - `hotfix`: Correção urgente na branch principal.
    - `docs`: Alterações em documentação.
    - `test`: Adição ou ajuste de testes.
- **Commits Claros**: Usem mensagens que expliquem o que foi feito (ex.: "Corrige erro 404 na rota X").
- **Evitem acentuações em commits**: Evitem usar acentuações em commits, é uma boa prática, mas não é obrigatório.
- **Resolvam Conflitos Juntos**: Se alguém tiver dificuldade, peça ajuda para resolver conflitos em dupla.

## Exemplo de Fluxo Simples

Carollina quer adicionar um botão:

```sh
git checkout main
git pull origin main
git checkout -b feature/saldodevedor-price
```

[Faz as mudanças]

```sh
git add . && git commit -m "adiciona calculo de saldo devedor atualizado tabela price"
git push origin feature/saldodevedor-price
```

Cria PR no GitHub, equipe revisa, faz merge.

Carollina atualiza:

```sh
git checkout main && git pull origin main
```
