<template>
    <div id="liste">
   <div class="panel panel-default">
                <div class="panel-heading" style="font-weight:bold"><span class="glyphicon glyphicon-align-justify"></span> Tous les fruits </div>
                <div class="row">
                    <div class="search-wrapper panel-heading col-sm-12">
                        <input class="form-control" type="text" v-model="searchQuery" placeholder="Rechercher" />
                    </div>                        
                </div>
                <div class="panel-body" style="max-height: 400px;overflow-y: scroll;display: grid; margin-top: 30px; margin-bottom: 40px;">
                    <table v-if="resources.length" class="table">
                        <thead>
                            <tr>
                                <th>Fruits</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr v-for="item in filteredResources">
                                <td><a v-bind:href="item.uri" target="_blank">{{item.title}}</a></td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
</div>
</template>

<script>
export default {
    name: '#liste',
  data() {
    return {
      searchQuery:'',
    resources:[
    {title:"Pomme",uri:"Pomme.com",category:"P",icon:null},
    {title:"Banane",uri:"Banane",category:"B",icon:null},
    {title:"Kiwi",uri:"Kiwi.com",category:"K",icon:null},
    {title:"Poire",uri:"Poire.com",category:"P",icon:null},
    {title:"Kaki",uri:"Kaki.com",category:"K",icon:null},
    {title:"Orange",uri:"Orange.com",category:"O",icon:null},
    {title:"Fraise",uri:"Fraise.com",category:"F",icon:null},
    {title:"Framboise",uri:"Framboise.com",category:"F",icon:null}
    ]
    };
  },
  computed: {
    filteredResources (){
      if(this.searchQuery){
      return this.resources.filter((item)=>{
        return item.title.startsWith(this.searchQuery);
      })
      }else{
        return this.resources;
      }
    }
  }
}
</script>

<style scoped>
a:-webkit-any-link {
text-decoration: none;
color:black
}

a:-webkit-any-link:hover {
  color:blue
  }

  th {
font-size: 18px;
text-decoration: underline;
  }

</style>