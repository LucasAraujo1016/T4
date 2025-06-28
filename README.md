# Sistema WB - Interface Gráfica (Frontend)

Bem-vindo à documentação oficial do projeto de interface gráfica do **Sistema WB**. Este projeto foi desenvolvido para o Grupo World Beauty (WB) com o objetivo de modernizar e facilitar o uso do sistema por meio de uma interface web responsiva, intuitiva e acessível em qualquer dispositivo.

---

## 📋 Sumário

- [Visão Geral](#visão-geral)
- [O que foi desenvolvido](#o-que-foi-desenvolvido)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Como Executar o Projeto](#como-executar-o-projeto)
- [Integração com o Backend](#integração-com-o-backend)
- [Funcionalidades Disponíveis](#funcionalidades-disponíveis)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Padrões de Desenvolvimento](#padrões-de-desenvolvimento)
- [Customização e Temas](#customização-e-temas)
- [Contribuição](#contribuição)
- [Contato](#contato)

---

## Visão Geral

O **Sistema WB** foi projetado para atender todas as franquias do Grupo World Beauty, proporcionando uma experiência moderna e eficiente para os usuários. A interface gráfica (GUI) foi construída com foco em usabilidade, responsividade e facilidade de navegação, garantindo que qualquer colaborador, independente do dispositivo, consiga operar o sistema sem dificuldades.

O sistema segue o padrão RESTful, separando as responsabilidades do frontend e backend, permitindo evolução independente de cada camada.

---

## O que foi desenvolvido

Este sistema foi desenvolvido com foco em robustez, escalabilidade e facilidade de manutenção, visando atender demandas reais do Grupo World Beauty.  
As principais entregas e diferenciais deste projeto são:

- **Integração completa com micro-serviço RESTful em Java**, utilizando comunicação via JSON para garantir flexibilidade e independência entre frontend e backend.
- **Operações essenciais de gestão de clientes**:
  - **Cadastro de clientes**: Formulário completo, validando e enviando todos os dados necessários para o backend.
  - **Listagem de clientes**: Visualização de todos os clientes cadastrados, com filtro por nome para facilitar buscas rápidas.
  - **Atualização de clientes**: Permite selecionar o cliente, escolher exatamente qual campo atualizar (incluindo campos individuais do endereço e manipulação de telefones), garantindo precisão e controle.
  - **Exclusão de clientes**: Busca por nome e exclusão segura, com feedback ao usuário.
- **Interface gráfica moderna e responsiva**, desenvolvida com React, TypeScript e Tailwind CSS, garantindo usabilidade em qualquer dispositivo.
- **Feedback visual ao usuário** em todas as operações, promovendo transparência e confiança no uso do sistema.
- **Documentação clara e detalhada**, facilitando o treinamento de colaboradores e a manutenção futura do sistema.
- **Estrutura preparada para expansão**, permitindo fácil inclusão de novos módulos como produtos, serviços e relatórios.

Este projeto foi desenvolvido seguindo as melhores práticas de engenharia de software, com foco em qualidade, segurança e experiência do usuário, alinhado às necessidades do Grupo WB.

---

## Tecnologias Utilizadas

- **React 18+** (componentes de função e hooks)
- **TypeScript**
- **Tailwind CSS** (responsividade e design moderno)
- **Heroicons** (ícones SVG)
- **Jest + Testing Library** (testes unitários)
- **Java 17+** (backend, microserviço REST)
- **Spring Boot** (backend)

---

## Como Executar o Projeto

### 1. Pré-requisitos

- Node.js (versão 14 ou superior)
- npm ou yarn
- Java 17 ou superior (para o backend)

### 2. Instalação do Frontend

```bash
cd frontend
npm install
# ou
yarn install
```

### 3. Execução do Frontend

```bash
cd frontend
npm start
# ou
yarn start
```

Acesse [http://localhost:3000](http://localhost:3000) no navegador.

### 4. Execução do Backend

O backend já está pronto e disponível no repositório. Para executar:

```bash
cd backend/executavel
java -jar wbbackend.jar
```

O backend ficará disponível em [http://localhost:32832](http://localhost:32832).

---

## Integração com o Backend

A comunicação entre frontend e backend é feita via requisições REST (JSON).  
Principais endpoints utilizados:

- `GET /clientes` — Listar todos os clientes
- `POST /cliente/cadastrar` — Cadastrar novo cliente
- `PUT /cliente/atualizar` — Atualizar dados de um cliente
- `DELETE /cliente/excluir` — Excluir cliente

O frontend consome esses endpoints para todas as operações de cadastro, listagem, atualização e exclusão.

---

## Funcionalidades Disponíveis

### Clientes

- **Cadastro de Cliente:**  
  Formulário completo, com campos para nome, sobrenome, email, telefones (DDD e número) e endereço (estado, cidade, bairro, rua, número, CEP, informações adicionais).

- **Listagem de Clientes:**  
  Visualização de todos os clientes cadastrados, com filtros por nome.

- **Atualização de Cliente:**  
  Busca por nome, seleção do cliente, escolha do campo a ser atualizado (incluindo campos individuais do endereço e manipulação de telefones).

- **Exclusão de Cliente:**  
  Busca por nome, seleção e exclusão do cliente.

- **Feedback ao Usuário:**  
  Mensagens de sucesso e erro em todas as operações.

### Outras Telas

- **Produtos e Serviços:**  
  Estrutura pronta para cadastro, atualização, exclusão e listagem (pode ser expandida conforme necessidade futura).

- **Listagens Especiais:**  
  Exemplos de listagens por gênero, maiores/menores consumidores, etc.

---

## Estrutura do Projeto

```
frontend/
  src/
    componentes/
      barraNavegacao.tsx
      clientes.tsx
      formularioCadastro.tsx
      home.tsx
      listagensEspeciais.tsx
      Modal.tsx
      produtos.tsx
      roteador.tsx
      servicos.tsx
    api/
      clientes.ts
    index.tsx
    index.css
  public/
    index.html
    manifest.json
    robots.txt

backend/
  executavel/
    wbbackend.jar
  wbbackend/
    src/
      main/
        java/
          com/
            wb/
              wbbackend/
                entidades/
                controles/
                repositorios/
                atualizadores/
                verificadores/
                hateoas/
        resources/
          application.properties
```

---

## Padrões de Desenvolvimento

- **Componentes de Função e Hooks:**  
  Todos os componentes React são implementados como funções utilizando hooks (`useState`, `useEffect`, etc.), seguindo as práticas modernas do React.

- **Responsividade:**  
  Layout adaptável para desktop, tablets e celulares.

- **Design Moderno:**  
  Uso de cores, gradientes e ícones para uma experiência agradável.

- **Integração RESTful:**  
  Comunicação entre frontend e backend via JSON, seguindo o padrão REST.

---

## Customização e Temas

- O tema principal utiliza tons de roxo e rosa, seguindo a identidade visual do Grupo WB.
- Para alterar cores ou estilos, edite o arquivo `index.css` e os utilitários Tailwind nos componentes.

---

## Contribuição

1. Faça um fork do projeto
2. Crie uma branch para sua feature (`git checkout -b feature/nome`)
3. Commit suas alterações (`git commit -am 'Adiciona nova feature'`)
4. Push para o branch (`git push origin feature/nome`)
5. Abra um Pull Request

---

**Desenvolvido para o Grupo World Beauty (WB) - 2025**  
Documentação criada para uso interno e treinamento de colaboradores.
