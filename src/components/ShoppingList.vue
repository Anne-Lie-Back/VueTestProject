<template>
    <div>
        <ul>
            <li v-for ="dog in dogs" :key= "dog.id"> {{dog.name}}</li>
        </ul>
        <div>
        <input type = "text" placeholder = "Buy what?" v-model = "newDog">
        <button>Köp This!</button>
        </div>
    </div>
</template>

<script>
export default{
    name:'ShoppingList',
    data(){
        
        return {
            newDogs: '',
                dogs: [
                {'name': 'Ninja',
                 'id': 1},
                {'name':'Casper',
                'id': 2},
                {'name': 'Ozzy',
                'id': 3}
                ],       
        }
    },
}


</script>


