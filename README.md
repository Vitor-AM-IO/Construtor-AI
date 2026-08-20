# 🏗️ Construtor

Um agente que **cria projetos do zero** a partir de uma descrição em texto. Você
escreve o que o projeto deve fazer, escolhe a linguagem, e ele **planeja os
arquivos e gera tudo** — pronto pra baixar e rodar.

Cria projetos em **Python, Java, PHP** e **Web (HTML/CSS/JS)**.

> Este é o "irmão" do Dr. Código: enquanto o Dr. Código **revisa** código, o
> Construtor **cria** código.

---

## Como funciona

1. Você descreve o projeto (uma lista do que ele deve fazer).
2. O agente **planeja** a estrutura (quais arquivos criar).
3. Ele **gera cada arquivo**, coerente com o todo.
4. Você **baixa o `.zip`** do projeto (ou ele salva numa pasta, pelo terminal).

É um MVP: funciona muito bem em projetos pequenos e bem descritos (sites,
scripts, programinhas, APIs simples). Projetos grandes e complexos ainda pedem
ajustes manuais.

## Instalação

```bash
git clone <seu-repo>.git
cd construtor
pip install .
```

Configure a chave (igual ao Dr. Código): copie `.env.example` para `.env` e
preencha, ou deixe o `start.py` perguntar na primeira vez.

## Usar pela interface (fácil)

```bash
python start.py
```

Abre uma página no navegador: você escreve a descrição, escolhe a linguagem,
clica em **Criar projeto** e baixa o `.zip`.

## Usar pelo terminal

```bash
# descrição direto no comando
construtor "uma agenda de contatos no terminal, que adiciona, lista e apaga" --lang python

# ou deixe ele perguntar a descrição
construtor --lang php --out ./meu-site
```

Opções: `--lang python|java|php|web`, `--out <pasta>`, `--provider`, `--model`.

## Configurar / trocar a IA (na própria tela)

Não precisa editar arquivo nem reinstalar nada. Na página, clique em
**⚙️ Configurar IA**: escolha o provedor (Anthropic, Groq, Ollama…), cole a chave
(se precisar) e o modelo, e clique em **Salvar**. Pronto — dá pra **trocar quando
quiser**, e ele lembra na próxima vez.

- O **Ollama** é **detectado automaticamente** se estiver rodando.
- Sua chave fica **só no seu PC** (arquivo `.env`), nunca sai dali, e a tela
  mostra só o começo/fim dela. Veja [SECURITY.md](SECURITY.md).

## Economia / provedores

Igual ao Dr. Código: funciona com Anthropic, OpenAI, Groq, DeepSeek… e **Ollama
local (grátis)**. Basta configurar no `.env` (`CONSTRUTOR_PROVIDER=ollama`).
Cada projeto cria até 12 arquivos, para controlar o custo.

## Licença

MIT. Criado por Vitor (@Vitor-AM-IO).
