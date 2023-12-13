<template>
    <div class="container my-1">
        <ul class="list-group">
            <h2 class="list-group-item">{{leNom}}{{premium == true ? ' (Ami Premium)' : ' (Ami Nul)'}}</h2> 
            <!--<h3>{{premiumData == '1' ? ' - Ami Premium' : ' - Ami Nul'}}</h3>-->
            <button @click="afficherPremium" class="btn btn-danger">Premium ?</button>
            <button @click="afficherDetails" class="btn btn-primary">Voir Détails</button>           
            <ul v-if="detailsVisibles" class="list-group">
                <li class="list-group-item">{{lePhone}}</li>
                <li class="list-group-item">{{leMail}}</li>
            </ul>
        </ul>
    </div>

</template>

<script>

export default {
    //props: ["leNom", "lePhone", "leMail", "premium"],
    props : {
        leNom : {
            type:String,
            required: true
        },
        id : {
            type:String,
            required: true
        },
        lePhone : {
            type:String,
            required: true
        },
        leMail : {
            type:String,
            required: true
        },
        premium : {
            type:Boolean,
            default: false,
            //validator: function (value) {
            //    return value === '1' || value === '0';
            //}
            required: false
        }
    },
    data(){
        return{
            
            premiumData: this.premium,
            detailsVisibles:false,
/*
            prop1:{
                leNom: 'Steven Seagal',
                lePhone: '1234567',
                leMail: 'steven@seagal.com',
            },
            prop2:{
                leNom: 'Gérard Mavuça',
                lePhone: '0987654',
                leMail: 'gérard@mavuça.com',
            },

            unPote:{
                id:'jojo',
                name:"Steven Seagal",
                phone:'123 12346 24',
                email:'steven@seegar.com',
            },

            unPote2: {
                id:'jojo',
                name:"Gérard Menvuça",
                phone:'123 45678 99',
                email:'gege@menvu.com',
            },
            */
        }
    },
    methods:{
        afficherDetails(){
            this.detailsVisibles = !this.detailsVisibles;
        } ,
        afficherPremium() {
            this.$emit(`mon-event-premium`, this.id) ;
            //this.premiumData = !this.premiumData ;
            /*if (this.premiumData === '1') {
                this.premiumData = '0' ;
            } else {
                this.premiumData = '1' ;
            }*/
        }
    },
}
</script>