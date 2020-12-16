<template>
    <div>
        <div class="footer">
            <p>Copyright 2020 Edidee</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Footer'
}
</script>

<style scoped>
    .footer{
        width: 100%;
        height: 50px;
        background: #93020B;
    }

    p{
        color: #fff;
        text-align: center;
        padding-top: 4%;
    }

    @media screen and (min-width: 768px ) and ( max-width: 1279px){
        p{   
        padding-top: 2%;
    }

    }

    @media screen and (min-width: 1280px) {
        p{
        
        padding-top: 1%;
        
        
    }
        
    }
</style>