<template>
  <div class="container">
    <div class="info">
      <div class="card">
        <div class="data">
          <h3>{{ article[art].infoName }}</h3>
          <p>{{ article[art].infoDate }}</p>
        </div>
        <div class="picture"></div>
      </div>
    </div>
    <div class="content">
      <div class="head">
        <h1 class="title">{{ article[art].title }}</h1>
        <h2 class="date">{{ article[art].date }}</h2>
      </div>

      <div class="content-1">
        <p>{{  article[art].text1 }}</p>
      </div>

      <div class="illu-principal" v-if="article[art].illuPrincipal != ''">
        <img :src="article[art].illuPrincipal" alt="">
      </div>

      <div class="content-2">
        <p>{{ article[art].text2 }}</p>
      </div>

      <div class="illu-table" v-if="article[art].illu.length != 0">
        <div class="illu" v-for="illu in article[art].illu">
          <img :src="illu" alt="">
        </div>
      </div>
      <div class="content-3">
        <p>{{ article[art].text3 }}</p>
      </div>
      <div class="foot">
        <h2>Autres articles</h2>
        <div class="foot-content">
          <a :href="'/?art='+(art)" v-if="art != 0">
            <h3>Article précédent</h3>
            <h4>{{ article[art-1].title }}</h4>
            <p>{{ article[art-1].date }}</p>
          </a>
          <a :href="'/?art='+(art+2)" v-if="art+1 != article.length">
            <h3>Article suivant</h3>
            <h4>{{ article[art+1].title }}</h4>
            <p>{{ article[art+1].date }}</p>
          </a>
        </div>
      </div>
    </div>
  </div>
</template>
  
<script setup lang="ts">
import { ref } from 'vue';


let url = new URL(window.location.href);
const art = ref(Number(url.searchParams.get("art"))-1);


