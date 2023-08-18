<template>
  <div>
    <div class="main-view" :class="{ hidden: scrolledDown }">
      <div class="sider sidebar">
        <div class="holder">
          <div class="xx" role="navigation" aria-labelledby="main-nav-heading">
            <div class="title" id="main-nav-heading">Table of Contents</div>
            <a class="listitem" href="#intro">Intro</a>
            <a class="listitem" href="#Intro">About Me</a>
            <a class="listitem" href="#Projects">Projects</a>
            <a class="listitem" href="#CV">Resume</a>
            <a class="listitem" href="#Contact">Contact</a>
            <br />
            <div class="contact">
              <a href="mailto:yourmail@gmail.com"> andyzhou443@gmail.com</a>
              <a href="https://github.com/andyzhou443/"
                >github.com/andyzhou443</a
              >
              <a href="tel:+1-347-679-4597">+1-347-679-4597</a>
              <br />
              <!--<a href="/impressum">Impressum</a> LEGAL INFORMATION-->
            </div>
          </div>
        </div>
      </div>
      <div class="main">
        <section id="intro">
          <div class="txt">
            <h1>
              Hi, my name is 
              <br />
              Andy Zhou
              <br />
              I am a Software Engineer from New York City!
            </h1>
            <br />
            <a href="#Intro">About Me <Fa fa="arrow-down" /></a>
          </div>
        </section>
        <section id="Intro" aria-labelledby="intro-heading">
          <h2 id="intro-heading">About Me</h2>
          <span>
            I earned my degree in Computer Engineering from the 
            City College of New York in 2023. While my journey 
            began with a fascination for 3D printers, it evolved 
            into a deep exploration of Embedded Software Engineering 
            and Machine Learning. Today, I am dedicated to embracing 
            and conquering the boundless array of challenges that 
            the world of programming presents, continually striving 
            to expand my knowledge and skills.
          </span>
        </section>
        <section id="Projects" aria-labelledby="projects-heading">
          <h2 id="projects-heading">Projects</h2>
          <div class="cards">
            <div class="card-col">
              <Card :item="projects[0]" :txt="select" />
              <Card :item="projects[1]" :txt="select" />
              <Card :item="projects[4]" :txt="select" />
            </div>
            <div class="card-col">
              <Card :item="projects[2]" :txt="select" />
              <Card :item="projects[3]" :txt="select" />
            </div>
          </div>
        </section>
        <section id="Experiences"></section>
        <section id="CV" aria-labelledby="CV-heading">
          <h2 id="CV-heading">Curriculum Vitae</h2>
          <div class="CV">
            <h3>Experience</h3>
            <div class="cont" v-for="i in experiences" :key="i.location">
              <span>{{ i.date }}</span>
              <span>{{ i.location }}</span>
              <span>{{ i.company }}</span>
              <span>{{ i.title }}</span>
              <span>{{ i.txt }}</span>
            </div>
          </div>
          <div class="education">
            <h3>Education</h3>
            <div class="cont" v-for="i in education" :key="i.title">
              <span>{{ i.date }}</span>
              <span>{{ i.location }}</span>
              <span>{{ i.company }}</span>
              <span>{{ i.title }}</span>
              <span>{{ i.txt }}</span>
            </div>
          </div>
          <br />
          <a href="Andy_Zhou_Resume.pdf"> <Fa fa="file-pdf" /> Download Resume </a>
        </section>
        <section id="Contact" aria-labelledby="contact-heading">
          <h2 id="contact-heading">Contact</h2>
          andyzhou443@gmail.com
          <br />
          <a href="mailto:andyzhou443@gmail.com">
            <Fa fa="envelope-o" /> Email me
          </a>
          <br />
          <br />
          +1-347-679-4597
          <br />
          <a href="tel:+1-347-679-4597"> <Fa fa="phone" /> Call</a>
        </section>
      </div>
    </div>
    <PopOver :selected="selected" :closeWindow="closePopOver" />
  </div>
</template>

<script>
import Card from './globals/Card.vue';
import Fa from './globals/Fa.vue';
import PopOver from './PopOver.vue';

