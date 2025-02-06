# Valorr TCG - Plataforma de Cartas Colecionáveis
![banner](https://mycollectify.s3.us-west-2.amazonaws.com/genesis/0-genesis-collection-carousel.jpeg?w=1920&h=600&fit=crop)

## 🎮 Demonstração

Acesse a demonstração ao vivo: [Valorr TCG](https://valorr-tcg.netlify.app)

## 📖 Sobre o Projeto

Valorr TCG é uma plataforma web moderna de cartas colecionáveis digitais que oferece uma experiência única de coleção, troca e gerenciamento de cartas virtuais. Desenvolvida com tecnologias modernas e focada em uma experiência de usuário envolvente, com animações suaves, feedback visual intuitivo e design responsivo.

## 🚀 Funcionalidades Principais

### Modo História
- Sistema de Progressão
  - Capítulos com 30 batalhas cada
  - 3 chefes por capítulo (batalhas 10, 20 e 30)
  - Dificuldade progressiva por seção (+30% por seção)
  - Aumento gradual por batalha (+3% por batalha)
  - Recompensas de 5000 moedas por capítulo completo
  - Sistema de desbloqueio baseado em capítulos
  - Cartas especiais por conquistas
  - Salvamento automático de progresso
  - Visualização do caminho de batalha
  - Indicadores de progresso visual
  - Recompensas especiais de chefe

### Sistema de Batalha
- Mecânicas Principais
  - Batalhas em turnos baseadas em velocidade
  - Campo com 1 posição ativa e 2 de banco
  - Sistema de dimensões com efeitos únicos
  - Promoção automática de cartas do banco
  - Log de batalha detalhado e interativo
  - Cemitério de cartas acessível
  - Animações de ataque, dano e esquiva
  - Sistema de esquiva baseado em velocidade
  - Confirmação ao tentar sair

### Efeitos de Dimensão
- Origem: +50% ataque e velocidade
- Sombria: Dobra velocidade e esquiva
- Luminosa: Cura 50% e +30% ataque
- Tecnológica: Dobra ataque, -25% velocidade
- Natural: Cura total e +30% velocidade

### Vitrine de Cartas
- Sistema de Compra Direta
  - Cartas raras por 3000 moedas
  - Cartas lendárias por 15000 moedas
  - Atualização mensal automática
  - 4 cartas raras e 1 lendária por mês
  - Histórico de compras
  - Indicador de próxima atualização
  - Sistema anti-fraude com validação no servidor

### Sistema de Minigames
- Caça Moedas (10 jogadas/dia)
  - Prêmio máximo: 1000 moedas
  - Sistema de símbolos progressivos
  - Animações de vitória

- Pedra, Papel e Tesoura (5 jogadas/dia)
  - Prêmio máximo: 500 moedas
  - Bônus por sequência de vitórias
  - Animações de batalha

- Campo Minado (3 jogadas/dia)
  - Prêmio máximo: 750 moedas
  - Grade 5x5 com 8 bombas
  - Recompensa por célula segura

- Encontre os Pares (1 jogada/dia)
  - Prêmio máximo: 300 moedas
  - Combine 3 símbolos iguais
  - Animações de combinação

### Sistema de Dados em Tempo Real
- Sincronização em tempo real com Firebase Firestore
- Cache local para melhor performance
- Sistema de logs para debugging
- Tratamento de erros robusto
- Backup automático de dados
- Sistema de atividades recentes
- Centro de mensagens e notificações
- Recompensas por eventos do jogo

### Gestão de Coleções
- Múltiplas coleções temáticas
- 5 Dimensões Únicas:
  - Origem: Poder ancestral e força bruta
  - Sombria: Velocidade e esquiva elevadas
  - Luminosa: Cura e fortalecimento
  - Tecnológica: Alto dano com custo de velocidade
  - Natural: Regeneração e agilidade

### Interface do Usuário
- Tema claro/escuro com persistência
- Design responsivo e adaptativo
- Layout otimizado para mobile
- Fonte épica Cinzel para títulos
- Efeitos de brilho e animações nos títulos
- Sidebar retrátil para melhor aproveitamento do espaço
- Carrossel de destaques na home
- Notificações e indicadores visuais
- Footer informativo com links úteis
- Sistema de pré-carregamento de imagens
- Indicadores de progresso de carregamento
- Centro de mensagens com recompensas
- Histórico de atividades recentes
- Configurações personalizáveis
- Página de ajuda e suporte
- Termos de uso e privacidade

### Sistema de Recompensas
- Recompensas diárias progressivas
- Bônus por sequência de login
- Minigames com prêmios
- Histórico de recompensas
- Estatísticas detalhadas
- Sistema de mensagens com recompensas
- Notificações de conquistas
- Recompensas por eventos especiais

## 🔄 Sistema de Dados

### Coleções do Firestore

#### users
- id: string
- email: string
- username: string
- coins: number
- createdAt: timestamp
- lastLogin: timestamp

#### collections
- cards: array
  - id: string
  - name: string
  - image: string
  - rarity: string
  - collection: string
  - quantity: number
- coins: number

#### showcase
- cards: array
  - id: string
  - name: string
  - image: string
  - rarity: string
  - collection: string
  - purchased: boolean
- lastRefresh: string
- lastRefreshTimestamp: timestamp
- nextRefreshDate: string
- purchasedCards: array
  - cardId: string
  - purchaseTime: string
  - price: number

#### story
- currentChapter: number
- completedChapters: array
- battleProgress: object
  - [chapterId-battleId]: object
    - completed: boolean
    - timestamp: string
- chapterRewards: array
  - chapterId: number
  - claimed: boolean
  - claimedAt: string
- level: number

#### stats
- totalPacksOpened: number
- totalCardsOwned: number
- totalCardsSold: number
- packsSinceLastLegendary: number
- cardStats: object
  - [cardKey]: object
    - id: string
    - name: string
    - collection: string
    - rarity: string
    - acquired: number
    - lastAcquired: string
- avatarId: string

#### activities
- activities: array
  - id: string
  - type: string
  - message: string
  - timestamp: number
  - details: object

#### minigames
- lastPlayDate: string
- plays: object
  - slots: number
  - rps: number
  - minesweeper: number
  - cardMatch: number

## 🛠️ Tecnologias Utilizadas

- React 18.3
- TypeScript 5.5
- Vite 5.4
- TailwindCSS 3.4
- Firebase 10.8
- Zustand 4.5
- React Router 6.22
- Lucide React Icons

## 📦 Instalação e Uso

1. Clone o repositório
2. Instale as dependências: `npm install`
3. Configure as variáveis de ambiente no `.env`
4. Execute o projeto: `npm run dev`

## 🤝 Contribuição

Contribuições são bem-vindas! Por favor, leia as diretrizes de contribuição antes de enviar um pull request.

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo LICENSE para mais detalhes.
