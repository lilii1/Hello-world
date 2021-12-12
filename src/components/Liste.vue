<template>
    <div class="liste">
   <div class="panel panel-default">
               <h1>CRYPTO TRACKER</h1>
                
                    <div class="searchtext">
                        <input class="search" type="text" v-model="searchQuery" placeholder="Rechercher" />
                    </div>                        
                </div>
                <div class="tableau">
                    <table v-if="resources.length" class="table">
                        <tbody>
                            <tr v-for="item in filteredResources" :key="item">
                                <td><a v-bind:href="item.uri" target="title">{{item.title}}</a></td>
                                <td><a v-bind:href="item.uri" target="category">{{item.category}}</a></td>
                                 <td><a v-bind:href="item.uri" target="number">{{item.number}}</a></td> 
                                  <td><a v-bind:href="item.uri" target="code">{{item.code}}</a></td> 
                                <td><a v-bind:href="item.uri" target="percentage">{{item.percentage}}</a></td> 
                                <td><a v-bind:href="item.uri" target="password">{{item.password}}</a></td> 
                            </tr>
                        </tbody>
                    </table>
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
    {title:"Bitcoin",category:"BTC",number:"₺689939",code:"₺276 792 760 664",percentage:"12,79%",password:"Mkt Cap: ₺13 044 577 536 191"},
    {title:"Ethereum",category:"ETH",number:"₺56170",code:"₺197 300 412 734",percentage:"0.66%",password:"Mkt Cap: ₺6 672 759 316 617"},
    {title:"Binance Coin",category:"BNB",number:"₺7881.07",code:"₺10 705 028 311",percentage:"2.46%",password:"Mkt Cap: ₺1 327 171 479 336"},
    {title:"Tether",category:"USDT",number:"₺13.9",code:"₺592 958 742 894",percentage:"0.40%",password:"Mkt Cap: ₺1 073 399 848 598"},
    {title:"Solana",category:"SOL",number:"₺2360.14",code:"₺15 351 183 976",percentage:"0.65%",password:"Mkt Cap: ₺726 089 449 125"},
    {title:"Cardano",category:"ADA",number:"₺18.7",code:"₺20 501 760 931",percentage:"4.57%",password:"Mkt Cap: ₺600 127 155 445"},
    {title:"USD Coin",category:"USDC",number:"₺13.88",code:"₺30 718 771 085",percentage:"-0.09%",password:"Mkt Cap: ₺577 082 095 911"},
    {title:"XRP",category:"XRP",number:"₺11.47",code:"₺34 986 281 847",percentage:"-1.36%",password:"Mkt Cap: ₺541 781 046 848"},
    {title:"Polkadot",category:"DOT",number:"₺394.99",code:"₺9 869 524 676",percentage:"3.94%",password:"Mkt Cap: ₺420 564 938 665"},
    {title:"Terra",category:"LUNA",number:"₺847.02",code:"₺21 834 424 590",percentage:"-3.65%",password:"Mkt Cap: ₺320 589 772 630"},
    {title:"Dogecoin",category:"DOGE",number:"₺2.33",code:"₺7 816 150 225",percentage:"-0.26%",password:"Mkt Cap: ₺308 846 162 821"},
    {title:"Avalanche",category:"AVAX",number:"₺1183.69",code:"₺7 866 414 099",percentage:"2.97%",password:"Mkt Cap: ₺287 714 346 697"},
    {title:"Shiba Inu",category:"SHIB",number:"₺0.00047721",code:"₺10 158 485 008",percentage:"0.60%",password:"Mkt Cap: ₺262 060 000 971"},
    {title:"Crypto.com Coin",category:"CRO",number:"₺8.23",code:"₺3 020 782 359",percentage:"4.74%",password:"Mkt Cap: ₺207 837 281 621"},
    {title:"Polygon",category:"MATIC",number:"₺28.64",code:"₺16 777 762 098",percentage:"-1.11%",password:"Mkt Cap: ₺196 832 377 510"},
    {title:"Binance USD",category:"BUSD",number:"₺13.9",code:"₺39 503 637 103",percentage:"0.13%",password:"Mkt Cap: ₺192 986 044 334"},
    {title:"Wrapped Bitcoin",category:"WBTC",number:"₺688913",code:"₺4 541 209 651",percentage:"2.48%",password:"Mkt Cap: ₺176 826 771 406"},
    {title:"Litecoin",category:"LTC",number:"₺2184.55",code:"₺10 942 930 402",percentage:"0.73%",password:"Mkt Cap: ₺151 194 748 521"},
    {title:"Algorand",category:"ALGO",number:"₺21.33",code:"₺2 306 172 441",percentage:"2.77%",password:"Mkt Cap: ₺134 664 747 933"},
    {title:"TRON",category:"TRX",number:"₺1.27",code:"₺11 172 760 082",percentage:"0.75%",password:"Mkt Cap: ₺129 466 609 849"},
    {title:"Chainlink",category:"LINK",number:"₺272.51",code:"₺8 154 695 537",percentage:"0.69%",password:"Mkt Cap: ₺127 262 829 160"},
    {title:"Dai",category:"DAI",number:"₺13.88",code:"₺5 596 404 377",percentage:"-0.30%",password:"Mkt Cap: ₺123 599 256 380"},
    {title:"TerraUSD",category:"UST",number:"₺13.91",code:"₺1 572 342 422",percentage:"0.49%",password:"Mkt Cap: ₺120 385 997 483"},
    {title:"Bitcoin Cash",category:"BCH",number:"₺6273.55",code:"₺25 878 303 318",percentage:"-0.22%",password:"Mkt Cap: ₺118 729 656 243"},
    {title:"Uniswap",category:"UNI",number:"₺217.83",code:"₺1 849 325 532",percentage:"-2.14%",password:"Mkt Cap: ₺98 672 000 047"},
    {title:"OKB",category:"OKB",number:"₺373.82",code:"₺9 000 544 072",percentage:"11.98%",password:"Mkt Cap: ₺98 175 484 009"},
    {title:"Axie Infinity",category:"AXS",number:"₺1421.58",code:"₺2 109 969 410",percentage:"0.49%",password:"Mkt Cap: ₺96 502 370 469"},
    {title:"Cosmos",category:"ATOM",number:"₺337.65",code:"₺5 694 271 627",percentage:"4.09%",password:"Mkt Cap: ₺95 970 515 447"},
    {title:"Stellar",category:"XLM",number:"₺3.81",code:"₺4 110 857 049",percentage:"-0.43%",password:"Mkt Cap: ₺93 836 279 596"},
    {title:"Lido Staked Ether",category:"STETH",number:"₺55653",code:"₺192 338 362",percentage:"0.24%",password:"Mkt Cap: ₺87 218 107 085"},
    {title:"Near",category:"NEAR",number:"₺149.82",code:"₺7 324 311 749",percentage:"1.08%",password:"Mkt Cap: ₺86 103 371 377"},
  
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
color:white
}

h1{
  font-weight:bold;
  margin-bottom: 20px;
  font-size: 23px;
  color: white;
  padding: 30px;
}
.tableau{
  max-height: 400px;
  overflow-y: scroll
  ;display: grid; 
  margin-top: 30px;
  margin-bottom: 40px;
  justify-content: space-around;
}
.liste{
      background-color: black;
}
td, a{
  color: white;
  padding: 10px;
  font-weight: 600;
  text-align: justify;
  border-bottom: 1px solid white;
}


input[type="text" i] {
    border-color: white;
    background-color: black;
    border-radius: 5px;
    padding: 6px;
    color: white;
}
</style>