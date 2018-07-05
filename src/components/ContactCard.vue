<template>
    <li class="list-group-item">
        <div class="row ">
            <img :src="contact.avatar ? contact.avatar : 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQJN9q9GanaCSCQ2xZoKypjkJpLu0fUVZp32OTdU8QEkMvdHOwINQ'" alt="" width="50px" height="50">
        <div class="text-block text-left">
            <span><b>{{contact.first_name}} {{contact.last_name}}</b></span>
            <div class="sub-text">{{contact.email}}</div>
        </div>
        </div>
    </li>
</template>

<script>

    export default {
        name: "ContactCard",
        props: ['contact'],
    }
</script>


<style>
    img{
        margin: 10px;
        border-radius: 25px;
     }
     .text-block{
         margin: 10px;
     }
     .sub-text{
         color: hsl(0, 0%, 40%);
     }
</style>
