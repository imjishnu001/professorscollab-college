<template>
  <div absolute>
    <v-img :aspect-ratio="16/5" src="../assets/College.jpg"></v-img>
    <h1 class="ma-5 pa-5 grey--text">About Xyz College</h1>
    <p class="ma-5 pa-5 grey-text">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Porro quas eius, at ab inventore nihil enim autem non excepturi beatae sequi, unde quia ipsum totam dolor architecto! Sapiente, omnis quis.
      Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quae voluptatem vero doloremque exercitationem ipsam omnis harum deserunt adipisci dolorum alias officiis mollitia aspernatur voluptate quam libero, doloribus eaque earum incidunt.
      Lorem ipsum dolor sit, amet consectetur adipisicing elit. Ipsa, quas provident! Debitis reiciendis eius amet hic qui, facere, laborum sed possimus cupiditate assumenda eaque molestias nesciunt voluptates distinctio, voluptate aliquam. Lorem ipsum dolor sit amet consectetur adipisicing elit. Quos iure consequatur magni, facilis temporibus, provident aperiam iusto expedita nemo cumque quibusdam velit earum molestiae debitis labore soluta rerum porro at. Lorem ipsum dolor sit, amet consectetur adipisicing elit. Corrupti id voluptates ipsam pariatur quia, quasi reiciendis asperiores nobis assumenda temporibus sed repellendus maiores, sit suscipit quaerat dignissimos ratione quo fuga!
    </p>
    <h1 class="ma-5 pa-5 grey--text">Professors</h1>
    <v-container class="ma-10">
      <v-layout row wrap>
        <v-flex xs12 sm6 md4 lg3 v-for="professor in professors" :key="professor.name">
          <v-card class="text-center ma-5 pa-5">
            <v-responsive class="pt-4">
                <v-avatar size="100">
                  <img :src="professor.path">
                </v-avatar>
            </v-responsive>
            <h3 class="subheading">{{professor.name}}</h3>
            <p>Exp: {{professor.experince}}</p>
            <div v-show="showMore">
            <div v-show="professor.project">
              <p>Project(s)</p>
              <p v-for="(key, value) in professor.projects" :key="value">
                {{key}}
              </p>
            </div>
            <div v-show="professor.researchPaper">
              <p>Paper(s)</p>
              <p v-for="(key, value) in professor.papers" :key="value">
                {{key}}
              </p>
            </div>
            <p class="success--text">Rank: {{professor.rank}}</p>
            </div>
            <v-card-action>
              <v-btn @click="showMore = !showMore" class="primary">
                <v-icon>mdi-binoculars</v-icon> Read More
              </v-btn>
            </v-card-action>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
    <h1 class="ma-5 pa-5 grey--text">Top 10 projects</h1>
    <v-container class="ma-5">
        <v-layout row wrap>
          <v-flex sx12 sm6 md4 lg3 v-for="student in students" :key="student.name">
            <v-card class="text-center ma-5 pa-5">
            <p class="grey--text heading">{{student.name}}</p>
            <p class="grey--text subheading">{{student.project}}</p>
            </v-card>
          </v-flex>
        </v-layout>
    </v-container>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  data(){
    return{
      professors:[
        {name:'Yash Gupta',experince:'3 Years',projects:{project1:'Students management system',project2:'Report analysis automation'},project:true,rank:'#43',researchPaper:true,papers:{paper1:'Analysis of cryptocurrency'},path:'/Yash.jpg'},
        {name:'Mukesh Kumar',experince:'5 Years',projects:{project1:'Students management system'},project:true,rank:'#53',researchPaper:true,papers:{paper1:'A step towards data driven world'},path:'/Mukesh.jpg'},
        {name:'Sailesh Topno',experince:'3 Years',projects:{project1:'Devops tracker'},project:true,rank:'#35',path:'/Sailesh.jpg',researchPaper:true,papers:{paper1:'Impact of unwanted server calls'}},
        {name:'Jishnu Mohan',experince:'1 Years',projects:{project1:'Leave Tracker'},project:true,rank:'#2',researchPaper:true,papers:{paper1:'Why IOT is the next bif thing'},path:'/jishnu.jpg'},
        //{name:'Shubham Gupta',experince:'5 Years',projects:{project1:'Leave Tracker'},project:true,researchPaper:true,papers:{paper1:'Impact of unwanted server calls'},rank:'#5'},
      ] ,
      students:[
        {name:'Deepika Choubey',project:'Web process automater'},
        {name:'Jishnu Mohan',project:'Employee management system'},
        {name:'Shubham Madan',project:'Object movement tracker'},
        {name:'Mahesh Kumar',project:'Exam management system'},
        {name:'Rahul Singh',project:'Web Scrapper'},
        {name:'Ankitha Mishra',project:'DevOps action automation system'},
        {name:'Vivek kumar',project:'Template management system'},
        {name:'Bhrath Gowda',project:'Project management system'},
        {name:'Salman Adam',project:'Device specs comparison system'},
        {name:'Anurika Singh',project:'Simple version control system'},
      ],
      showMore:false, 
    }
  },  
}
</script>

<style>
.pass{
  border-left: 8px solid green;
}
.fail{
  border-left: 8px solid red;
}
*{
  margin: 0;
  padding: 0;
}
body{
  padding: 0;
  margin: 0;
  background-color: aqua;
}
</style>
