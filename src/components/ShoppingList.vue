<template>
    <div class="listWrapper">
        <ul class="listItem">
            <li v-for ="(dog, index) in dogs" :key= "dog.id"> 
                <div>
                    {{dog.name}}
                </div>
                <div class="removeItem" @click ="removeListItem(index)">
                    X
                </div>
            </li>
        </ul>
        <div>
        <input type = "text" placeholder = "Buy what?" v-model = "newDog" v-on:keyup.enter="addDoggo">
        <button>Köp This!</button>
        </div>
    </div>
</template>

<script>
export default{
    name:'ShoppingList',
    data(){   
        return {
            newDog: '',

            idForDoggo: 4,
                dogs: [
                {'name': 'Ninja',
                 'id': 1,},
                {'name':'Casper',
                'id': 2},
                {'name': 'Ozzy',
                'id': 3},
                ]       
        }

    },

    methods:{
        addDoggo(){
            if(this.newDog.trim().length == 0){
                return
            }
            this.dogs.push({
                name: this.newDog, 
                id: this.idForDoggo
                })
            this.newDog = ''
            this.idForDoggo ++
        },

        removeListItem(index){
            this.dogs.splice(index, 1)
        }
    }
}


</script>

<style>

.listWrapper{
    display:flex;
    flex-direction: column;
    align-items: center;
}

ul{
    width: 15%;
    padding:0;
    margin: 3rem;
}

li{
    display:flex;
    justify-content: space-between;
    margin-top: 0.5rem;

}

.removeItem{
    font-weight:bold;
}
</style>
