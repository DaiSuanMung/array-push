<template>
     <div class="col-6">
       <input class="form-control m-3" type="text" v-model="inputText" id="inputTest">
     
      <table class="table">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">Name</th>
      <th scope="col">Category</th>
      <th scope="col">Start</th>
      <th scope="col">End</th>
      <th scope="col">Location</th>
    </tr>
  </thead>
  <tbody>
    <tr v-for="(item,i) in items" :key="i">
      <th scope="row">{{i+1}}</th>
      <td>{{item.name}}</td>
      <td>{{item.category}}</td>
      <td>{{item.start}}</td>
      <td>{{item.end}}</td>
        <td>{{item.location}}</td>
    </tr>
     
     </tbody>
      </table>
     </div>
</template>

<script>
export default {
    name: 'result',
   props:{
    filterArray:{String, default: null},
       items:{
           type: Array
       }
   },
    data:()=>({
     inputText: '',
   }),
 
   created(){
    
  },
  methods:{
  },

   computed: {
//       filteredList() {
//         let items = JSON.parse(JSON.stringify(this.items));

//         switch (this.filterArray) {
//           case 'year':
//             items = items.sort((a,b) => a.start-b.start);
//             break;
//          case 'Naypyidaw':
//           items =  this.items.filter(loc => loc.location === 'Naypyidaw');
//             break;
//           case 'between':
//             items =  this.items.filter(loc=> loc.start > 1992);
//             break;
//           default:
//             items =  this.items;
//             break;
//           }

//         if(this.inputText) {
//        return   items = items.filter(d=>{
//            let  allOf = [d.name.toLowerCase(),d.category.toLowerCase(),d.location.toLowerCase()]
//          //   return allOf.toString().indexOf(this.inputText.toLowerCase())>-1
//       return allOf.includes(this.inputText.toLowerCase())
  
//             });
        
//         }

// return items;
//     }
  },

  }

</script>