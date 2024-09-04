<template>
  <div>
    <HeaderComponent />
    <b-container fluid class="profile" :style="backgroundStyle">
      <!-- ▼ Commint Profile Start ▼ -->
      <b-row class="justify-content-center">
        <b-col md="8" lg="6" class="text-center">
          <h1 class="display-4 mb-4">{{ name }}</h1>
          <b-img :src="profileImage" alt="Profile" class="rounded-circle mb-4" width="300" height="300" />
          <h2 class="h4 mb-3">Profile</h2>
          <b-card class="mb-4" body-class="p-4">
            <b-list-group flush>
              <b-list-group-item v-for="(entry, index) in careerHistory" :key="index" class="list-group-item-action" style="text-align: left;">
                {{ entry.date }} - {{ entry.description }}
              </b-list-group-item>
            </b-list-group>
          </b-card>
        </b-col>
      </b-row>
      <!-- ▲ Commint Profile End ▲ -->

      <!-- ▼ Commint Projects Start ▼ -->
      <b-row class="justify-content-center">
        <b-col md="8" lg="6" class="text-center">
          <h2 class="h4 mb-3">Commit Projects</h2>
          <b-card-group deck class="mb-4">
            <!-- imageでProjectのアイコンをnameの横に追加する -->
            <!-- backgroundでProjectの背景画像を追加する -->
            <b-card
              v-for="(project, index) in commitProjects"
              :key="index"
              class="mb-4"
              :title="project.name"
              :footer="project.link ? 'Detail' : ''"
              :footer-class="project.link ? 'text-center' : ''"
              :footer-href="project.link"
              target="_blank"
              header-class="bg-primary text-white"
            >
              <b-card-text>
                {{ project.description }}
              </b-card-text>
              <b-list-group flush>
                <b-list-group-item v-for="(role, rIndex) in project.roles" :key="rIndex" class="list-group-item-action">
                  {{ role }}
                </b-list-group-item>
              </b-list-group>
            </b-card>
          </b-card-group>
        </b-col>
      </b-row>
      <!-- ▲ Commint Projects End ▲ -->
    </b-container>
    <FooterComponent />
  </div>
</template>

<script>
import HeaderComponent from '@/components/header-pc.vue';
import FooterComponent from '@/components/footer-pc.vue';

// ここは後ほど、WebAPIから取得したデータを使えるようにする
// Googleスプレッドシート&AppScriptを使ったGoogleAPIを使用予定
export default {
  components: {
    HeaderComponent,
    FooterComponent,
  },
  data() {
    return {
      // ここも後ほどAPIにするから@assets/imagesもファイル格納じゃなくて、どっかにアップした画像そのものを使用するように対応する
      name: 'SHO43',
      profileImage: require('@/static/top/PFP.png'),
      backgroundImage: require('@/static/back.png'),
      careerHistory: [
        { date: '2023.04', description: 'Meet Solana.' },
        { date: '2023.07', description: 'Join Solana Japan team.' },
        { date: '2023.08', description: 'Join Scannner as Community Manager.' },
        { date: '2024.05', description: 'Join Superteam Japan Member.' },
      ],
      commitProjects: [
        {
          name: 'Scannner',
          image: 'https://pbs.twimg.com/profile_images/1689488626709913600/8gfY7I1x_400x400.png',
          background: 'https://pbs.twimg.com/profile_banners/1684457449225592833/1701673664/1500x500',
          roles: ['Community Manager'],
          description: 'Solana BlockChain Game "Scannner" Community Manager.',
          link: 'https://scannner.io/'
        },
        {
          name: 'Scannner2',
          image: 'https://pbs.twimg.com/profile_images/1689488626709913600/8gfY7I1x_400x400.png',
          background: 'https://pbs.twimg.com/profile_banners/1684457449225592833/1701673664/1500x500',
          roles: ['Community Manager'],
          description: 'Solana BlockChain Game "Scannner" Community Manager.',
          link: 'https://scannner.io/'
        }
      ]
    };
  },
  computed: {
    backgroundStyle() {
      return {
        background: 'linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url(' + this.backgroundImage + ')',
        backgroundSize: 'cover',
        backgroundPosition: 'center',
        minHeight: '100vh',
        padding: '50px 0',
        position: 'relative',
        overflow: 'hidden'
      };
    }
  },
};
</script>

<style scoped>
.profile::before {
  content: '';
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 1;
}

.profile {
  .mb-3.h4{
    color: #fff;
    font-style: bold;
    font-size: 2.0rem;
  }
  .mb-4.display-4{
    color: #fff;
    font-style: bold;
  }
  position: relative;
  overflow: hidden;
  font-family: 'Oswald', sans-serif;
}
</style>
