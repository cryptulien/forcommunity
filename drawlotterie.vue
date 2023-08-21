<template>
    <v-row class="justify-center">
      <v-sheet border class="pa-2" rounded="lg" style="width: 700px; height: 500px;">
        <v-col>
          <div class="rounded-lg ma-2 pa-2 custom-div">
            <div class="ma-2 pa-2 custom-font">
              CYBERHUAHUA PREMIUM LOTTERY
            </div>
            <v-row
              align="start"
              class="pa-4 justify-center align-center"
            >
              <v-col 
                cols="12"
                sm="8"
              >
                <div> Winner is: <span :class="{'winner-text': winnerPremium !== ''}">{{ winnerPremium }}</span></div>
                <div> This Cyberhuahua had this probability: <span :class="{'winner-text': probabilityPremium !== ''}">{{ probabilityPremium }}</span></div>
                <br>
                <v-btn @click="pickPremiumWinner"> Draw </v-btn>
              </v-col>
              <v-col
                cols="12"
                sm="4"
              >
                <v-img
                  v-bind:src="nftImgPremium"
                  max-width="200"
                  class="rounded-lg"
                >
    
                </v-img>
                <br>
                <v-btn 
                  v-bind:href="nftUrlPremium"
                  target="_blank"
                > 
                  See NFT 
                </v-btn>
              </v-col>
            </v-row>
          </div>
        </v-col>
      </v-sheet>
      <v-sheet border class="pa-2" rounded="lg" style="width: 700px; height: 500px;">
        <v-col>
          <div class="rounded-lg ma-2 pa-2 custom-div">
            <div class="ma-2 pa-2 custom-font">
              CYBERHUAHUA ZOMBIES LOTTERY
            </div>
            <v-row
              align="start"
              class="pa-4 justify-center align-center"
            >
              <v-col 
                cols="12"
                sm="8"
              >
                <div> Winner is: <span :class="{'winner-text': winnerZombies !== ''}">{{ winnerZombies }}</span></div>
                <div> This Cyberhuahua had this probability: <span :class="{'winner-text': probabilityZombies !== ''}">{{ probabilityZombies }}</span></div>
                <br>
                <v-btn @click="pickZombiesWinner"> Draw </v-btn>
              </v-col>
              <v-col
                cols="12"
                sm="4"
              >
                <v-img
                  v-bind:src="nftImgZombies"
                  max-width="200"
                  class="rounded-lg"
                >
    
                </v-img>
                <br>
                <v-btn 
                  v-bind:href="nftUrlZombies"
                  target="_blank"
                > 
                  See NFT 
                </v-btn>
              </v-col>
            </v-row>
          </div>
        </v-col>
      </v-sheet>
    </v-row>
    <v-row class="justify-center">
      <v-sheet border class="pa-2" rounded="lg" style="width: 700px; height: 500px;">
        <v-col>
          <div class="rounded-lg ma-2 pa-2 custom-div">
            <div class="ma-2 pa-2 custom-font">
              CHADPUNKS RAFFLE
            </div>
            <v-row
              align="start"
              class="pa-4 justify-center align-center"
            >
              <v-col 
                cols="12"
                sm="8"
              >
                <div> Winner is: <span :class="{'winner-text': winnerChadPunk !== ''}">{{ winnerChadPunk }}</span></div>
                <div> This ChadPunk had this probability: <span :class="{'winner-text': probabilityChadPunk !== ''}">{{ probabilityChadPunk }}</span></div>
                <br>
                <v-btn @click="pickChadPunkWinner"> Raffle </v-btn>
              </v-col>
              <v-col
                cols="12"
                sm="4"
              >
                <v-img
                  v-bind:src="nftImgChadPunk"
                  max-width="200"
                  class="rounded-lg"
                >
    
                </v-img>
                <br>
                <v-btn 
                  v-bind:href="nftUrlChadPunk"
                  target="_blank"
                > 
                  See NFT 
                </v-btn>
              </v-col>
            </v-row>
          </div>
        </v-col>
      </v-sheet>
      <v-sheet border class="pa-2" rounded="lg" v-if="toripunksactivate" style="width: 700px; height: 500px;">
        <v-col>
          <div class="rounded-lg ma-2 pa-2 custom-div">
            <div class="ma-2 pa-2 custom-font">
              TORIPUNKS RAFFLE
            </div>
            <v-row
              align="start"
              class="pa-4 justify-center align-center"
            >
              <v-col 
                cols="12"
                sm="8"
              >
                <div> Winner is: <span :class="{'winner-text': winnerToriPunk !== ''}">{{ winnerToriPunk }}</span></div>
                <div> This ToriPunk had this probability: <span :class="{'winner-text': probabilityToriPunk !== ''}">{{ probabilityToriPunk }}</span></div>
                <br>
                <v-btn @click="pickToriPunkWinner"> Raffle </v-btn>
              </v-col>
              <v-col
                cols="12"
                sm="4"
              >
                <v-img
                  v-bind:src="nftImgPremium"
                  max-width="200"
                  class="rounded-lg"
                >
    
                </v-img>
                <br>
                <v-btn 
                  v-bind:href="nftUrlPremium"
                  target="_blank"
                > 
                  See NFT 
                </v-btn>
              </v-col>
            </v-row>
          </div>
        </v-col>
      </v-sheet>
    </v-row>
    
