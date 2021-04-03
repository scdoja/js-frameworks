<template>
  <div id="app">
	  <div class="info">
		  <img src="./assets/arc.gif" width="265" height="150">
		  <p>Welcome Tony Stark, please see available Mark Armours below.</p>
		  <input type="text" placeholder="Input Specific Feature..." v-model="search">
	  </div>

	  <div class="suits" v-for="suit in filteredSuits" :key="suit.id">
		  <suit :suit="suit"></suit>
	  </div>

  </div>
</template>

<script>
import Suit from './components/Suit';
export default {
	name: 'App',
	components: { Suit },
	data(){
		return{
			search: "",
			suits: [
			  	{
				  	id: 1,
				  	title: 'The Mark IV (Mark 4)',
				  	body: 'Strength, Bullet-Proof, Repulsors, Flight Activation.',
				  	link: 'https://ironman.fandom.com/wiki/Iron_Man_Mark_IV',
				  	image: 'man4.png'
			  	},
			  	{
				  	id: 2,
				  	title: 'The Mark XVII (Mark 17)',
				  	body: 'Heavy Firepower, JARVIS OS, Super Durability.',
				  	link: 'https://ironman.fandom.com/wiki/Mark_XVII_-_Heartbreaker',
				  	image: 'man17.png'
			  	},
			  	{
				 	id: 3,
 				 	title: 'The Mark XLIII (Mark 43)',
 				 	body: 'Remote Command, Life Support Systems, Tactical Weapons',
 				 	link: 'https://ironman.fandom.com/wiki/Mark_43',
 				 	image: 'man43.png'
			  	},
			  	{
				 	id: 4,
				 	title: 'The Mark XLVII (Mark 47)',
				 	body: 'Sonic Pulse, Grapple Chains, Sentry Mode, Retractable.',
				 	link: 'https://ironman.fandom.com/wiki/Mark_47',
				 	image: 'man47.png'
			  	},
			  	{
					id: 5,
					title: 'The Mark L (Mark 50)',
					body: 'Thanos Combat Tested, Bleeding Edge, Nano Technology.',
					link: 'https://ironman.fandom.com/wiki/Mark_50',
					image: 'man50.png'
			  	}
		  	]
		};
	},

  computed: {
	  filteredSuits(){
		  return this.suits.filter(suit => suit.body.toLowerCase().includes(this.search.toLowerCase()))
	  }
  }
};

</script>

<style>
	@import './assets/css/main.css';
</style>
