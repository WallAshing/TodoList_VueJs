
<style>
      body{
        display: flex;
        justify-content: center;
        align-items: center;
      }

      div{
        display: block;
      }

      #TodoCard{
        position: relative;
        height: 350px;
        width: 610px;
        background-color: white;
        border-radius: 5px;
      }
      header{
        position: relative;
        height: 35px;
        display: flex;
        align-items: center;
        justify-content: center;
        box-shadow: 0 5px 5px -2px rgba(128, 128, 128, 0.24);
        border-radius: 5px;
      }
      h2{
        color: #0CD3B5;
      }
      .date{
        position: absolute;
        left: 0px;
        margin: 0px 10px;
      }
      .date::first-letter{
        text-transform: uppercase;
      }
      .task{
        position: absolute;
        right: 0px;
        margin: 0px 10px;
      }
      #NewTodo{
        position:relative; 
        display: flex;
        justify-content: center;
        align-items: center;
      }

      button:focus {outline:0;}

      .addingButton{
        position: absolute;
        right: 120px;
        top: 37px;
        height: 30px;
        width: 30px;
        border-radius: 100%;
        border: none;
        background-color: #48C774;
        transition: 1s;
      }

      .addingButton:hover{
        cursor: pointer;
        background-color: rgb(57, 163, 98);
      }

      .addingButton p{
        position: absolute;
        top: -5px;
        left: 6px;
        font-size: 25px;
        color: white;
      }

      #TodoList{
        position: absolute;
        height: 200px;
        width: 570px;
        top: 130px;
        left: 20px;
      }

      li{
        position: relative;
        display: flex;
        align-items: center;
        width: 100%;
        height: 25px;
        margin: 10px 0;
      }

      .todoLabel{
        margin-left: 10px;
        margin-bottom: 3px;
        display: flex;
        justify-content: center;
        align-items: center;
        width: fit-content;
        
      }

      .deletingButton{
        position: absolute;
        right: 0px;
        top: -2.5px;
        height: 30px;
        width: 30px;
        border-radius: 100%;
        border: none;
        background-color: red;
        transition: 1s;
      }

      .deletingButton:hover{
        cursor: pointer;
        background-color: rgb(185, 0, 0);
      }

      .deletingButton img{
        width: 60%;
      }

      .deleted{
        display:none;
      }

      .striped{
        text-decoration:line-through;
      }

      .container ul{
        position: absolute;
        width: 550px;
        left: 28px;
        top: 90px;
      }

/* --------------------------------------------------------- */

      .group 			  { 
        position:absolute;
        top: 25px;
        margin-bottom:45px; 
      }
      .taskInput 				{
        font-size:18px;
        padding:10px 10px 10px 5px;
        display:block;
        width:300px;
        border:none;
        border-bottom:1px solid #757575;
      }
      .taskInput:focus{ outline:none; }

      .taskLabel 				 {
        color:#999; 
        font-size:18px;
        font-weight:normal;
        position:absolute;
        pointer-events:none;
        left:5px;
        top:10px;
        transition:0.2s ease all; 
        -moz-transition:0.2s ease all; 
        -webkit-transition:0.2s ease all;
      }

      .taskInput:focus ~ .taskLabel, .taskInput:valid ~ .taskLabel 		{
        top:-20px;
        font-size:14px;
        color:#48C774;
      }

      .bar 	{ position:relative; display:block; width:300px; }
      .bar:before, .bar:after 	{
        content:'';
        height:2px; 
        width:0;
        bottom:1px; 
        position:absolute;
        background:#48C774; 
        transition:0.2s ease all; 
        -moz-transition:0.2s ease all; 
        -webkit-transition:0.2s ease all;
      }
      .bar:before {
        left:50%;
      }
      .bar:after {
        right:50%; 
      }

      .taskInput:focus ~ .bar:before, .taskInput:focus ~ .bar:after {
        width:50%;
      }

      .highlight {
        position:absolute;
        height:60%; 
        width:100px; 
        top:25%; 
        left:0;
        pointer-events:none;
        opacity:0.5;
      }

      .taskInput:focus ~ .highlight {
        -webkit-animation:inputHighlighter 0.3s ease;
        -moz-animation:inputHighlighter 0.3s ease;
        animation:inputHighlighter 0.3s ease;
      }

      @-webkit-keyframes inputHighlighter {
        from { background:#48C774; }
        to 	{ width:0; background:transparent; }
      }
      @-moz-keyframes inputHighlighter {
        from { background:#48C774; }
        to 	{ width:0; background:transparent; }
      }
      @keyframes inputHighlighter {
        from { background:#48C774; }
        to 	{ width:0; background:transparent; }
      }

    </style>

<template>
    <TodoCard/>



</template>

<script>
import TodoCard from './components/TodoCard.vue'
export default {
  name: 'app',
  data () {
    return {
      msg: 'Hello, et bienvenue sur la demo TodoList en Vue.js!'
    } 
  },
  components:{
    TodoCard,
  }
}
</script>