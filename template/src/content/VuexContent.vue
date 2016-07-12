<template>
    <div>
        <h3>Vuex Content</h3>
        <button class="btn btn-success" @click="trySetUser">Vuex setUser</button>
        <pre>user from vuex.store</pre>
        <pre>{{user | json }}</pre>
        <button class="btn btn-danger" v-if="user.username" @click="logoutUser">Vuex clearUser</button>
        <pre>msg from this.$data.msg</pre>
        <pre>'{{msg}}'</pre>
    </div>
</template>
<script>
    export default{
        vuex: {  
            getters: {
                user: function(store){ return store.user }
            },
            actions: {
                setUser ({dispatch}, obj) {
                    this.msg = 'user set!'
                    dispatch('SET_USER', obj)
                },
                logoutUser ({dispatch}) {
                    this.msg = 'user clear!'
                    dispatch('CLEAR_USER')
                }
            }
        },

        data () {
            return {
                msg: ''
            }
        },

        methods: {
            trySetUser(){
                  let obj = {
                    user: {
                        username: 'New username',
                        email: 'email@email.com'
                    }
                  }
                  this.setUser(obj);
            }
        }
    }    
</script>