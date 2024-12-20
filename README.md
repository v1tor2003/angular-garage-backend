# AngularGarage API

Bem-vindo à API de backend do Sistema de Gestão AngularGarage! Este projeto foi desenvolvido para fornecer a camada de backend que suporta as funcionalidades do aplicativo frontend Angular Garage, permitindo operações CRUD nos recursos de carros.

## Índice

- [Recursos](#recursos)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Instalação](#instalação)
- [Uso](#uso)
- [Rotas da API](#rotas-da-api)
- [Possíveis Melhorias](#possíveis-melhorias)
- [Licença](#licença)

## Recursos

- API RESTful para operações CRUD de carros
- Validações de dados para manter a integridade
- Suporte para paginar, buscar e filtrar carros

## Tecnologias Utilizadas

- [Ruby on Rails](https://rubyonrails.org/)
- [PostgreSQL](https://www.postgresql.org/) (ou SQLite para desenvolvimento local)
- [RSpec](https://rspec.info/) (para testes)

## Instalação

1. Clone o repositório:
   ```bash
   git clone https://github.com/seuusuario/RailsGarageAPI.git
   ```

2. Navegue até o diretório do projeto:
   ```bash
   cd RailsGarageAPI
   ```

3. Instale as dependências:
   ```bash
   bundle install
   ```

4. Configure o banco de dados:
   ```bash
   rails db:setup
   ```

5. Inicie o servidor de desenvolvimento:
   ```bash
   rails server
   ```

6. Acesse a API em `http://localhost:3000/`.

## Uso

Esta API foi projetada para ser consumida por um cliente frontend, como o Angular Garage. Utilize ferramentas como Postman ou cURL para testar endpoints diretamente.

## Rotas da API

### Car Resource

| Método | Rota                  | Descrição                              |
|--------|-----------------------|----------------------------------------|
| GET    | `/cars`               | Retorna uma lista de todos os carros. |
| GET    | `/cars/:id`           | Retorna os detalhes de um carro específico. |
| POST   | `/cars`               | Cria um novo carro.                   |
| PATCH  | `/cars/:id`           | Atualiza os dados de um carro específico. |
| DELETE | `/cars/:id`           | Remove um carro específico.           |

#### Exemplos de Uso

1. **Listar todos os carros**
   - Endpoint: `GET /cars`
   - Exemplo de resposta:
     ```json
     [
       {
         "id": 1,
         "brand": "Toyota",
         "model": "Corolla",
         "year": 2020,
         "color": "White"
       },
       {
         "id": 2,
         "brand": "Ford",
         "model": "Fiesta",
         "year": 2018,
         "color": "Blue"
       }
     ]
     ```

2. **Criar um novo carro**
   - Endpoint: `POST /cars`
   - Body:
     ```json
     {
       "brand": "Honda",
       "model": "Civic",
       "year": 2022,
       "color": "Black"
     }
     ```
   - Exemplo de resposta:
     ```json
     {
       "id": 3,
       "brand": "Honda",
       "model": "Civic",
       "year": 2022,
       "color": "Black"
     }
     ```

3. **Atualizar um carro**
   - Endpoint: `PATCH /cars/:id`
   - Body:
     ```json
     {
       "color": "Red"
     }
     ```
   - Exemplo de resposta:
     ```json
     {
       "id": 3,
       "brand": "Honda",
       "model": "Civic",
       "year": 2022,
       "color": "Red"
     }
     ```

4. **Excluir um carro**
   - Endpoint: `DELETE /cars/:id`
   - Exemplo de resposta:
     ```json
     {
       "message": "Car deleted successfully."
     }
     ```

## Possíveis Melhorias

- Adicionar autenticação e autorização para gerenciamento seguro de carros.
- Implementar buscas e filtros avançados com parâmetros de query.
- Expandir o modelo de carro para incluir mais atributos (e.g., preço, estado do veículo).
- Adicionar suporte para upload de imagens do carro.
- Melhorar os testes automatizados para cobrir todos os casos de uso.

## Licença

Este projeto é licenciado sob a Licença MIT - consulte o arquivo [LICENSE](LICENSE) para mais detalhes.