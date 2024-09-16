## Integrantes 

- Ana Carolina Tavares - RM552283
- Gabriel Lopes Pereira - RM98023
- Giovanni Paschoalatto - rm98837
- Sofia Sprocatti - RM99208
- Vinicius Minei - RM98486

## Link do pitch
[Pitch](https://www.youtube.com/watch?v=Dftv_DrgO88)

## Link do github
[GitHub](https://github.com/anabrandt/sprint3-ia)

Para adaptar a estrutura do projeto Doracorde ao uso de React e integração com a API Assistive e vLibras, aqui está uma versão atualizada do README e estrutura de diretórios:


# Doracorde - Harmonia para Todos os Sentidos

## Sobre o Projeto
**Doracorde** é uma plataforma inovadora de ensino musical adaptada para pessoas com deficiência visual. Utilizamos React para o frontend e integramos APIs assistivas, como **vLibras**, para oferecer uma experiência de aprendizagem musical acessível e inclusiva.

## Tabela de Conteúdos
- [Sobre o Projeto](#sobre-o-projeto)
- [Requisitos do Projeto](#requisitos-do-projeto)
- [Instalação e Configuração](#instalação-e-configuração)
- [Arquitetura do Projeto](#arquitetura-do-projeto)
- [Integração com APIs](#integração-com-apis)
- [Testes](#testes)
- [Contribuindo](#contribuindo)
- [Licença](#licença)

## Requisitos do Projeto
- **Frontend**: React.js
- **APIs Assistivas**: Assistive, vLibras
- **Gerenciador de Pacotes**: npm ou yarn
- **Testes**: Jest, React Testing Library

## Instalação e Configuração
1. Clone o repositório:
   ```bash
   git clone https://github.com/seuusuario/doracorde.git
   ```
2. Navegue até o diretório do projeto:
   ```bash
   cd doracorde
   ```
3. Instale as dependências:
   ```bash
   npm install
   ```
4. Execute a aplicação em modo de desenvolvimento:
   ```bash
   npm start
   ```

## Arquitetura do Projeto
O projeto está estruturado da seguinte forma:

```
doracorde/
│
├── node_modules/
├── public/
│
├── src/
│   ├── assets/               # Arquivos de mídia e imagens
│   ├── components/           # Componentes reutilizáveis
│   ├── locales/              # Arquivos de tradução e i18n
│   ├── Pages/                # Páginas da aplicação
│   ├── utils/                # Funções utilitárias
│   ├── App.css               # Estilos globais
│   ├── App.js                # Componente principal da aplicação
│   ├── App.test.js           # Testes do componente App
│   ├── i18n.js               # Configuração de internacionalização
│   ├── index.css             # Estilos do index
│   ├── index.js              # Ponto de entrada da aplicação
│   ├── logo.svg              # Logo da aplicação
│   ├── main.jsx              # Arquivo JSX principal
│   ├── reportWebVitals.js    # Relatório de performance
│   └── setupTests.js         # Configuração de testes
│
├── .gitignore                # Arquivos ignorados pelo Git
├── doracorde-banner.png      # Banner do projeto
├── package-lock.json         # Lockfile do npm
├── package.json              # Dependências e scripts do projeto
└── README.md                 # Documentação do projeto
```

## Integração com APIs
O Doracorde integra as seguintes APIs assistivas:
- **Assistive**: Proporciona suporte para diversas tecnologias assistivas.
- **vLibras**: Implementa tradução automática de conteúdo para Libras (Língua Brasileira de Sinais).

### Configuração da API Assistive
Para configurar a integração com a API Assistive, siga as instruções fornecidas na documentação oficial.

### Configuração da API vLibras
A integração com a API vLibras requer a inclusão do widget em sua aplicação React. Exemplo:

```jsx
import React, { useEffect } from 'react';

function App() {
  useEffect(() => {
    const script = document.createElement('script');
    script.src = "https://vlibras.gov.br/app/vlibras-plugin.js";
    script.async = true;
    document.body.appendChild(script);
    script.onload = () => {
      new window.VLibras.Widget('https://vlibras.gov.br/app');
    };
  }, []);

  return (
    <div className="App">
      <h1>Bem-vindo ao Doracorde</h1>
      {/* Conteúdo da aplicação */}
    </div>
  );
}

export default App;
```

## Testes
Os testes foram implementados utilizando **Jest** e **React Testing Library**. Para executar os testes, use o seguinte comando:

```bash
npm test
```

## Contribuindo
Contribuições são bem-vindas! Se você deseja contribuir para o projeto Doracorde, siga estas etapas:

1. Fork este repositório.
2. Crie uma branch com sua feature (`git checkout -b feature/nome-da-feature`).
3. Commit suas alterações (`git commit -m 'Adiciona nova feature'`).
4. Envie para a branch (`git push origin feature/nome-da-feature`).
5. Abra um Pull Request.
