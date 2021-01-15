<template>
    <div>
        <div class="title">热门推荐</div>
        <ul class="menu" v-for="menuInfo in menuList" v-bind:key="menuInfo.id">
            <li @click="menuInfo.click">
				<p >{{menuInfo.name}}</p>
			</li>
        </ul>
    </div>
</template>
<script>
import Msg from './msg.js'
export default {
	data() {
		return {
			menuList: [{
				id: 1,
				name: '笔记本电脑',
				click: function () {
					Msg.$emit('val', '1')
				}
			}, {
				id: 2,
				name: '手机',
				click: function () {
					Msg.$emit('val', '2')
				}
			}, {
				id: 3,
				name: '服饰',
				click: function () {
					Msg.$emit('val', '3')
				}
			}, {
				id: 4,
				name: '手表',
				click: function () {
					Msg.$emit('val', '4')
				}
			}, {
				name: '书籍',
				click: function () {
					Msg.$emit('val', '5')
				}
			}, {
				name: '玩具',
				click: function () {
					Msg.$emit('val', '6')
				}
			}, {
				name: '家电',
				click: function () {
					Msg.$emit('val', '7')
				}
			}, {
				name: '学习用品',
				click: function () {
					Msg.$emit('val', '8')
				}
			}, {
				name: '办公用品',
				click: function () {
					Msg.$emit('val', '9')
				}
			}, {
				name: '旅游必备',
				click: function () {
					Msg.$emit('val', '10')
				}
			}, {
				name: '游戏专栏',
				click: function () {
					Msg.$emit('val', '11')
				}
			}]
		}
	},
	mounted: function() {
		var _this=this;
		Msg.$on('val', function(m) {
			for (var i = 0; i < document.getElementsByClassName('menu').length; i++) {
				document.getElementsByClassName('menu')[i]['style']['color'] = 'black';
			}
			document.getElementsByClassName('menu')[m-1]['style']['color'] = 'blue';
		})
	}
}
</script>
<style type='text/css'>
    .title{
		width: 100px;
		color: red;
	}
    .menu li{
		list-style: none;						/* 去掉li前面的点 */
		height: 50px;
		margin-top: 2px;
		background-color: white;
		line-height: 50px;					/* 行高与height一致可居中 */
		cursor: pointer;						/* 鼠标指针-手型 */
	}
	.menu li:active{
		color: blue;
	}
	.menu li:default{
		color: lightgrey;
	}
</style>