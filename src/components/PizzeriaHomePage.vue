<template>
  <div>
    <div id="header">
      <video loop autoplay >
        <source src="../assets/pizzaneon.mp4" type="video/mp4"> 
      </video>
    </div>
    <img class="banner" src="banner.jpg" alt="Banner Pizzeria">
    <h1>Titolo</h1>
    <h2>Sottotitolo</h2>

    <div class="pizza-container">
      <div class="pizza-card" v-for="pizza in pizze" :key="pizza.name">
        <img :src="pizza.image" :alt="pizza.name">
        <div class="pizza-info">
          <div>
            <h3>{{ pizza.name }}</h3>
            <p>{{ pizza.description }}</p>
            <p>{{ pizza.price }}€</p>
          </div>
          <select v-model="pizza.quantity" class="quantity-select">
            <option disabled value="">Seleziona la quantità</option>
            <option v-for="number in 10" :key="number">{{ number }}</option>
          </select>
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
        }
      ]
    }
  },
  methods: {
    submitOrder() {
    }
  }
}

</script>