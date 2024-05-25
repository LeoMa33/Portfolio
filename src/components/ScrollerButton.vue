<template>
    <div>
        <!--<img src="/arrow.png" alt="" srcset="">-->
        <ul id="downArrow">
            <li style="--i:1"></li>
            <li style="--i:2"></li>
            <li style="--i:3"></li>
        </ul>
    </div>
</template>

<script setup lang="ts">
</script>



<style scoped>
div {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 12.5dvh;
}

ul#downArrow {
    position: relative;
    width: 40px;
    display: flex;
    align-items: center;
    flex-flow: column;
    margin-bottom: 30px;
}

ul#downArrow li {
    list-style: none;
    width: 8px;
    height: 8px;
    background-color: #00B578;
    border-radius: 100%;
    margin-bottom: 10px;
    animation: ani 0.8s infinite ease-in-out;
    animation-delay: calc(0.2s * var(--i));
}

ul#downArrow::before,
ul#downArrow::after {
    position: absolute;
    content: '';
    background-color: #00B578;
    width: 30px;
    height: 5px;
    bottom: 0;
    border-radius: 4px;
}

ul#downArrow::before {
    right: 0;
    transform: rotate(-45deg);
    transform-origin: center right;
}

ul#downArrow::after {
    left: 0;
    transform: rotate(45deg);
    transform-origin: center left;
}

@keyframes ani {
    0% {
        opacity: 0;
        transform: scale(0.5) translateY(-5px);
    }

    50% {
        opacity: 1;
        transform: scale(1) translateY(20px);
    }

    100% {
        opacity: 0;
        transform: scale(0.5) translateY(30px);
    }
    
}
</style>