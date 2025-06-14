# Terraform Hello World 🧱

Este projeto é um exemplo mínimo de uso do Terraform, projetado para ajudar a entender os conceitos fundamentais da ferramenta — usando um recurso local (`local_file`) para criar um arquivo `hello.txt`.

Projeto criado usando o passo a passo criado neste [chat com o ChatGPT](https://chatgpt.com/g/g-p-6846f371f32481919861afebb43aca4e-terraform/c/68470069-3b64-800e-851e-5077fdb41c9f)

---

## 📂 Estrutura do Projeto

```bash
terraform-hello/
├── main.tf             # Recurso principal: cria o arquivo hello.txt
├── variables.tf        # Declaração da variável 'target'
├── terraform.tfvars    # Valores da variável (opcional)
├── output.tf           # Exibe o conteúdo gerado no final do apply
└── hello.txt           # Arquivo gerado após o apply
````

---

## 🚀 Objetivo

Demonstrar:

* Uso de providers
* Declaração e uso de variáveis
* Geração de recursos locais
* Interpolação de strings
* Ciclo completo: `init`, `plan`, `apply`, `destroy`

---

## 📦 Requisitos

* [Docker](https://www.docker.com/) instalado e configurado
* Alias para rodar Terraform em container:

```bash
alias tf='docker run --rm -i -e TF_VAR_target -v $(pwd):/workspace -w /workspace hashicorp/terraform:1.12'
```

> Esse alias permite executar o Terraform sem instalá-lo diretamente, com suporte a variáveis de ambiente.

---

## ⚙️ Uso

### 1. Inicializar o projeto

```bash
tf init
```

### 2. Aplicar a infraestrutura (modo interativo)

```bash
tf apply
```

### 3. Aplicar com variável de ambiente

```bash
export TF_VAR_target="Valdemar"
tf apply
```

### 4. Aplicar com valor via CLI

```bash
tf apply -var="target=Val CLI"
```

### 5. Ver o resultado

```bash
cat hello.txt
# Hello, Val CLI!
```

---

## 🔁 Destruir os recursos

```bash
tf destroy
```

---

## 🧪 Testes

Você pode alterar o valor da variável `target` em:

* `terraform.tfvars`
* Variável de ambiente `TF_VAR_target`
* Linha de comando `-var="..."`

---

## 📄 Licença

MIT — livre para uso, modificação e distribuição.

---

## 🤝 Contribuições

Pull requests são bem-vindos para melhorar exemplos, modularização, ou adicionar suporte a outros providers.

```

Se quiser adaptar para Markdown de Obsidian ou incluir badges (ex: Terraform Registry, Docker, MIT License), posso complementar também. Deseja isso?
```
