<template>
    <div>
        <button :class="{'button-white': color === 'white'}" class="button" :title="title">
            <slot />
        </button>
    </div>
</template>

<script>
export default {
  name: 'Button',
  props: {
    color: {
        type: String
    },
    title: {
        type: String
    }
  }
}
</script>

<style lang="scss">
.button {
    font-size: 13px;
    font-weight: 700;
    width: 100px;
    border: 2px solid rgb(35, 35, 35);
    background: transparent;
    line-height: 26px;
    color: rgb(35, 35, 35);
    margin: 9px 0;
    cursor: pointer;
    text-transform: uppercase;
    opacity: 1;
    transition: opacity .8s ease; 
    letter-spacing: 2px;
    &:hover {
        opacity: .5;
    }  
}


.button-white {
    background: rgb(255, 255, 255);
    color: #000;
    min-width: 160px;
    font-size: 16px;
    transition: all .8s ease; 
    padding: 8px 10px;
    border: 2px solid #fff;
    letter-spacing: 2px;
    &:hover {
        background: #000;
        color: #fff;
        opacity: 1;
        border: 2px solid #000;
    }
}

 
</style>
