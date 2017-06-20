
# `慧科 Wisers 工作紀錄`

`2017/06/19` 任職，職務為 `Node.js Developer` 。第一個專案為 `Wevo` 

reselect 的架構我第一次看到
redux-sage 處理 redux async 的操作

folder 結構也不太一樣 actions、reducers 是放在 container 同層目錄底下

createStore 呢？

components -> dispatch(action) -> redux-sage  -> redux store
                                 這兩關的順序我沒弄清楚

redux-saga 原來是有所謂的 pattern 參數，只要 dispatch 送出來的 actions 跟 pattern 相符合，就會 trigger saga 去做事情。
saga 說到底就是 redux async 的一個方案。
                                 
reselect 目的是為了改善 redux 效能，但感覺這個方案玩的很極端了！有需要為了這樣改善去存記憶體嗎？
沒有實測過，不知道成效如何。另外這樣的架構堆疊起來又更複雜了！！　前端的命啊。

接著繼續熟悉 immutable 吧，這邊當初就沒有很熟
最主要是 array, object 不好比較，所以透過 immutable.is 來處理不但方便、又快速！

仔細看了點 [react-decoration](https://github.com/mbasso/react-decoration) ，原來這麼強大，看來是很好用的工具！
