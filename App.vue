<template>
  <!-- <div class="container"> -->
    <h1 class="text-center">Les Amis</h1>
    <ul class="list-group">
      <un-ami v-for="(unAmi) in lesAmis" 
      :key="unAmi.id" 
      :leNom="unAmi.name" 
      :lePhone="unAmi.phone" 
      :leMail="unAmi.email" 
      :premium="unAmi.premium"
      :id="unAmi.id"
      @mon-event-premium = "afficherStatusPremium"
      ></un-ami>
      <!--<un-ami leNom="Steven Seagal" lePhone="1234567" leMail="steven@seagal.com" premium="1"></un-ami>
      <un-ami leNom="Gérard Menvuça" lePhone="0987654" leMail="gérard@menvuça.com" premium="0"></un-ami>   
      <un-ami leNom="Jacques Arton" lePhone="023456578" leMail="carton@lolilol.com" premium="1"></un-ami>-->
    </ul>
  <!-- </div> -->
</template>

<script>
export default{
  data(){
    return {
      lesAmis: [
        {
            id: 'lasticot',
            name: 'COCO L ASTICOT',
            phone: '01234 5678 991',
            email: 'coco@lasticot.com',
            premium: true,
        },
        {
            id: 'janine',
            name: 'Janine DeLavega',
            phone: '09876 543 221',
            email: 'janine@delavega.com',
            premium: false,
        },
        {
            id: 'stan',
            name: 'Stanislas Lefort',
            phone: '07896 345 210',
            email: 'stanislas@lefort.com',
            premium: true,
        },
    ],
    }
  },
  methods: {
    afficherStatusPremium(leIdDansUnAmi) {
      const unAmiIdentified= this.lesAmis.find(unAmi => unAmi.id === leIdDansUnAmi) ;
      console.log(unAmiIdentified) ;
      unAmiIdentified.premium = !unAmiIdentified.premium ;
    },
  },
}
</script>