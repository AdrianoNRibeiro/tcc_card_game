<template>
  <div class="hello">
    <main class="main">
      <div class="container">
        <div class="card-player">
          <div class="title"><h2>CARTAS DE LINGUAGENS</h2></div>
          <div class="grid" id="language-cards"></div>
        </div>
        <div class="card-player2">
          <div class="title2"><h2>CARTAS DE PROJETOS(FUSÕES)</h2></div>
          <div class="grid2" id="project-cards"></div>
        </div>
        <div class="card-player3">
          <div class="title2"><h2>CARTAS DE AMBIENTE</h2></div>
          <div class="grid3"></div>
        </div>
        <div class="card-player4">
          <div class="title2 dev"><h2>CARTAS DE DEV</h2></div>
          <div class="grid4"></div>
        </div>
        <div class="card-player5">
          <div class="title2 frame"><h2>CARTAS DE FRAMEWORKS</h2></div>
          <div class="grid5"></div>
        </div>
        <div class="card-player6">
          <div class="title2 bug"><h2>CARTAS DE BUGS</h2></div>
          <div class="grid6"></div>
        </div>
      </div>
    </main>
    <aside>
      <div class="card-information" id="information">
        <div class="card-amp">
          <img src="" alt="" class="img-card-amp" id="card-show" />
        </div>
        <div class="card-description">
          <div class="field f-name">
            <div style="display: flex; justify-content: space-between">
              <label style="text-decoration: underline">Nome:</label>
              <img src="" alt="Fechar" id="close-info" class="close-info" />
            </div>
            <p id="card-name">ASSEMBELES</p>
          </div>
          <div class="field f-desc">
            <label style="text-decoration: underline">Descrição:</label>
            <p id="description">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam
              voluptatibus, quod, voluptates, voluptas voluptatibus quos
              voluptatum voluptatibus quos voluptatum voluptatibus quos
              voluptatum voluptatibus quos voluptatum voluptatibus quos
              voluptatum voluptatibus quos voluptatum voluptatibus quos
            </p>
          </div>
          <div class="field f-frame">
            <label style="text-decoration: underline">Frameworks:</label>
            <div class="small-cards">
              <img src="" alt="" class="img-frameworks" id="card-framework" />
            </div>
          </div>
          <div class="field">
            <label style="text-decoration: underline">Fusões:</label>
            <div class="small-cards">
              <img src="#" alt="" class="img-frameworks" />
            </div>
          </div>
        </div>
      </div>
    </aside>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      characters: [
        "ASSEMBELE",
        "C.MAISMAIS",
        "CEH",
        "CESHARP",
        "CESSESSE",
        "DARTY",
        "ESKELLE",
        "F.ORTRAM",
        "GOH",
        "HAGATEMELER",
        "JAVAH",
        "JAVASCRIPTO",
        "KOTLEEN",
        "PAITON",
        "PEAGAPE",
        "PERULU",
        "RIUBI",
        "RUUSSTY",
        "SWIIFT",
        "TAI PIS CRIP",
        "VISUBAZICK",
      ],
      projects: [
        "TIPS CRYPTO",
        "WEBSPAGER",
        "FRONTENDOR",
        "FRONTENDORZ",
        "BACKNET",
        "APPINET",
        "APPINETZ",
      ],
      environment: [
        "VESSE-ESTUDIO",
        "VESSE-CORDE",
        "NONTEPEDEMAIS",
        "PAICHARMO",
        "EKLIPSER",
        "UNRIUENGINOR",
        "JEITOBREINS",
        "ANDROIDS-TUDOR",
        "MARSS",
        "DARTYPEDE",
        "PADRE",
        "SIMPLAI-FORT",
      ],
      dev: ["TRAINEE", "JUNIOR", "PLENO", "SENIOR"],
      frameworks: ["FreeRTOS", "CMSIS", "ULTIMATE++", "QT", "NANA++"],
      bugs: [],
      selectedcard: null,
      showPopup: false,
    };
  },
  methods: {
    renderCards(listCards, campGrids) {
      const grids = document.querySelector(campGrids);

      if (!grids) {
        console.error(`Elemento ${campGrids} não encontrado`);
        return;
      }
      grids.innerHTML = "";

      listCards.forEach((tag) => {
        const tagElement = document.createElement("div");
        const tagImage = document.createElement("img");

        tagElement.className = "img-card";

        tagImage.src = `../img/${tag}.png`;
        tagImage.className = "img-cardTeste";

        grids.appendChild(tagElement);
        tagElement.appendChild(tagImage);

        tagElement.style.marginTop = "8%";
        tagElement.style.marginBottom = "5%";

        tagImage.style.width = "100%";
        tagImage.style.height = "100%";
        tagImage.style.borderRadius = "5%";
        tagImage.style.boxShadow = "rgba(238, 236, 236, 0.35) 0px 5px 15px";
        tagImage.style.cursor = "pointer";
        tagImage.style.marginBottom = "1%";
        tagImage.addEventListener("mouseover", () => {
          tagImage.style.transform = "scale(1.1)";
          tagImage.style.transition = "all 0.8s ease";
        });
        tagImage.addEventListener("mouseout", () => {
          tagImage.style.transform = "";
          tagImage.style.transition = "";
        });
      });
    },
  },
  mounted() {
    this.renderCards(this.characters, ".grid");
    this.renderCards(this.projects, ".grid2");
    this.renderCards(this.environment, ".grid3");
    this.renderCards(this.dev, ".grid4");
    this.renderCards(this.frameworks, ".grid5");
    this.renderCards(this.bugs, ".grid6");
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.main {
  background-color: #361cca;
}

.grid,
.grid2,
.grid3,
.grid4,
.grid5,
.grid6 {
  display: grid;
  grid-template-columns: repeat(8, 1fr);
  gap: 1.1%;
  width: 100%;
  height: 80%;
  max-width: 80%;
  margin-left: auto;
  margin-right: auto;
  margin: 15px auto 0 auto;
}

.title,
.title2 {
  width: 100%;
  max-width: 80%;
  margin-left: auto;
  margin-right: auto;
  border-bottom: 1px solid #fcf812;
  border-top: 1px solid #fcf812;
  padding: 8px;
}

.title2 {
  margin-top: 25px;
}

h2 {
  text-align: center;
  font-family: "Passero One", sans-serif;
  font-size: 2.5em;
  color: #fcf812;
  text-shadow: 1px 1px 2px rgb(218, 211, 211);
}

.close-info {
  width: 40px;
  cursor: pointer;
}

.img-card {
  display: flex;
  flex-direction: column;
  width: 160px;
  height: 260px;
  cursor: pointer;
  border-radius: 2px;
}

.img-cardTeste {
  width: 100%;
  height: 230px;
  cursor: pointer;
  border-radius: 2px;
  margin-bottom: 1%;
  border-radius: 5%;
  box-shadow: rgba(238, 236, 236, 0.35) 0px 5px 15px;
}

.img-cardTeste:hover {
  transform: scale(1.1);
  transition: all 400ms ease;
}

.nameCharacter {
  text-align: center;
  font-family: "Passero One", sans-serif;
  font-size: 1.4em;
  font-weight: bold;
  color: #ccd82b;
}

.nameCharacter {
  text-align: center;
  font-family: "Passero One", sans-serif;
  font-size: 1.4em;
  font-weight: bold;
  color: #ccd82b;
}

.card-information {
  width: 90%;
  height: 80%;
  margin-left: auto;
  margin-right: auto;
  display: flex;
  position: fixed;
  top: 12%;
  left: 5%;
}

.hidden {
  visibility: hidden;
}

.backgroundDark {
  opacity: 0.5;
}

.card-description {
  width: 70%;
  height: 86%;
  background-color: rgba(240, 248, 255, 0.918);
  display: flex;
  flex-direction: column;
  padding: 15px;
  border-radius: 5px;
  transition: all 200ms ease-in-out;
}

.card-description label {
  text-align: justify;
  font-family: "Space Grotesk", sans-serif;
  font-size: 2em;
  color: #361cca;
  text-shadow: 1px 1px 2px rgb(218, 211, 211);
}

.card-amp {
  width: 30%;
  margin-right: 1%;
  text-align: center;
}

.img-card-amp {
  width: 100%;
  height: 90%;
  border-radius: 5px;
}

.field {
  padding: 5px;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.f-name {
  height: 11%;
}

.f-desc {
  height: 24%;
  border-bottom: 2px solid green;
  width: 95%;
}

.field p {
  font-family: "Space Grotesk", sans-serif;
  color: rgb(4, 12, 34);
  font-size: 1.5em;
  margin-top: -5px;
}

.img-frameworks {
  width: 9%;
  cursor: pointer;
  border-radius: 5px;
  box-shadow: rgba(37, 36, 36, 0.35) 0px 5px 15px;
}

.img-frameworks:hover {
  transform: scale(1.1);
}

.f-frame {
  width: 95%;
  border-bottom: 2px solid green;
}

.card-player,
.card-player2,
.card-player3,
.card-player4,
.card-player5,
.card-player6 {
  border-radius: 5px;
}
</style>
