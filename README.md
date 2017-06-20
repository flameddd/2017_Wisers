
# `慧科 Wisers 工作紀錄`

## 2017/06/20 第一篇工作紀錄

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
比較的時候，它是拿內部的 hash 去做比較，沒有做「歷遍」，所以這樣效能好。

仔細看了點 [react-decoration](https://github.com/mbasso/react-decoration) ，原來這麼強大，看來是很好用的工具！

Wevo 這專案用的框架是 [react-boilerplate](https://github.com/react-boilerplate/react-boilerplate) 是個很強的基底，星星數 14K 真是誇張。
硬要說缺點的話，就是 redux async 的方案我不喜歡， redux-saga 採用的方法是 generator 的方式，此方式實在沒有很好閱讀、維護。 Node.js 都支援 async, wait 的方式了。更不用說沒支援 ReactiveX 了。　個人還是想朝 ReactiveX 下去磨練。
把 HTML tag 改寫成 component 方式我第一次看到，這樣寫有很強的優點在，可以一次設定完所有的 styles 。 `styled-components` 我有感受到這　library 的強大了，比起官方的 JSX 把 Html、CSS 一起混搭進去在 Javascript 裡面框架清楚很多！

~~想到一個 `styled-components` 的缺點，這樣寫成 Javascript 以後，我們的 IDE 就沒有辦法用 plugin 來 css color highlight 了！　這個很可惜
像我這樣 css 弱雞，看到 `background-color: #fafafa` 的時候，根本沒辦法一時想像出是甚麼顏色！！！！~~

找了其他的 entension 解決了！ Color Highlight 

```javascript
// Install ServiceWorker and AppCache in the end since
// it's not most important operation and if main code fails,
// we do not want it installed
if (process.env.NODE_ENV === 'production') {
  require('offline-plugin/runtime').install(); // eslint-disable-line global-require
}
```
webpack 的plugin `offline-plugin` ，原來有這麼強大的 plugin ，讓 User 看過的頁面都緩存起來。但這邊註解也有提到，如果你的 code fial 掉的話也沒甚麼幫助，所以並不是一定要使用此方案，看來還是視情況而定了！！


待會也看一下 SASS 。搜尋了一下，目前沒有寫任何 SASS ，有用到的都是第三方的 library e.x. bootstrap 。


有說這套系統是要給「客戶」使用的，那我想 SEO 的重要性就很低了，因為目前這套基底是 CSR 架構，不方便做 SEO ，希望最初的架構師有想到這個因素。
（我要趁機研究一下 pre render 嗎？～）

明天香港的同事要來跟我們解釋系統！ 