const article = [
  {
    infoName: "MACE Léo",
    infoDate: "18 Juin 2024",
    title: "Arrivé à la Cité du Vin",
    date: "17 Juin 2024",
    text1: "Aujourd'hui est mon premier jour à la Cité du Vin, marquant le début d'une toute nouvelle expérience et d'une précieuse opportunité d'apprentissage. À mon arrivée, j'ai rencontré mon maître de stage, qui m'a ensuite présenté aux différentes personnes travaillant à la Cité du Vin, en particulier celles avec qui je serai amené à collaborer au cours de mes missions. Je l'ai ensuite accompagné lors de l'allumage des différents modules d'exposition, ce qui m'a permis de découvrir le module sur lequel je vais travailler, « Le Jeu des Couleurs », ainsi que les installations techniques situées derrière les décors des expositions. Pour bien commencer mon stage et m'immerger dans le monde professionnel, j'ai rapidement eu l'occasion de suivre mon maître de stage lorsqu'il a dû intervenir sur un module qui ne s'était pas démarré correctement. J'ai ainsi pu l'observer et l'assister dans les différentes manipulations nécessaires à la remise en marche de l'installation. Une fois tous les modules correctement démarrés, j'ai découvert le sujet de mon stage : « Comprendre le fonctionnement du Jeu des Couleurs, qui ne possède aucune documentation, qu'elle soit logicielle ou matérielle, prototyper un système capable de remplacer l'actuel sans perdre de fonctionnalités, et rédiger une documentation complète. »",
    text2: "Qu’est-ce que le Jeu des Couleurs ? Le Jeu des Couleurs est un module interactif composé d'un plateau de jeu et d'une interface graphique. Les visiteurs y sélectionnent une couleur de vin qu'ils doivent ensuite essayer de retrouver sur le plateau, composé de 24 cônes lumineux, chacun éclairé par des LEDs. Pour valider leur choix, les visiteurs placent leur main sur l'un des 14 capteurs, chaque capteur représentant une zone de couleur spécifique.",
    text3:"Pour commencer cette tâche, j'avais besoin d'interagir avec le module en place afin de récupérer et analyser les communications entre la carte contrôlant les capteurs, les plots lumineux, et l'interface utilisateur avec laquelle les visiteurs interagissent. Un point crucial que je dois prendre en compte dans mon travail, et qui pourrait me ralentir si je ne m'adapte pas rapidement, est le suivant : la Cité du Vin étant un musée, le module sur lequel je travaille fait partie d'une exposition. Par conséquent, je ne peux pas intervenir dessus pendant les heures d'ouverture du musée, ce qui réduit considérablement les périodes durant lesquelles je peux effectuer mes tests et comprendre le fonctionnement du module. N'ayant pas pu commencer mon sujet ce jour-là, j'ai accompagné mon maître de stage lors de ses différentes interventions sur le matériel et lors de l'installation de plusieurs serveurs.",
    illuPrincipal:"/article/illustration/Video_6.gif",
    illu: ["/article/illustration/IMG_0367.jpg","/article/illustration/IMG_0369.jpg"]
  },
  {
    infoName: "MACE Léo",
    infoDate: "22 Juin 2024",
    title: "Analyse et prototypage du « Jeu des Couleurs »",
    date: "21 Juin 2024",
    text1: "Aujourd'hui marque la fin de ma première semaine à la Cité du Vin, où j'ai commencé à rédiger la documentation pour mon prototype du « Jeu des Couleurs ». Cette semaine a été très productive et m'a permis de faire d'importants progrès sur mon projet. Je me suis rapidement adapté au rythme de travail, qui ne me permettait pas de travailler sur le module pendant les heures d'ouverture. Dès le lendemain de mon arrivée, j'avais déjà effectué toutes les analyses des requêtes UART se produisant entre la carte et l'interface, ainsi que les observations sur les réactions des différentes LED et des capteurs impliqués dans les interactions.",
    text2: "Grâce à ces analyses, j'ai pu directement commencer à créer un prototype reproduisant les fonctionnalités de la carte, ainsi que les interactions et réactions des capteurs et des LED. Un problème majeur rencontré était le nombre insuffisant de broches disponibles sur la carte imposée : une esp32-s3. En effet, celle-ci ne disposait pas de suffisamment de connecteurs pour brancher les 14 capteurs et 24 LED. Après avoir envisagé plusieurs solutions, nous avons décidé d'utiliser le protocole I2C pour connecter toutes les LED à seulement deux connecteurs. Pour cela, j'ai dû rechercher des pilotes permettant de connecter des LED non compatibles avec le protocole I2C. C'est ainsi que j'ai découvert le driver PCA9685, capable de gérer jusqu'à 16 LED. Deux drivers ont donc suffi pour connecter l'ensemble de nos LED.",
    text3:"Une fois le premier prototype fonctionnel du « Jeu des Couleurs » réalisé, j'ai établi la liste des composants nécessaires pour créer une version « finale » du jeu, dépassant ainsi l'étape du simple prototype. J'ai également commencé à rédiger une première documentation et à concevoir le schéma électrique pour reproduire mon prototype, ainsi que lancé la commande de matériel. Cette première semaine m'a permis de développer mes compétences en programmation de microcontrôleurs, d'apprendre à utiliser les protocoles I2C et UART, et surtout d'acquérir une méthodologie de rétro-ingénierie précieuse pour la suite de mon parcours.",
    illuPrincipal:"",
    illu: ["/article/illustration/image5 (1).jpeg","/article/illustration/image17.jpeg","/article/illustration/image0 (1).jpeg"]
  },
  {
    infoName: "MACE Léo",
    infoDate: "30 Juin 2024",
    title: "Un nouveau sujet de stage",
    date: "28 Juin 2024",
    text1: "Aujourd'hui marque le dernier jour de ma deuxième semaine de stage à la Cité du Vin. Contrairement à la première semaine, celle-ci n'a pas été consacrée au « Jeu des Couleurs », mais à un tout autre sujet de stage. Ayant terminé la tâche principale de mon stage, qui consistait à « comprendre, prototyper et documenter le Jeu des Couleurs », mon maître de stage m'a redirigé vers le directeur de mon service pour qu'il m'assigne une nouvelle mission en parallèle. En effet, pour continuer à avancer sur le « Jeu des Couleurs », j'avais besoin de matériel encore en cours de livraison.",
    text2: "Ma nouvelle tâche consiste à « réaliser un outil d’inventaire comprenant une application mobile, un logiciel de bureau, une base de données et une API ». Pour bien appréhender cette mission, j'ai d'abord étudié le cahier des charges pour comprendre les différentes fonctionnalités nécessaires au développement du logiciel. Ensuite, j'ai participé à plusieurs réunions où j'ai pu présenter des maquettes, clarifier les besoins, et convenir des technologies à utiliser. Nous avons décidé d'utiliser Angular pour la partie bureau, React Native pour l'application mobile, ainsi que MySQL et Node.js pour la base de données et l'API.",
    text3:"À la fin de cette semaine, j'ai pu réaliser quelques pages du module bureau ainsi que les pages et fonctionnalités de l'application mobile. J'ai également commencé à concevoir la base de données et à développer une API minimale permettant la création, la suppression, et la récupération des données. Enfin, aujourd'hui, nous avons reçu la commande de matériel passée en fin de semaine dernière, ce qui me permettra de poursuivre et finaliser mon travail sur le « Jeu des Couleurs » dans les semaines à venir.",
    illuPrincipal:"/article/illustration/aze.png",
    illu: ["/article/illustration/aze.png","/article/illustration/qsd.png"]
  },
  {
    infoName: "MACE Léo",
    infoDate: "2 Aôut 2024",
    title: "« Jeu des Couleurs, du prototype au fonctionnel »",
    date: "2 Août 2024",
    text1: "Nous sommes à une semaine de la fin de mon stage, et j'ai enfin une nouvelle version fonctionnelle du « Jeu des Couleurs ». Ces dernières semaines ont été marquées par de multiples tests et ajustements du code, ainsi que par la réalisation des soudures des différents composants nécessaires à la mise en place du jeu.",
    text2: "Mon objectif principal durant cette période était de créer un module fonctionnel pouvant être intégré au modèle en production sans nécessiter de modifications des alimentations des LEDs et des capteurs. Je suis fier de dire que cet objectif est atteint ! En effet, j'ai réussi à souder deux versions du Jeu des Couleurs en plug-and-play, qui peuvent être directement implantées sur le module d'exposition. Cela permet de changer facilement de version en cas de panne matérielle.",
    text3:"J'ai énormément appris en électronique et en soudure au cours de ce projet. Je suis maintenant à l'étape de la rédaction d'une documentation complète, détaillant les différentes étapes pour reproduire mon travail, le comprendre, l'installer, et le transmettre efficacement à la Cité du Vin.",
    illuPrincipal:"/article/illustration/Video_6.gif",
    illu: ["/article/illustration/image11.jpeg","/article/illustration/image5.jpeg","/article/illustration/image2 (1).jpeg"]
  },
  {
    infoName: "MACE Léo",
    infoDate: "11 Août 2024",
    title: "Conclusion",
    date: "9 Août 2024",
    text1: "Aujourd'hui, en tant que dernier jour de mon stage à la Cité du Vin, je prends un moment pour réfléchir à l'ensemble de cette expérience enrichissante. Ce stage a été une occasion précieuse d'apprentissage et de développement professionnel, me permettant de faire des avancées significatives dans divers domaines techniques.",
    text2: "Au cours de ces semaines, j'ai acquis des compétences approfondies en programmation de microcontrôleurs, en particulier avec les protocoles UART et I2C. J'ai également développé une solide compréhension de l'électronique et des techniques de soudure, essentielles pour la création et le perfectionnement des prototypes. La gestion de la documentation technique et la mise en œuvre de la rétro-ingénierie ont été des aspects clés de mon apprentissage, me permettant de structurer et de transmettre efficacement les informations techniques. Les défis principaux ont été liés à la gestion du matériel limité et aux contraintes spécifiques de l'environnement muséal. L'insuffisance de broches sur la carte initiale a exigé l'adoption du protocole I2C pour connecter un grand nombre de LEDs. De plus, la nécessité de ne pas intervenir sur les modules pendant les heures d'ouverture du musée a restreint les périodes disponibles pour les tests et les ajustements, demandant une organisation minutieuse et une grande adaptabilité.",
    text3:"J'ai réussi à concevoir et à prototyper un système fonctionnel pour le « Jeu des Couleurs », en développant un module plug-and-play. J'ai soudé deux versions du prototype, permettant une intégration facile et un remplacement rapide en cas de défaillance. En outre, j'ai rédigé une documentation complète expliquant les étapes nécessaires pour reproduire et comprendre le système, facilitant ainsi la transition du projet à l'équipe de la Cité du Vin. Je souhaite exprimer ma sincère gratitude à mon maître de stage et à toute l'équipe de la Cité du Vin pour leur soutien constant, leurs conseils précieux et leur patience tout au long de ce stage. Leur expertise et leur encadrement ont été essentiels à la réussite de ce projet. Cette expérience m'a permis de développer des compétences techniques importantes et de mieux comprendre le fonctionnement des systèmes en milieu professionnel. Merci à tous pour cette opportunité et pour la confiance accordée dans la réalisation de ces missions.",
    illuPrincipal:"",
    illu: []
  },
  ];





