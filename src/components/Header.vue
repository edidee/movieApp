<template>
    <div>
        <div class="header">
            <p>Dream Movies</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Header'
}
</script>

<style scoped>
    .header{
        width: 100%;
        height: 50px;
        background: #93020B;
    
    }

    p{
        color: #fff;
        padding-top: 4%;
        padding-left: 3%;
        
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