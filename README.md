# TranspoGraph

**TranspoGraph** é um sistema de gestão e otimização de rotas de transporte entre cidades. Ele utiliza grafos para representar a rede de transporte e permite a otimização das rotas com base em critérios como custo, tempo de viagem ou capacidade de transporte.

## Funcionalidades Principais
- **Cadastro de cidades e rotas**: Adicione e edite cidades e as rotas entre elas, especificando dados como distância, tempo de viagem e custo.
- **API de gerenciamento**: Interaja com o sistema por meio de uma API REST, permitindo a criação, edição, consulta e exclusão de rotas e cidades.
- **Otimização de rotas**: Utilize algoritmos avançados para encontrar as melhores rotas entre cidades com base em diferentes critérios (custo mínimo, tempo mínimo, fluxo máximo).
- **Visualização e ordenação**: Visualize todas as rotas cadastradas e ordene-as de acordo com o critério desejado, como distância, custo ou tempo de viagem.

## Estrutura de Dados
O sistema utiliza grafos para modelar a rede de transporte:
- **Nós (vértices)**: Cada cidade é representada por um nó.
- **Arestas**: Cada rota entre duas cidades é representada por uma aresta ponderada com o custo, distância e tempo de viagem.

### Possíveis Algoritmos
- **Dijkstra**: Para encontrar o caminho mais curto entre duas cidades, levando em consideração o tempo ou a distância.
- **Ford-Fulkerson**: Para otimizar o fluxo máximo entre dois pontos, maximizando o transporte de passageiros ou cargas.
- **Árvore Geradora Mínima (Kruskal ou Prim)**: Para construir a rede de transporte com o menor custo total, conectando todas as cidades com o menor número de rotas.

## Endpoints da API
A API foi desenvolvida para facilitar a interação com o sistema de transporte. Abaixo estão os principais endpoints:

### **Cidades**
- `GET /cidades`: Retorna a lista de todas as cidades cadastradas.
- `POST /cidades`: Adiciona uma nova cidade (exige nome e coordenadas).
- `PUT /cidades/:id`: Atualiza as informações de uma cidade.
- `DELETE /cidades/:id`: Remove uma cidade específica.

### **Rotas**
- `GET /rotas`: Retorna a lista de todas as rotas cadastradas.
- `POST /rotas`: Adiciona uma nova rota entre duas cidades (exige cidade de origem, destino, distância, custo e tempo).
- `PUT /rotas/:id`: Atualiza as informações de uma rota existente.
- `DELETE /rotas/:id`: Remove uma rota específica.

### **Otimização de Rotas**
- `GET /rotas/otimizadas`: Retorna a rota otimizada com base em um critério (tempo, custo, fluxo).
- `POST /rotas/fluxo-maximo`: Calcula o fluxo máximo de passageiros ou cargas entre dois pontos.

## Tecnologias Utilizadas
- **Backend**: Node.js com Express 
- **Banco de Dados**: PostgreSQL 
- **Front-End (Opcional)**: Next.js para visualização de mapas e rotas
- **Algoritmos de Otimização**: Dijkstra, Ford-Fulkerson, Kruskal/Prim    
