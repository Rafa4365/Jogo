function setup() {
  createCanvas(400, 400);
}

let Jogador = [0, 0, 0]; // Array para armazenar as posições X dos jogadores
let yJogador = [100, 200, 300]; // Posições Y dos jogadores
let velocidade = 1; // Velocidade de movimento dos jogadores
let vencedor = false; // Variável para controlar se um jogador já venceu

function draw() {
  background("#D2EBB5"); // Fundo verde quando o jogo está ativo
  ativaJogo();
  desenhaJogadores();
  desenhaLinhaDeChegada();
  verificaVencedor();
  moveJogadores();
}

function ativaJogo() {
  // A lógica de ativação do jogo não é mais necessária, pois o fundo está sempre setado
  // background("#D2EBB5"); // Fundo verde quando o jogo está ativo
}

function desenhaJogadores() {
  textSize(40);
  text("😎", Jogador[0], yJogador[0]);
  text("❤️", Jogador[1], yJogador[1]);
  text("👽", Jogador[2], yJogador[2]);
}

function desenhaLinhaDeChegada() {
  fill("white");
  rect(350, 0, 10, 400);
  fill("black");
  for (let yAtual = 0; yAtual < 400; yAtual += 20) {
    rect(350, yAtual, 10, 10);
  }
}

function moveJogadores() {
  // Movimenta os jogadores para a direita
  Jogador[0] = Jogador[0] + velocidade;
  Jogador[1] = Jogador[1] + velocidade;
  Jogador[2] = Jogador[2] + velocidade;
}

function verificaVencedor() {
  if (Jogador[0] > 350 && !vencedor) {
    text("Jogador 1 venceu!", 50, 200);
    vencedor = true;
    noLoop();
  }
  if (Jogador[1] > 350 && !vencedor) {
    text("Jogador 2 venceu!", 50, 200);
    vencedor = true;
    noLoop();
  }
  if (Jogador[2] > 350 && !vencedor) {
    text("Jogador 3 venceu!", 50, 200);
    vencedor = true;
    noLoop();
  }
}
