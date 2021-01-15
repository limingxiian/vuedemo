<template>
    <div>
        <div v-if="kk==='1'">
            <GoodList :goodId='1'></GoodList>
        </div>
        <div v-else-if="kk==='2'">
            <GoodList :goodId='2'></GoodList>
        </div>
        <div v-else-if="kk==='3'">
            <GoodList></GoodList>
        </div>
        <div v-else>
            <GoodList :goodId='0'></GoodList>
        </div>
    </div>
</template>
<script>
    import Msg from './msg.js'
    import GoodList from './GoodList'
    export default {
        components: {
            GoodList
        },
        data() {
            return {
                kk: 0
            }
        },
        mounted: function() {
            var _this=this;
            Msg.$on('val', function(m) {
                _this.kk = m;
            })
        }
    }
</script>