export default {
  components: {
    Card,
    Fa,
    PopOver,
  },
  data: () => ({
    experiences: [
      {
        date: 'Jun 2022 - Aug 2022',
        location: 'Dulles, VA',
        company: 'Northrop Grumman',
        title: 'Flight Software Engineer Intern',
        txt: 'C++, Python, SVN, Embedded Software Engineering',
      },
      {
        date: 'Jun 2021 - Dec 2021',
        location: 'Montclair, NJ',
        company: 'Montclair State University',
        title: 'Lead Researcher',
        txt: 'Python, Streamlit, Google Cloud, Web Development',
      },
      {
        date: 'May 2021 - Sep 2021',
        location: 'New York, NY',
        company: 'HydroCosm',
        title: 'Software Engineer Intern',
        txt: 'Java, Android Studio, Google Cloud, Google Maps API, Application Development',
      },
    ],
    education: [
      {
        date: 'Sep 2018 - May 2023',
        location: 'New York, NY',
        company: 'The City College of New York',
        title: 'Bachelors of Engineering Computer Engineering',
        txt: 'Honors: Manga Cum Laude Honors, S Jay Levy Fellow (Top 20% of students), President of CCNY Robotics Club',
      },
    ],
    projects: [
      {
        id: 0,
        images: [
          {
            img: 'images/Productify.gif',
          },
          {
            img: 'images/Productify.jpg',
          },
        ],
        title: 'Productify',
        tags: ['Javascript', 'React Native', 'Expo Go', 'Google Cloud'],
        demo: '',
        source: '',
      },
      {
        id: 1,
        images: [
          {
            img: '',
          },
          {
            img: 'images/MBSAM.jpg',
          },
        ],
        title: 'Metric-based Software Assessment',
        tags: ['Python', 'Streamlit', 'Google Cloud', 'IEEE'],
        demo: '',
        source: 'https://github.com/andyzhou443/PacBot-CCNY',
        publication: 'https://ieeexplore.ieee.org/document/9671334',
      },
      {
        id: 2,
        images: [
          {
            img: 'images/PacBot.gif',
          },
          {
            img: 'images/PacBot.jpg',
          },
        ],
        title: 'Harvard Pac Bot Competition',
        tags: ['C++', 'Python', 'CircuitPython', 'UART', 'Teensy 4.1', 'Raspberry Pi', 'Solidworks', 'Electronics', 'Robotics'],
        demo: '',
        source: 'https://github.com/andyzhou443/PacBot-CCNY',
      },
      {
        id: 3,
        images: [
          {
            img: 'images/PacManML.gif',
          },
          {
            img: 'images/PacManML.jpg',
          },
        ],
        title: 'Pac Man Reinforcement Learning',
        tags: ['Python', 'OpenAI Gym', 'Pytorch', 'Stable-Baseline3'],
        demo: '',
        source: 'https://github.com/w-smesnoj/parallax-swipe',
      },
      {
        id: 4,
        images: [
          {
            img: 'images/3DPrinterRound.gif',
          },
          {
            img: 'images/.MasterAssemblyBelt.JPG',
          },
        ],
        title: 'Fusion Core 3D Printer',
        tags: ['Solidworks', 'Electronics'],
        demo: '',
        source: 'https://github.com/andyzhou443/FusionCore3DPrinter',
      },
    ],
    selected: null,
  }),
  mounted() {
    window.onscroll = this.lodash.debounce(this.scrollcalc, 5);
    this.scrollcalc();
    let anchorlinks = document.querySelectorAll('a[href^="#"]');

    for (let item of anchorlinks) {
      item.addEventListener('click', (e) => {
        let hashval = item.getAttribute('href');
        let target = document.querySelector(hashval);
        target.scrollIntoView({
          behavior: 'smooth',
          block: 'start',
        });
        history.pushState(null, null, hashval);
        e.preventDefault();
      });
    }
  },
  methods: {
    select: function (id) {
      this.selected = this.projects.find((x) => x.id === id);
    },
    closePopOver() {
      this.selected = null;
    },
    scrollcalc() {
      let mainNavLinks = document.querySelectorAll('.xx a');
      let fromTop = document.documentElement.scrollTop;
      let navbarHeight = 200;

      mainNavLinks.forEach((link) => {
        if (link.hash == '') return;

        let section = document.querySelector(link.hash);
        if (section == null) return;
        if (
          section.offsetTop <= fromTop + window.innerHeight &&
          section.offsetTop + section.offsetHeight > fromTop + navbarHeight
        ) {
          link.classList.add('current');
          let allCurrents = document.querySelectorAll('.current');
          let allFirsts = document.querySelector('.first');
          if (allFirsts != null) {
            allFirsts.classList.remove('first');
          }
          allCurrents[0].classList.add('first');
        } else {
          link.classList.remove('current');
        }
      });
    },
  },
  props: {
    scrolledDown: Boolean,
  },
};
</script>

