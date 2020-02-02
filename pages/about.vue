<template>
    <div>
        <h1>About Us</h1>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil, laborum. Enim consectetur optio earum eaque blanditiis culpa. 
            Accusantium delectus architecto et molestiae excepturi, earum obcaecati, doloribus, ratione provident quas exercitationem?</p>
    </div>
</template>

<script>
    export default {
        head() {
            return {
                title: 'About Us',
                meta: [
                    {
                        hid: 'description',
                        name: 'description',
                        content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit'
                    }
                ]
            }
        }
    }
</script>