 <template>
  <div id="app">
  <md-card>
<md-card-header>
  <div class="md-title">
  Vue materail Design is Cooool!
</div>
    <div class="md-subhead">
  by Eric Li
</div>
</md-card-header>
<md-bottom-bar>
  <md-bottom-bar-item md-icon="history">Recents</md-bottom-bar-item>
  <md-bottom-bar-item md-icon="favorite" md-active>Favorites</md-bottom-bar-item>
  <md-bottom-bar-item md-icon="near_me">Nearby</md-bottom-bar-item>
</md-bottom-bar>

<md-bottom-bar>
  <md-bottom-bar-item md-icon-src="assets/icon-home.svg">Recents</md-bottom-bar-item>
  <md-bottom-bar-item md-icon-src="assets/icon-home.svg" md-active>Favorites</md-bottom-bar-item>
  <md-bottom-bar-item md-icon-src="assets/icon-home.svg">Nearby</md-bottom-bar-item>
</md-bottom-bar>
  <md-card-content>
    <md-button class="md-raised">Default</md-button>
    <md-button class="md-raised md-primary">Primary</md-button>
    <md-button class="md-raised md-accent">Accent</md-button>
    <md-button class="md-raised md-warn">Warn</md-button>
    <md-button class="md-raised md-primary" disabled>Disabled</md-button>
    <md-button class="md-raised md-dense">Dense</md-button>
    <hr>
    <md-button class="md-raised md-primary" v-on:click="fillTable()">Fill Table</md-button>
    <md-button class="md-raised md-warn" v-on:click="clearTable()">Clear Table</md-button>

  </md-card-content>
  <md-table >
  <md-table-header>
    <md-table-row>
      <md-table-head>First name</md-table-head>
      <md-table-head>Last name</md-table-head>
	  <md-table-head>Email</md-table-head>
    </md-table-row>
  </md-table-header>

  <md-table-body>
    <md-table-row v-for="contact in contacts">
      <md-table-cell>{{contact.firstname}}</md-table-cell>
           <md-table-cell>{{contact.lastname}}</md-table-cell>
		     <md-table-cell>{{contact.ëmail}}</md-table-cell>
    </md-table-row>
  </md-table-body>
</md-table>
  </md-card>
  </div>
</template>

<script>
import Search from './components/Search'

export default {
  name: 'app',
  data: function(){
    return{
      contacts:[]
    }
  },
  methods:{
    fillTable:function() {
      this.contacts.push({firstname:"Eric",lastname:"Li",email:"ericli@gmail.com"})
        this.contacts.push({firstname:"Johan",lastname:"Smith",email:"johansmith@gmail.com"})
    },
    clearTable:function(){
      this.contacts.splice(0,this.contacts.length);
    }
  }

}
</script>

<style>
#app {

  margin-top: 60px;
    margin-left: 30px;
      margin-right: 30px;
}
</style>
