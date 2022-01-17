<template>
    <footer class="footer">
        <div class="footer-wrap">
            <p>Všetký práva vyhradené © 2022  |  Blockchain Sloavakia O.z.</p>
            <a href="http://" target="_blank" rel="noopener noreferrer">blockchainslovakia.sk</a>
        </div>
    </footer>
</template>

<script>
    export default {
        
    }
</script>

<style lang="css" scoped>
.footer{
    /* width: 1600px; */
    width: 100%;
    height: 50px;
    margin: 0 auto;
    background: #F6F6FC;
    color: #7E7E9C;

    display: flex;
    justify-content: center;
    align-items: center;
}
.footer-wrap{
    width:1170px;
    padding: 16px;

    display: flex;
    justify-content: space-between;
    align-items: center;
}
.footer a{
    color: #7E7E9C;
}
@media only screen and (max-width: 660px){
    .footer{
        height: 92px;

    }
    .footer-wrap{
        align-items: flex-start;
        flex-direction: column;
        font-size: 12px;
        line-height: 18px;
    }
}
</style>