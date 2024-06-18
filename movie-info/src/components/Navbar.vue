<template>
    <nav class ="Navbar">
        <a href="#">Home</a>
        <a href="#">Movies</a>
        <a href="#">About</a>
    </nav>

</template>
<script>
    export default{
        name : 'NavbarComponent', // 이건 뭐지 
    }
</script>
<style>
    .Navbar{
        background: #000;
        padding: 20px;
        text-align: center;
    }

    .Navbar a {
        color: #fff;
        text-decoration: none;
        padding: 1em;
    }
</style>