<style lang="scss" scoped>
#intro {
  .txt {
    a {
      display: none;
      text-decoration: none;
      color: white;
    }
  }
}
@media screen and (max-width: 680px) {
  .cards {
    display: block !important;
  }
  .card {
    width: 100% !important;
    height: 33rem !important;
  }
  #intro {
    .txt {
      a {
        display: hidden;
      }
    }
  }
  .hidden {
    #intro {
      .txt {
        a {
          display: block;
        }
      }
    }
  }
  .cont {
    grid-template-areas:
      'date'
      'extra'
      'title'
      'location'
      'txt' !important;
    grid-template-columns: 100% !important;
  }
  .txt h1 {
    font-size: 7vw !important;
  }
}
#Contact,
#CV {
  a {
    color: white;
    i {
      font-size: 0.9rem;
    }
  }
  a:hover {
    color: hsl(0deg 0% 63%);
  }
}
.education,
.CV {
  h3 {
    font-size: 0.9rem;
  }
  cursor: default;
}
.cont {
  display: grid;
  grid-template-areas:
    'date title'
    'extra location'
    '. txt';
  grid-template-columns: 11rem 370px;
  gap: 0rem 1rem;
  margin-bottom: 1.3rem;
  span:nth-child(1) {
    grid-area: date;
    font-weight: 600;
    font-size: 0.9rem;
    color: hsl(0deg 0% 63%);
    letter-spacing: -0.02rem;
  }
  span:nth-child(2) {
    grid-area: extra;
    font-size: 0.87rem;
    color: hsl(0deg 0% 63%);
    letter-spacing: -0.02rem;
  }
  span:nth-child(3) {
    grid-area: title;
  }
  span:nth-child(4) {
    grid-area: location;
    font-size: 0.9rem;
    color: hsl(0deg 0% 63%);
  }
  span:nth-child(5) {
    grid-area: txt;
    font-size: 0.9rem;
    color: hsl(0deg 0% 63%);
  }
}

.contact {
  // margin: 2rem 0rem;
  display: flex;
  flex-flow: column;
  gap: 0.7rem;
  width: 100%;
  transition: opacity 0.3s;
  a {
    text-decoration: none;
    color: var(--txt-med);
    padding: 0rem 1.5rem;
  }
}
.contact {
  a:hover {
    color: white;
  }
}
#Intro {
  a {
    color: var(--accent-1);
    text-decoration: none;
    i {
      margin-left: 0.4rem;
    }
  }
}
section {
  padding: 6rem 0rem;
  &:empty {
    display: none;
  }
  span {
    display: block;
    max-width: 550px;
  }
}
.mainitem-active {
  border-radius: 6px;
  background: hsl(220 100% 71% / 0.11);
  color: hsl(220 100% 53% / 1) !important;
  margin-bottom: 0.3rem;
}
.title {
  font-size: 12px !important;
  font-weight: 700 !important;
  margin: 0.2em 0em 1rem 0rem;
  text-transform: capitalize;
  color: #b2b2b2;
  text-transform: uppercase;
  letter-spacing: 0.02rem;
  width: 100%;
  text-align: center;
}
.xx {
  display: flex;
  flex-flow: column;
  align-items: self-end;
  gap: 0.7rem;
  a {
    transition: min-width 0.3s, border 0.3s, padding 0.3s, box-shadow 0.3s,
      background 0.15s;
    width: fit-content;
    min-width: 210px;
    max-width: -webkit-fill-available;
  }
}
.listitem:nth-child(2).first {
  background: var(--accent-1);
}
.listitem:nth-child(3).first {
  background: var(--accent-2);
}
.listitem:nth-child(4).first {
  background: var(--accent-3);
}
.listitem:nth-child(5).first {
  background: var(--accent-4);
}
.listitem:nth-child(6).first {
  background: var(--accent-5);
}
.listitem:nth-child(7).first {
  background: var(--accent-6);
}
.listitem:hover {
  background-color: hsla(0, 0%, 80%, 0.15);
}
.listitem {
  text-decoration: none;
  display: block;
  padding: 0.75rem 1.8rem;
  margin-right: 1rem;
  color: white;
  font-size: 0.95em;
  cursor: pointer;
  transition: border 0.3s, padding 0.3s, box-shadow 0.3s, background 0.15s;
  border-left: 2px solid transparent;
  font-weight: 500;
  border-radius: 0.4rem;
}
.mainitem {
  padding: 0.5rem 0.5rem;
}
.current {
  border-left: 6px solid #ffffff1c;
  // box-shadow: 0px 0px 0px 0px black;
}
.first {
  color: black;
  color: black !important;
  padding-left: 2rem;
  font-weight: 600;
  transform-origin: left;
  animation: pop 0.25s ease-out;
}
@keyframes pop {
  35% {
    transform: scale(1.05);
  }
  75% {
    transform: scale(0.96);
  }
  100% {
    transform: scale(1);
  }
}
</style>

