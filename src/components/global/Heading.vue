<template>
    <div>
        <h1 v-if="level === 1" :class="{'grey-heading' : headingColor === 'grey', 'white-heading' : headingColor === 'white', 'heading-first-level' : heading === 'h1' }" > {{ title }} </h1>
        <h2 v-if="level === 2" :class="{'grey-heading' : headingColor === 'grey', 'white-heading' : headingColor === 'white', 'heading-second-level' : heading === 'h2' }" > {{ title }} </h2>
        <h3 v-if="level === 3" :class="{'grey-heading' : headingColor === 'grey', 'white-heading' : headingColor === 'white', 'heading-third-level' : heading === 'h3'}" > {{ title }} </h3>
        <h4 v-if="level === 4" :class="{'grey-heading' : headingColor === 'grey', 'white-heading' : headingColor === 'white', 'heading-fourth-level' : heading === 'h4' }" > {{ title }} </h4>
    </div>
</template>

<script>
export default {
    name: 'Heading',
    props: {
        level: {
            type: Number
        },
        title: {
            type: String
        },
        heading: {
            type: String
        },
        headingColor: {
            type:String
        }
    }
}
</script>

<style lang="scss"> 
    .heading-first-level {
        font-size: 60px;
        line-height: 72px;
        letter-spacing: 1.5px;
        font-weight: 900;
    }
    .heading-second-level {
        line-height: 24px;
        font-size: 18px;
        letter-spacing: 0.6px;
        font-weight: 400;
    }
    .heading-third-level {
        font-size: 14px;
        line-height: 18px;
        letter-spacing: 2px;
        font-weight: 900;
    }
    .heading-fourth-level {
        font-size: 14px;
        line-height: 16px;
        letter-spacing: 0.5px;
        font-weight: 400;
    }
    .white-heading {
        color: #fff;
    }
    .grey-heading {
        color: #666;
        text-transform: uppercase;
    }

</style>