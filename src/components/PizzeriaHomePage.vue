<template>
  <div>
    <div id="header">
      <video loop autoplay muted>
        <source src="../assets/pizzaneon.mp4" type="video/mp4"> 
      </video>
    </div>
    <div id="content"> 
      <h1>JOE's PIZZA</h1>
      <h2>LA PIZZA PIU' BUONA DI NEW YORK</h2>
    
      <div class="pizza-container">
        <div class="pizza-card" v-for="(pizza, index) in pizze" :key="index">
          <img :src="pizza.image" alt="Pizza" class="pizza-img">
          <div class="pizza-info">
            <h3>{{ pizza.name }}</h3>
            <p>{{ pizza.description }}</p>
            <div class="price-quantity">
              <p>Prezzo: {{ pizza.price }}€</p>
              <select v-model="pizza.quantity">
                <option disabled value="">Seleziona la quantità</option>
                <option v-for="i in 10" :key="i">{{ i }}</option>
              </select>
            </div>
          </div>
        </div>
      </div>

      <form>
        <input type="text" name="nome" placeholder="Nome">
        <input type="text" name="cognome" placeholder="Cognome">
        <input type="email" name="email" placeholder="Email">
        <input type="tel" name="telefono" placeholder="Numero di Telefono">
        <input type="text" name="indirizzo" placeholder="Indirizzo">
        <textarea name="ordine" placeholder="Scrivi qui il tuo ordine"></textarea>
        <button type="submit">Ordina ora</button>
      </form>

      <div id="footer">
        <p>Joe's Pizza - consegna in 3 minuti</p>
        <p>Contatti: joespizza@bellanapoli.it - 3493333333</p>
      </div>
    </div>
  </div>
</template>

<script>
  import '../assets/styles/components/PizzeriaHomePage.scss';
  export default {
  data() {
    return {
      pizze: [
        {
          name: 'Margherita',
          description: 'Ingredienti: mozzarella, pomodoro, basilico',
          price: 10,
          image: require('../assets/pizzamarghe.png'),
          quantity: ''
        },
        {
          name: 'Capricciosa',
          description: 'Ingredienti: mozzarella, pomodoro, funghi, prosciutto cotto, carciofini',
          price: 12,
          image: require('../assets/pizzacapricc.png'),
          quantity: ''
        },
        {
          name: 'Marinara',
          description: 'Ingredienti: pomodoro, aglio, rosmarino',
          price: 7,
          image: require('../assets/marinara.png'),
          quantity: ''
        },
        {
          name: 'Vegana',
          description: 'Ingredienti: pomodoro, melanzane, peperoni, zucchine',
          price: 7,
          image: require('../assets/vegana.png'),
          quantity: ''
        },
        {
          name: '4 formaggi',
          description: 'Ingredienti: gorgonzola, taleggio, hemmental, mozzarella',
          price: 7,
          image: require('../assets/4formaggi.png'),
          quantity: ''
        },
        {
          name: 'Wurstel e Patate',
          description: 'Ingredienti: pomodoro, mozzarella, wurstel, patate fritte',
          price: 7,
          image: require('../assets/patate.png'),
          quantity: ''
        },
      
      ]
    }
  },
  methods: {
    submitOrder() {
    }
  }
}

</script>