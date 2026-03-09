# ♟️ Chess Game

Jogo de xadrez para dois jogadores executado no terminal, desenvolvido em Java com Maven. O projeto aplica conceitos de Programação Orientada a Objetos como herança, polimorfismo, encapsulamento e tratamento de exceções.

---

## Tecnologias

- **Java 21**
- **Maven** (gerenciamento de dependências e build)

---

## Estrutura do Projeto

```
src/main/java/
├── application/
│   ├── Program.java       # Ponto de entrada da aplicação
│   └── UI.java            # Interface do usuário (terminal com cores ANSI)
├── boardgame/
│   ├── Board.java         # Lógica do tabuleiro genérico
│   ├── Piece.java         # Classe abstrata de peça
│   ├── Position.java      # Posição no tabuleiro (linha/coluna)
│   └── BoardException.java
├── chess/
│   ├── ChessMatch.java    # Controlador da partida
│   ├── ChessPiece.java    # Peça de xadrez (estende Piece)
│   ├── ChessPosition.java # Posição no formato xadrez (ex: a1, h8)
│   ├── Color.java         # Enum WHITE / BLACK
│   ├── ChessException.java
│   └── pieces/
│       ├── King.java
│       ├── Queen.java
│       ├── Rook.java
│       ├── Bishop.java
│       ├── Knight.java
│       └── Pawn.java
```

---

## Funcionalidades

- Partida completa de xadrez para dois jogadores no terminal
- Exibição do tabuleiro com cores ANSI (peças brancas e pretas)
- Destaque visual dos movimentos possíveis para a peça selecionada
- Controle de turno e alternância entre jogadores
- Rastreamento de peças capturadas
- Detecção de **Check** e **Checkmate**
- Movimentos especiais:
    - **En passant**
    - **Promoção de peão** (promovido automaticamente para Rainha)
    - **Roque** (kingside e queenside)

---

## Como Executar

### Pré-requisitos

- Java 21+
- Maven 3.x

### Compilar e rodar

```bash
# Clonar o repositório
git clone <url-do-repositorio>
cd chess

# Compilar
mvn compile

# Executar
mvn exec:java -Dexec.mainClass="application.Program"
```

Ou, alternativamente, gere o JAR e execute:

```bash
mvn package
java -cp target/chess-1.0-SNAPSHOT.jar application.Program
```

> **Dica:** Execute em um terminal que suporte cores ANSI para melhor visualização (Linux, macOS ou Windows Terminal).

---

## Como Jogar

1. Ao iniciar, o tabuleiro é exibido com as peças na posição inicial.
2. Digite a posição de **origem** da peça que deseja mover (ex: `e2`).
3. Os movimentos possíveis serão destacados no tabuleiro.
4. Digite a posição de **destino** (ex: `e4`).
5. O jogo alterna automaticamente entre as cores Branca e Preta.
6. O jogo termina quando um jogador entra em **Checkmate**.

**Formato de posição:** letra (coluna `a`–`h`) + número (linha `1`–`8`). Exemplo: `d1`, `h8`.

---

## Design do Projeto

O projeto é dividido em duas camadas:

- **`boardgame`** — camada genérica e reutilizável para qualquer jogo de tabuleiro.
- **`chess`** — camada específica com as regras do xadrez, estendendo a camada `boardgame`.

Essa separação garante baixo acoplamento e alta coesão, facilitando manutenção e extensão futura.

---

## Licença

Este projeto foi desenvolvido para fins educacionais.