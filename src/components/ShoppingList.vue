<template>
    <div class="listWrapper">
        <ul>
            <h2>Buy This:</h2>
            <li v-for ="(item, index) in listItems" :key= "item.id"> 
                <div>
                    {{item.name}}
                </div>
                <div class="removeItem" v-on:click ="removeListItem(index)">
                    X
                </div>
            </li>
        </ul>
        <div class="inputContainer">
            <input type = "text" placeholder = "What u need?" :maxlength="max" v-model = "newItem" v-on:keyup.enter="addItem">
            <div class="textCounter" v-text="(max - newItem.length)"></div>
            <button v-on:click ="addItem">Add!</button>
        </div>
    </div>
</template>

<script>
    export default{
        
        data(){   
            return {
                max: 15,
                newItem: '',
                idForItem: 4,

                listItems: [
                {'name': 'Covfefe',
                    'id': 1,},
                {'name':'Toilet Paper',
                'id': 2},
                {'name': 'Apples',
                'id': 3},
                ]       
            }

        },

        methods:{
            addItem(){
                if(this.newItem.trim().length == 0){
                    return
                }
                this.listItems.push({
                    name: this.newItem, 
                    id: this.idForItem
                    })
                this.newItem = ''
                this.idForItem ++
            },

            removeListItem(index){
                this.listItems.splice(index, 1)
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

    h2{
        padding: 0 2rem 1rem 2rem;
        border-bottom: 1px solid lightgray;
        font-size:1rem;
    }

    ul{
        width: 15rem;
        padding: 1rem 0;
        margin: 2rem 3rem;
        background: white;
        border: 1px solid black;
        box-shadow: 0 0 5px black;
        max-height:50vh;
        overflow-y: auto;
    }

    ::-webkit-scrollbar {
        -webkit-appearance: none;
        width: 0.3rem;
    }

    ::-webkit-scrollbar { /*Keeps the scrollbar in the todolist visable*/
        -webkit-appearance: none;
        width: 0.3rem;
    }
    ::-webkit-scrollbar-thumb { /*Styles the todolist scrollbar*/
        border-radius: 4px;
        background-color: rgb(0,0,0);
        padding-right: 0.7rem;
    }

    li{
        display:flex;
        justify-content: space-between;
        margin-top: 1rem;
        border-bottom: 1px solid lightgray;
        padding: 0 2rem;
        font-family: 'Indie Flower', cursive;

    }

    .inputContainer{
        display:flex;
        border: 1px solid black;
    }

    input{
        width:9rem;
        padding: 0.5rem;
        border:0;
        outline:none;
    }

    .textCounter{
        background:white;
        padding: 0.5rem 0.7rem;
        border-right: 1px solid black;
        
    }

    button{
        padding:0.5rem;
        background: #E0C7E2;
        border:1px solid #8E7291;
    }

    .removeItem{
        font-weight:bold;
    }

    .removeItem:hover{
        cursor: pointer;
    }
</style>
