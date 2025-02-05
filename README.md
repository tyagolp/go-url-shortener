# url-shortener

## Descrição

**url-shortener** é uma aplicação desenvolvida em **Go** para encurtamento de URLs. Ela utiliza o framework **go-chi** para gerenciar as rotas de forma eficiente e modular.

## Recursos

- Encurtamento de URLs com hash exclusivo
- Redirecionamento para a URL original
- API RESTful para integração
- Validação de URLs
- Armazenamento em **map[string]string** (sem uso de banco de dados)

## Tecnologias Utilizadas

- **Go** (Golang)
- **go-chi** (roteamento)

## Instalação e Uso

### 1. Clonar o repositório

```sh
git clone https://github.com/tyagolp/go-url-shortener.git
cd go-url-shortener
```

### 2. Instalar as dependências

```sh
go mod tidy
```

### 3. Executar a aplicação

```sh
go run main.go
```

A API estará rodando em `http://localhost:8080` por padrão.

## Rotas Disponíveis

### **Encurtar uma URL**

**POST** `/api/shorten`

#### Request Body:

```json
{
  "url": "https://example.com"
}
```

#### Resposta:

```json
{
  "short_url": "http://localhost:8080/abcd1234"
}
```

### **Acessar a URL encurtada**

**GET** `/{code}`

Exemplo:

```sh
curl -L http://localhost:8080/abcd1234
```

## Estrutura do Projeto

```
/go-url-shortener
├── main.go
├── go.mod
├── go.sum
├── api/
│   ├── api.go
├── README.md
```