</script>

<style scoped>

.container {
  display: flex;
  flex-direction: row;
  justify-content: center;
  min-height: 100dvh;
  margin-top: 10dvh;
  gap: 2dvw;
}


.content {
  width: 45dvw;
  margin-top: 10dvh;
  gap: 8dvh;
  display: flex;
  flex-direction: column;
}

.head {
  display: flex;
  flex-direction: column;
}

.title {
  font-weight: 400;
  color: var(--primary);
  font-size: 40px;
}

.date {
  text-transform: uppercase;
  color: var(--medium);
  font-size: 15px;
}

p {
  color: var(--medium);
  font-size: 18px;
}

.illu-principal {
  width: 100dvw;
  background-color: var(--light);
  height: 70dvh;
  margin-left: calc((-100dvw + 45dvw - 10dvw) / 2);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}

.illu-principal img {
  width: 100%;
}

.illu-table {
  display: flex;
  flex-direction: row;
  overflow: hidden;
  width: 100dvw;
  height: 30dvh;
  justify-content: center;
  margin-left: calc((-100dvw + 45dvw) / 2);
  gap: 1dvw;
}

.illu {
  height: 100%;
  background-color: var(--light);
}

.illu img {
  height: 100%;
}

.foot {
  display: flex;
  flex-direction: column;
  margin: 5dvh;
  margin-left: -8dvw;
  align-items: center;
  gap: 5dvh;
}

