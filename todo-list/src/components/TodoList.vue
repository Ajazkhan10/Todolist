<template>
    <div>
        <h1>To Do List</h1>
        <p>Create a list of tables:</p>
        <div class="search">
            <input type="text">
            <button>ADD</button>
        </div>
          <div class="main" v-for="display in displays" :key="display[0]">
             <div class="display"> {{display[0]}}</div>
             <button>DONE</button>
             <button>DELETE</button>
          </div>
    </div>
</template>

<script>
export default {
    name:'TodoList',
    displays:['vue js example.com','vus js tut 2','vue js tut 3']
}
</script>
<style>
body{
    margin: 0;
    padding: 0;
    background: rgb(93, 133, 102);
    text-align: center;
    justify-content: center;
}
h1 ,p{
    font-size: 50px ;
    font-weight: 800;
    text-align: center;
    justify-content: center;
    color: white;
}
.search input{
    background: rgb(224, 224, 224);
    width: 400px;
    border: 1px solid rgb(141, 141, 141);
    margin: 20px 5px 20px 5px ;
    height: 40px;
    border-radius: 20px 10px 20px 10px;
    font-size: 25px;
    padding-left: 20px;
    font-weight: 500;
}
.search button{
    border-radius: 10px 20px 10px 20px;
    font-weight: 800;
    font-size: 25px;
    width: 90px;
    background: orange;
    height: 48px;
    cursor: pointer;
}
.search button:hover{
       color: lightgray;
}
.main{
    width: 500px;
    height: 50px;
    display: flex;
    flex-direction:row;
    margin: auto;
    text-align: center;
    justify-content: center;
}
.display{
    width: 400px;
    background: white;
    height: 40px;
    border-radius: 20px 10px 20px 10px;
    margin: auto;
    padding: 5px 0 0 0;
}
.main button{
     border-radius: 10px 20px 10px 20px;
    font-weight: 800;
    font-size: 20px;
    width: 100px;
    background: orange;
    height: 48px;
    margin-left: 5px;
    cursor: pointer;
}
.main button:hover{
       color: lightgray;

}
</style>