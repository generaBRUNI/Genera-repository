let campoIdade;
let campoFantasia;
let campoAventura;
let campoRomance;

function setup() {
  createCanvas(800, 400);
  createElement("h2", "Recomendador de filmes");
  createSpan("Sua idade:");
  campoIdade = createInput("5");
  campoFantasia = createCheckbox("Fantasia");
  campoAventura = createCheckbox("Aventura");
campoRomance = createCheckbox("Romance")

}

function draw() {
  background("black");
  let idade = campoIdade.value();
  let gostaDeFantasia = campoFantasia.checked();
  let gostaDeAventura = campoAventura.checked();
  let gostaDeRomance = campoRomance.checked();
  let recomendacao = geraRecomendacao(idade, gostaDeFantasia, gostaDeAventura, gostaDeRomance, );

  fill(color(100, 0, 100));
  textAlign(CENTER, CENTER);
  textSize(38);
  text(recomendacao, width / 2, height / 2);
}

function geraRecomendacao(idade, gostaDeFantasia, gostaDeAventura, gostadeRomance) {
  if (idade >= 10) {
    if (idade >= 14) {
      if (gostaDeAventura)
      return "Tomb Raider: A Origem";
    } else {
      if (idade >= 12) {
        if(gostaDeFantasia) {
          return "Homem aranha: no aranhaverso";          
        } else {
          return "Uncharted: Fora do mapa"
        }
      } else {
        if (gostaDeFantasia) {
          return "As aventuras de pi";
        } else {
          return "Depois da chuva";
        }
      }
    }
  } else {
    if (gostaDeFantasia) {
      return "A viagem de chihiro";
    } else {
      return "O feitiço do tempo";
    }
  }
}