.foot h2 {
  color: #00B578;
  font-size: 30px;
  font-weight: bold;
  text-transform: uppercase;
}

.foot-content {
  display: flex;
  flex-direction: row;
  gap: 2dvw;
}

.foot-content a {
  aspect-ratio: 25/9;
  display: flex;
  text-decoration: none;
  background-color: #F2F3F7;
  height: calc(15dvh - 60px);
  border-radius: 10px;
  padding: 30px;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.foot-content h3 {
  color: var(--medium);
  font-size: 15px;
  line-height: 16px;
}

.foot-content h4 {
  color: var(--primary);
  font-size: 20px;
  max-width: 100%;
  overflow: hidden;
  text-wrap: nowrap;
  text-overflow: ellipsis;
  text-transform: uppercase;
}

.foot-content p {
  color: var(--medium);
  font-size: 12px;
}


.info {
  display: flex;
  flex-direction: column;
  width: 8dvw;
  margin-top: 12dvh;
  font-size: 12px;
}

.card {
  display: flex;
  flex-direction: row;
  justify-content: end;
  align-items: center;
  gap: 1dvw;
}

.card .data {
  display: flex;
  flex-direction: column;
  align-items: end;
}

.card .picture {
  aspect-ratio: 1/1;
  border-radius: 50%;
  border: var(--medium) solid 2px;
  width: 40px;
}

.info .card p {
  font-size: 12px;
}

</style>