</template>
    
    <script>
    
    import jsonDataChadPunks from '@/configs/raritychadpunks.json'
    import jsonDataToriPunks from '@/configs/raritytoripunks.json'
    import jsonPremiumLottery from '@/configs/raritypremiumlottery.json'
    
    export default {
      data() {
        return {
          winnerChadPunk: '',
          probabilityChadPunk: '',
          nftUrlChadPunk: '',
          nftImgChadPunk:'',
    
          winnerToriPunk: '',
          probabilityToriPunk: '',
          nftUrlToriPunk: '',
          nftImgToriPunk:'',
    
          winnerPremium: '',
          probabilityPremium: '',
          nftUrlPremium: '',
          nftImgPremium: '',
    
          winnerZombies: '',
          probabilityZombies: '',
          nftUrlZombies: '',
          nftImgZombies: '',
    
          toripunksactivate: false,
        }
      },
      methods: {

        // Function to format numbers appropriately

        formatNumberWithSpaces(number) {
            return number.toLocaleString("en-IN");
        },

        // Winner draw function
    
        pickChadPunkWinner() {
            // Get the IDs of the ChadPunks as keys
            const keys = Object.keys(jsonDataChadPunks);
            
            // Calculate the total probability of winning
            const totalChances = keys.reduce((total, key) => total + (1001 - parseInt(key)) / 500500, 0);
            
            // Generate a random value within the total probability range
            const randomValue = Math.random() * totalChances;
            let cumulativeProbability = 0;
            
            // Iterate through ChadPunks and select a winner based on probability
            for (const key of keys) {
                cumulativeProbability += (1001 - parseInt(key)) / 500500;
                
                // If the random value falls within the current cumulative probability, select the winner
                if (randomValue <= cumulativeProbability) {
                // Set winner properties and break the loop
                this.winnerChadPunk = `CHADPUNK #${key}`;
                const probability = (((1001 - parseInt(key)) / 500500) / totalChances) * 100;
                this.probabilityChadPunk = `${probability.toFixed(2)}%`;
                this.nftUrlChadPunk = `https://app.teritori.com/nft/tori-tori1a8h38nsxu254trpfm0z65mrvguhp544mf9e36670ltm4s89y5wjq7mqevy-${key}`;
                this.nftImgChadPunk = `https://bafybeia5gf3bwhtyioaxmt35xu3jjqdeqy6y3lenbnv5jywstwghsln22a.ipfs.nftstorage.link/${key}.png`;
                break;
                }
            }
        },

        pickToriPunkWinner() {
            // Calculate the total chances of winning
            const totalChances = (10001 * 10000) / 2;
            console.log(totalChances);
            
            // Generate a random value within the total chances range
            const randomValue = Math.floor(Math.random() * totalChances) + 1;
            console.log(randomValue);
            
            // Calculate the winning number using a formula
            const winningNumber = Math.floor(10001 - Math.sqrt(10001 * 10001 - 2 * randomValue));
            console.log(winningNumber);
            
            // Set winner properties and calculate winning probability
            this.winnerToriPunk = `TORIPUNK #${winningNumber}`;
            console.log(this.winnerToriPunk);
            const probability = this.formatNumberWithSpaces(((10001 - winningNumber) / totalChances) * 100);
            console.log(probability);
            this.probabilityToriPunk = `${probability}%`;
            console.log(this.probabilityToriPunk);
            
            // Set URLs for the winning ToriPunk
            this.nftUrlToriPunk = `https://app.teritori.com/nft/tori-tori1a8h38nsxu254trpfm0z65mrvguhp544mf9e36670ltm4s89y5wjq7mqevy-${winningNumber}`;
            console.log(this.nftUrlToriPunk);
        },

        pickPremiumWinner() {
            // Get the IDs of participants in the premium lottery
            const keys = Object.keys(jsonPremiumLottery);
            
            // Calculate the total number of participants
            const totalChances = keys.length;
            
            // Randomly select a participant
            const randomIndex = Math.floor(Math.random() * totalChances);
            const selectedKey = keys[randomIndex];
            
            // Get the winning number associated with the selected participant
            const winningNumber = jsonPremiumLottery[selectedKey];
            
            // Calculate and set the winning probability
            const probability = this.formatNumberWithSpaces((1 / 69) * 100);
            this.probabilityPremium = `${probability}%`;
            
            // Set the winner and URLs based on the type of winner
            this.winnerPremium = selectedKey;
            if (selectedKey.includes("PREMIUM")) {
                this.nftUrlPremium = `https://www.stargaze.zone/m/stars1s7uu0v6k83vw9fpfwnc0ugnplhg9uvxn3hvqg8wd678gf7dr38wsglczwg/${winningNumber}`;
                this.nftImgPremium = `https://ipfs-gw.stargaze-apis.com/ipfs/bafybeihlh4pvvbkcwr35f2brcwogl5zpnvxqlzfd63dmstp6ykcv5thppi/${winningNumber}.png`;
            } else if (selectedKey.includes("EXTREMELY RARE ZOMBIES")) {
                this.nftUrlPremium = `https://www.stargaze.zone/m/stars198yy57r6sym5tngc2xd9k2pctg9v89q36785zc2cqljukqdglalqzdf2k4/${winningNumber}`;
                this.nftImgPremium = `https://ipfs-gw.stargaze-apis.com/ipfs/bafybeidxvrxq55f3twrydukprghbpasgfkhjf4oj3fry3qwuad7wcohu4e/${winningNumber}.png`;
            }
        },

        pickZombiesWinner() {
            // Set the total chances of winning
            const totalChances = 200;
            
            // Generate a random value within the total chances range
            const randomValue = Math.floor(Math.random() * totalChances) + 1;
            const winningNumber = randomValue;
            
            // Set winner and probability properties
            this.winnerZombies = `CYBERHUAHUA ZOMBIES #${winningNumber}`;
            const probability = this.formatNumberWithSpaces((1 / 200) * 100);
            this.probabilityZombies = `${probability}%`;
            
            // Set URLs for the winning CyberHuahua Zombie
            this.nftUrlZombies = `https://www.stargaze.zone/m/stars198yy57r6sym5tngc2xd9k2pctg9v89q36785zc2cqljukqdglalqzdf2k4/${winningNumber}`;
            this.nftImgZombies = `https://ipfs-gw.stargaze-apis.com/ipfs/bafybeidxvrxq55f3twrydukprghbpasgfkhjf4oj3fry3qwuad7wcohu4e/${winningNumber}.png`;
        }

    },
    
    }
    
    
    
    </script>
    
    <style>
    .custom-div {
      background-color: rgb(28, 28, 28);
    }
    .custom-font {
      font-weight: bold;
    }
    .winner-text {
      font-weight: bold;
      color:#D18920;
    }
    </style>
    