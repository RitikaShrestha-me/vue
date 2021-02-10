<template>
    
    <!-- Vue Directives -->

    <!-- use of vue directive v-html to render the string as html statement (element) -->
    <div v-html="name" ></div>

    <!-- render title -->
    <!-- use of vue directive, shows this if isShowing is true else hide it -->
    <h1 v-if="isShowing">{{ title }}</h1>
    <!-- shows this if above isShowing is null -->
    <p v-else-if="isShowing === null">v-else-if part</p>
    <!-- shows this if above isShowing is false -->
    <p v-else>v-else part</p>

    <!-- v-show while false just hides the content by using display:none; property so, vlaue is conserved -->
    <p v-show="showOrHide">Hidden Text</p>

    <!-- any can be used "Mustache" or v-text -->
    <p><span>Count is: </span>{{ count }}</p>
    <p v-text="count"></p>

    <!-- v-once stops rerendering of element -->
    <p v-once v-text="count"></p>

</template>

<script>
export default {
    data(){
        return{
            title: "Learning VueJS 3",
            name: "<h2>It's Me Vue3</h2>",
            isShowing: true,
            showOrHide: true,
            count: 0,
        };
    },
    mounted(){
        setInterval(()=>{
            this.count++;
        },1000);
    }
};
</script>