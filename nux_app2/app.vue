<template>
    <main>
      <h1>Zoznam ľudí</h1>
      <section class="list">
        <section v-for="person of persons" v-bind:key="person"
        v-bind:class="{'card-container':true,'card':true,'adult':person.birthday>=18 }"><!--v tomto prípade clase priradíme objekt, ktorého vlastnosti predstavujú jednotlivé triedy a ich hodnoti predstavujú bool vyjadrujúci, kedy sa má daná trieda pridať danému elemntu-->
		<!--alebo takto tu to poriešime ternárnym operátorom...
		<section v-for="person of persons" v-bind:key="person" 
		v-bind:class="person.birthday>=18 ? 'adult card-container card' : 'card-container card'">
		-->
          <article class="info">
            <div class="name">{{person.fname}} {{person.lname}}</div>
            <div class="birthday">{{person.birthday}} <span class="year-title">year</span></div>
          </article>
          <footer class="footer-card">
            <span class="btn edit">Edit</span>
            <span class="btn remove">Remove</span>
          </footer>
        </section>
      </section>
    </main>
</template>

<script setup>
let persons = [
		{
			fname: "Magdalena",
			lname: "Mikulova",
			birthday: 22,
			
		},
		{
			fname: "Mirka",
			lname: "Makovicova",
			birthday: 30
		},
		{
			fname: "Hugo",
			lname: "Hugovic",
			birthday: 15
		},
		{
			fname: "Miki",
			lname: "Hric",
			birthday: 19
		},
		{
			fname: "Andrea",
			lname: "Veresova",
			birthday: 40
		},
		{
			fname: "Nora",
			lname: "Mojsejova",
			birthday: 13
		},
	]
</script>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Oswald:wght@200;300;500;600;700&display=swap');
	body {
		font-size: 10px;	
		font-family: 'Oswald', sans-serif;
		padding: 1rem;
	}
	main {
		display: flex;
		flex-direction: column;
		gap: .75rem;
	}
	.list {
		display: flex;
		gap: 20px;
		flex-direction: row;
		flex-wrap: wrap;
		justify-content: stretch;
		font-size: 1.2rem;
	}
	.card-container {
		flex-grow: 1;
	}
	.card {
		background: rgba(255,255,255, 1);
		border: 1px solid #bbb;
		color: #444;
		box-shadow: 0 3px 5px rgba(0,0,0,.2);
		border-top-width: 5px;
		border-top-color: dodgerblue;
	}
	.card.adult {
		border-top-color: orange;
	}
	.card:hover {}
	.info {
		padding: 1rem;
		text-align: center;
		font-size: 1.3rem;
	}
	.name {}
	.birthday {
		font-weight: 300;
		font-size: 1rem;
	}
	.year-title {
		color: #bbbbbb;
	}
	.footer-card {
		display: flex;
	}
	.btn {
		padding: .75rem 2rem;
		color: white;
		width: 50px;
		flex-grow: 1;
		text-align: center;
		transition: .5s;
		font-size: 1rem;
	}
	.btn.edit {
		background: rgb(91, 236, 91);
	}
	.btn.remove {
		background: red;
	}
	.btn:hover {
		opacity: .3;
		cursor: pointer;;
	}
</style>