<style lang="scss" scoped>
.card-col:nth-child(2) {
  margin-top: 5rem;
}
.cards {
  display: flex;
  gap: 1.7rem;
}
.card-col {
  display: flex;
  flex-flow: column;
  gap: 1.7rem;
}

.sidebar,
.sideoptions {
  transition: width 0.3s;
}
@media screen and (max-width: 1300px) {
  .main-view {
    grid-template: 'siderbar main main';
  }
  .sideoptions {
    display: none;
  }
}
@media screen and (max-width: 1023px) {
  .main-view {
    grid-template: 'main main main' !important;
    grid-template-columns: 1fr !important;
    width: auto !important;
  }
  .sidebar {
    display: none;
  }
}

.holder {
  scrollbar-color: #bebebe transparent;
  scrollbar-width: thin;
}
.holder:hover {
  scrollbar-color: #bebebe #f2f2f2;

  scrollbar-width: revert !important;
}

.holder::-webkit-scrollbar {
  width: 15px;
  padding: 10px;
}

.holder::-webkit-scrollbar-thumb {
  border-radius: 10px;
  /* background-color: #bebebe; */
  border: 5px solid transparent;
  background-clip: content-box;
}

.sider:hover .holder::-webkit-scrollbar {
  width: 15px;
}

.sider:hover .holder::-webkit-scrollbar-track {
  border-radius: 10px;
}

.sider:hover .holder::-webkit-scrollbar-thumb {
  border: 0;
  border-radius: 10px;
}

.sider:hover .holder::-webkit-scrollbar-thumb:hover {
  background: #818b99;
}
.sider {
  height: 100%;
  width: 310px;
}
.holder {
  padding: 1rem;
  position: -webkit-sticky;
  position: sticky;
  top: 60px;
  height: calc(100vh - 90px);
  overflow-y: auto;
}
.sidebar {
  justify-self: right;
}

.link .fas {
  font-size: 0.8rem;
}

.filters > .text {
  padding: 0.5em 0em;
  display: block;
}
.filters > .text > input {
  width: 125px;
  border: 0;
  background: 0;
  margin: 0rem 0.3rem;
  border-bottom: 1px solid gray;
}
.filters {
  margin: 2rem 0rem;
}

h2 {
  font-size: 1rem;
  color: var(--txt-med);
  margin-bottom: 2rem;
  cursor: default;
}
.main-view {
  display: grid;
  grid-template: 'siderbar main';
  grid-template-columns: 1fr minmax(600px, 770px);
  width: fit-content;
  margin-left: auto;
  margin-right: auto;
  z-index: 100;
}
div > .main {
  max-width: 1000px;
  margin: auto;
  padding: 2rem;
  box-sizing: border-box;
  line-height: 1.6;
  color: var(--txt);
  padding: 1.5rem 1.5rem 80vh 1.5rem;
  width: 100%;
  z-index: 100;
}
</style>
<style scoped lang="scss">
.txt h1 {
  font-size: 3rem;
  margin: 0.2rem 0;
  line-height: 1.3;
  max-width: 600px;
}
.main-view {
  transition: background 0.3s;
  section {
    transition: opacity 0.3s;
  }
}

.main-view,
.main-view {
  .main .holder,
  .sider {
    transition: background 0.3s;
  }
}
.hidden {
  .xx {
    a {
      transition: min-width 0.3s;
      min-width: 0px;
      width: fit-content;
    }

    .title {
      opacity: 0;
    }
    .listitem {
      border: 0;
      color: black;
    }
    .listitem:nth-child(2) {
      background: var(--accent-1);
    }
    .listitem:nth-child(3) {
      background: var(--accent-2);
    }
    .listitem:nth-child(4) {
      background: var(--accent-3);
    }
    .listitem:nth-child(5) {
      background: var(--accent-4);
    }
    .listitem:nth-child(6) {
      background: var(--accent-5);
    }
    .listitem:nth-child(7) {
      background: var(--accent-6);
    }
    .listitem:hover {
      background: #fbfbfb;
    }
  }
  .contact,
  section {
    opacity: 0;
  }
  .main,
  .holder,
  .sider {
    background: transparent !important;
  }
  background: transparent !important;
  box-shadow: unset !important;
}
#intro {
  opacity: 100;
}
</style>
