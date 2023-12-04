```js
state: {
    // 播放列表
    playList: [{...}],
    lyricList:{},//歌词
    currentTime:0,//播放时间
    playListIndex:0,//默认下标为0
    isStopBtnShow:true,//播放暂停显示
    detailShow:false,//歌曲详情页显示
    duration:0,//歌曲时长
}
getters:{/*获取方法*/}
mutations:{/*更新方法*/}
actions:{//异步网络请求
	//更新歌词
	getLyric:async function(context,value){
	  let res = await getMusicLyric(value)
	  context.commit('updateLyricList',res.data.lrc)
	}
}